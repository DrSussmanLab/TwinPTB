# TwinPTB
Code Repository for the manuscript "Prediction of Preterm Birth from Successive Cervical Length Measurements in Twin Pregnancies Using Machine Learning"

## Files included

**pre_process.ipynb**
Given a CSV file containing features related to twin PTB, this notebook drops irrelevant features, defines new features, and ensures features are aggregated such that each patient contains 1 row of features (aggregation of exams). 

**dataset_creation.ipynb**
Splits the data generated from pre_process.ipynb into global and binned cervical length features as explained in the manuscript. 

**train.ipynb**
Loads all four datasets and performs a 5-fold CV hyperparameter search on various machine learning models. Once the best parameters are found, we perform 10-fold CV and bootstrap for each dataset and model. Results are saved in:
results.json -> Results from bootstrapped CV for each dataset, model and label.
cv_fold_metrics.json -> Results from 10-fold CV give each fold values for each dataset, model and label.
outer_predictions.json -> Results for a list of every prediction value on each specific patient. 

