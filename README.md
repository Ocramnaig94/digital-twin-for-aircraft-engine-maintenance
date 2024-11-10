# A Digital-Twin (DT) based solution for predictive maintenance of aircraft engine
An initial Digital Twin prototype for aircraft engine health management, starting from the data acquisition process up to the application of Deep Learning (DL) techniques, in order to identify possible faults (diagnostics) and to predict the RUL of the aircraft engine (prognostics) for assessing the overall health of the structure

The goal is to implement a predictive maintenance workflow:

+ **Data acquisition process**: Using the renowned [N-CMAPSS](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/#:~:text=Turbofan%20Engine%20Degradation%20Simulation%2D2) dataset, developed by NASA researchers.
+ **Exploratory Data Analysis (EDA)**: The first step to perform for understanding the dataset structure by pinpointing the important traits.
+ **Feature selection step**: Applying specific techniques in order to choose only relevant features.
+ **Deep Learning models**: The core of the Digital Twin, represented by the Long Short-Term Memory (LSTM) architecture.
+ **Data visualization tools**: A simple dashboard to check whether a failure has occurred and how much time is left for the intervention.

## The workflow 

Of the several datasets provided by Nasa, the focus is placed on the third set **`N-CMAPSS_DS03-012.h5`**, whose download link is mentioned above. The dataset is divided into development and test set.

1. Exploratory Data Analysis is applied by analysing data with visual aid in `Exploratory_data_analysis.ipynb`. In short, different unit numbers and flight classes are investigated and the existing failure modes are analysed, in order to perform data preprocessing correctly.
   
2. Feature selection is applied both for diagnostics and prognostics tasks in `Feature_selection.ipynb`, using the ANOVA technique and the Mutual Information measure. The scores of each apporach are saved in the `feature_selection_models` folder.

3. Two distinct models for each task are trained in `Deep_learning_model.ipynb`. The Deep Learning model chosen for both tasks is made of Long-Short Term memory (LSTM) layers, specifically of the Bidirectional type. The models are saved in the `deep_learning_models` folder.
