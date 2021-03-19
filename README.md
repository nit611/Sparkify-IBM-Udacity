# Predict Customer Churn - with Spark for python.

## Table of Contents

1. [Overview](#overview)
2. [Installations](#installations)
3. [Data & Files](#data)
4. [Modelling](#Modelling)
5. [Results & Thoughts](#results)
6. [Conclusion](#conclusion)

## <a name="overview"></a> Overview

The Capstone project for [Udacity's Data Scientist Nanodegree](https://www.udacity.com/course/data-scientist-nanodegree--nd025). This project involves predicting customer churn for a hypothetical music streaming app Sparkify, using Spark's MLlib to engineer features and build a classification model. The dataset used here is a medium-sized (248 MB, with 548,000 rows) version of the whole dataset (which is 12 GB). <br>
This project is worked on [IBM Cloud's Watson Studio](https://www.ibm.com/se-en/cloud/watson-studio), uploading the data cluster, with a Python 3.7/Spark 3.0 enabled Jupyter Notebook. <br>

Using `pyspark`, the project broadly involves the following:

- Loading and cleaning the data.
- Exploratory Data Analysis - where the data is explored in its depth, and data visualizations to help with selecting features, and to basically understand the data more.
- Feature Engineering - appropriate features are selected based on the EDA, as well as creating new features from existing data, to create a final dataset ready for training using Spark's ML.
- Modelling - four different classification algorithms are tested, based on its characteristics, and is evaluated using metrics. This section also involves further tuning of the model that has highest potential (based on the metric defined)
- Concluding Remarks - This section summarizes the whole project, along with a couple of thoughts and possible improvements to the project for further scalability to the whole dataset.
