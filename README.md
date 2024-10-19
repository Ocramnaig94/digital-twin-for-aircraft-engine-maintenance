# A Digital-Twin (DT) based solution for predictive maintenance of aircraft engine
An initial Digital Twin prototype for aircraft engine health management, starting from the data acquisition process up to the application of Deep Learning (DL) techniques, in order to identify possible faults (diagnostics) and to predict the RUL of the aircraft engine (prognostics) for assessing the overall health of the structure

The goal is to implement a predictive maintenance workflow:

+ **Data acquisition process**: Using the renowned [N-CMAPSS](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/#:~:text=Turbofan%20Engine%20Degradation%20Simulation%2D2) dataset, developed by NASA researchers.
+ **Exploratory Data Analysis (EDA)**: The first step to perform for understanding the dataset structure by pinpointing the important traits.
+ **Data preprocessing stage**: Cleaning up data and transforming them, if necessary.
+ **Feature selection step**: Applying specific techniques in order to choose only relevant features.
+ **Deep Learning models**: The core of the Digital Twin, represented by the Long Short-Term Memory (LSTM) architecture.
+ **Data visualization tools**: A simple dashboard to check whether a failure has occurred and how much time is left for the intervention.

## The workflow 

1. Of the several datasets provided by Nasa, the focus is placed on the third set **`N-CMAPSS_DS03-012.h5`**, whose download link is mentioned above. The dataset is divided into development and test set.

2. Exploratory Data Analysis is applied by analysing data with visual aid in `Exploratory_data_analysis.ipynb`. In short, any missing value is found, different unit numbers and flight classes are investigated and the existing failure modes are analysed.
