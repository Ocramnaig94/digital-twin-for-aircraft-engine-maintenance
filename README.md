# A Digital-Twin (DT) based solution for predictive maintenance of aircraft engine
An initial Digital Twin prototype for aircraft engine health management, starting from the data acquisition process up to the application of Deep Learning (DL) techniques, in order to identify possible faults (diagnostics) and to predict the RUL of the aircraft engine (prognostics) for assessing the overall health of the structure

The goal is to implement a predictive maintenance workflow:

+ **Data acquisition process**: Using the renowned [N-CMAPSS](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/#:~:text=Turbofan%20Engine%20Degradation%20Simulation%2D2) dataset, developed by NASA researchers.
+ **Exploratory Data Analysis (EDA)**: The first step to perform for understanding the dataset structure by pinpointing the important traits.
+ **Data preprocessing stage**: Cleaning up data and transforming them, if necessary.
+ **Feature selection step**: Applying specific techniques in order to choose only relevant features.
+ **Deep Learning models**: The core of the Digital Twin, represented by the Long Short-Term Memory (LSTM) architecture.
+ **Data visualization tools**: A simple dashboard to check whether a failure has occurred and how much time is left for the intervention.
