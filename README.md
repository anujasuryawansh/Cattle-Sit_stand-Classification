# Cattle-Sit_stand-Classification
# Predict the sit_stand label using time-series sensor data from data.csv and generate predictions for evaluation_ext.csv.
# Approach:
1) Data Preprocessing:
-Parsed sensor values (e.g., ax, ay, ..., mz) which were stored as strings representing arrays.
-Cleaned and converted these strings into numeric arrays.

2) Feature Engineering: 
-From each sensor array, extracted summary statistics: 
-Mean, Standard Deviation, Min, and Max.

3) Model Selection:
 -Used Random Forest Classifier for its robustness on tabular data and ability to handle feature importance.
 -Split data.csv into training and validation sets (80-20 split).
 -Achieved good accuracy on validation data.

4) Prediction:
   -Applied the trained model to evaluation_ext.csv.
   -Appended predictions as a new column sit_stand_predicted.

# Key Observations:
-Sensor readings were noisy, but using summary features like mean and max helped capture useful patterns.
-Random Forest worked well without needing to scale or normalize the data.
-Using PCA reduced extra noise and helped improve accuracy and prevent overfitting.

# Model Used:
-Random Forest Classifier was used for its robustness and ability to handle mixed types of features.
-It works well without needing scaling or normalization.
-The model was trained on statistical summaries (like mean, std, max) of the sensor data.
-PCA (Principal Component Analysis) was used to reduce dimensionality and noise before model training.
