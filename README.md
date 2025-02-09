# A Digital-Twin (DT) based solution for predictive maintenance of aircraft engine
An initial Digital Twin prototype for aircraft engine health management, starting from the data acquisition process up to the application of Deep Learning (DL) techniques, in order to identify possible faults (diagnostics) and to predict the RUL of the aircraft engine (prognostics) for assessing the overall health of the structure. For this purpose, the renowned [N-CMAPSS](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/#:~:text=Turbofan%20Engine%20Degradation%20Simulation%2D2) dataset, developed by NASA researchers, is used.

The first goal is to implement a predictive maintenance workflow:

+ **Exploratory Data Analysis (EDA)**: The first step to perform for understanding the dataset structure by pinpointing the important traits.
+ **Feature selection step**: Applying specific techniques in order to choose only relevant features.
+ **Deep Learning models**: The core of the Digital Twin, represented by the Long Short-Term Memory (LSTM) architecture.

## The workflow 

Of the several datasets provided by Nasa, the focus is placed on the third set **`N-CMAPSS_DS03-012.h5`**, whose download link is mentioned above. The dataset is divided into development and test set.

1. Exploratory Data Analysis is applied by analysing data with visual aid in `Exploratory_data_analysis.ipynb`. In short, different unit numbers and flight classes are investigated and the existing failure modes are analysed, in order to perform data preprocessing correctly.
   
2. Feature selection is applied both for diagnostics and prognostics tasks in `Feature_selection.ipynb`, using the ANOVA technique and the Mutual Information measure. The scores of each apporach are saved in the `feature_selection_models` folder.

3. Two distinct models for each task are trained in `Deep_learning_model.ipynb`. The Deep Learning model chosen for both tasks is made of Long-Short Term memory (LSTM) layers, specifically of the Bidirectional type. The models and the scaler are saved in the `deep_learning_models` folder.

The second and last goal is to present a real use case to demonstrate the applicability of the previously proposed models:

+ **Data acquisition process**: Capturing the required data and sending them upon request.
+ **Data evaluation step**: Evaluating the incoming data and sending the evaluation results back.
+ **Data visualization tools**: A simple dashboard to check whether a failure has occurred and how much time is left for the intervention.

## The use case

The scenario described involves three different agents that communicate with each other through the [Mosquitto MQTT Broker](https://mosquitto.org/), each one with its own specific task: 

1. The task of capturing the required data is assigned in `Agent_collection.ipynb`, by loading the entire test set in memory and by sending the entire flight data at a time when requested.

2. The entire logic for evaluating the incoming data is present in `Agent_evaluation.ipynb`, which will first apply the preprocessing steps needed on the raw data.

3. A [Node-RED](https://nodered.org/) instance enables communication between the agents in `Agent_dashboard.ipynb`, providing a dashboard that delivers key features about the aircraft health state.

## Prerequisites

Install pip, the package manager for Python3 in order to install the required packages for running the notebooks with:
```
pip install -r requirements.txt
```
To be able to start effectively the agents, also install the Mosquitto MQTT Broker (**v2.0.18**), Node.js (**v17.9.1**) and Node-RED (**v3.0.2**). In order to install the extra modules needed for the node-RED dashboard, copy `package.json` into the local **.node-red** folder and from the same directory run:
```
npm install
```

