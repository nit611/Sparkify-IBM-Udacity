# Predict Customer Churn - with Spark for python.

## Table of Contents

1. [Overview](#overview)
2. [Installations](#installations)
3. [Data](#data)
4. [Modelling](#Modelling)
5. [Results & Thoughts](#results)
6. [Conclusion](#conclusion)

## <a name="overview"></a> Overview

The Capstone project for [Udacity's Data Scientist Nanodegree](https://www.udacity.com/course/data-scientist-nanodegree--nd025). This project involves predicting **Customer Churn for a hypothetical music streaming app Sparkify**, using Spark's MLlib to engineer features and build a classification model. The dataset used here is a medium-sized (248 MB, with 544,000 rows) version of the whole dataset (which is 12 GB). <br>
This project is worked on [IBM Cloud's Watson Studio](https://www.ibm.com/se-en/cloud/watson-studio), uploading the data cluster, with a Python 3.7/Spark 3.0 enabled Jupyter Notebook. <br>

Using `pyspark`, the project broadly involves the following:

- Loading and cleaning the data.
- Exploratory Data Analysis - where the data is explored in its depth, and data visualizations to help with selecting features, and to basically understand the data more.
- Feature Engineering - appropriate features are selected based on the EDA, as well as creating new features from existing data, to create a final dataset ready for training using Spark's ML.
- Modelling - four different classification algorithms are tested, based on its characteristics, and is evaluated using metrics. This section also involves further tuning of the model that has highest potential (based on the metric defined)
- Concluding Remarks - This section summarizes the whole project, along with a couple of thoughts and possible improvements to the project for further scalability to the whole dataset.

## <a name="installations"></a> Installations

- Python 3.6+
- `pyspark.*`
- Jupyter - available through [this link](https://jupyter.org/install), or IBM Watson Studio (Lite)

## <a name="data"></a> Data

The data is provided by Udacity. Due to the size of the data, it is not avaialable in this repository. <br>
A broad overview of the raw data:

- `artist` - the artist of the soundtrack
- `auth` - variable indicating whether the user has cancelled the subscription or not
- `firstName` - first name of the user
- `gender` - gender of the user
- `ItemInSession` - Item ID for each session (row) recorded
- `lastName` - last name of the user
- `length` - length of each session by the user
- `level` - the level of subscription of the user (free trial or paid)
- `location` - location data of the user (city and state)
- `page` - the page in Sparkify the user visited in each session
- `song` - the song listened to in each session, by the user
- `ts` - the timestamp of each session
- `userAgent` - the user agent used by the user to visit sparkify
- `userId` - unique number identifying each user

For more information about the data, visit the [Jupyter Notebook above!](https://github.com/nit611/Sparkify-IBM-Udacity/blob/da_real_nit/Sparkify.ipynb).

## <a name="modelling"></a> Modelling

1. The classification algorithms tested here are - Random Forest Classifier, Gradient Boosted Trees Classifier, Logistic Regression and Linear Support Vector Machines. The thorough documentation for the algorithms and its application is available in the [Spark ML documentation](https://spark.apache.org/docs/latest/ml-classification-regression.html).
2. Based on the performance metric, the **F1-Score**, the models are evaluated and for the love of experimentation, I took 3 out of the 4 for hyperparameter tuning, which is the second part of this section of the notebook. For more detailed discussion of the parameters and algorithms selected to tune, visit the section Modelling, linked in the [Jupyter Notebook above!](https://github.com/nit611/Sparkify-IBM-Udacity/blob/da_real_nit/Sparkify.ipynb).

## <a name = "results"></a> Results & Thoughts

The Random Forest classifier performed the best, with an **F1-Score of 88.5%** approximately. The other algorithms performed reasonably well too. However:

- All this must be taken with a grain of salt, as the target variable `Churn`, is imbalanced. Even if the F1-Score does account into the metric the False Positives and False Negatives, before scaling the model to the entire 12 GB dataset, we need to be wary of the result, due to the imbalanced nature.
- Further SMOTE-like oversampling or undersampling to equalize the size of the two classes could be more unbiased, but they come with disadvantages too. They are discussed in the last section of the notebook above.
