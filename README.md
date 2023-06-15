# Network Intrusion Detection System using Machine Learning
This project aims to build a Network Intrusion Detection System (NIDS) using Machine Learning. The NIDS is trained to detect intrusions or malicious activities on a network. The dataset used for training is the KDD Cup 1999 dataset, which is publicly available. This dataset is a version of the DARPA dataset made to train Intrusion Detection Systems.

# Requirements
The main libraries used in this project are:

- pandas
- numpy
- scikit-learn
- matplotlib
- plotly

You can install the necessary libraries using pip:

```pip install pandas numpy scikit-learn matplotlib plotly```

# Structure
The script begins by importing necessary libraries and loading the training and testing datasets (kdd_train.csv and kdd_test.csv). It then identifies categorical and numerical features in the data and separates the target column ("labels") from the feature columns.

Next, the script handles less frequent values in categorical features by replacing them with a unique identifier. This prevents the model from overfitting to these less frequent values.

The next phase involves data preprocessing. Using scikit-learn's Pipeline and ColumnTransformer, the numerical data are scaled and imputed while the categorical features are one-hot encoded.

A Random Forest classifier model is then trained on the preprocessed data and used to make predictions on the test set. The script outputs several evaluation metrics, such as accuracy, precision, recall, F1-score, and the ROC AUC score.

The script then proceeds to a feature selection phase where it computes feature importance based on the trained Random Forest model. It displays a bar chart of feature importances and calculates the accuracy when using different numbers of the top features.

Finally, the script uses Mutual Information to further refine the feature selection and re-trains a Random Forest model with these selected features. The evaluation metrics are again outputted, along with a multi-class ROC AUC curve plot for each class in the target column.
