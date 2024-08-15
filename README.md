# Weather Prediction using Machine Learning Models

This project focuses on predicting whether it will rain tomorrow based on historical weather data from Australia. Various machine learning models including Logistic Regression, K-Nearest Neighbors (KNN), Decision Tree, Support Vector Machine (SVM), and Linear Regression are trained and evaluated for accuracy.

## Table of Contents
- [Instructions](#instructions)
- [About the Data](#about-the-data)
- [Importing Data](#importing-data)
- [Data Preprocessing](#data-preprocessing)
- [One Hot Encoding](#one-hot-encoding)
- [Train and Test Data Split](#train-and-test-data-split)
- [Model Training and Evaluation](#model-training-and-evaluation)
  - [Linear Regression](#linear-regression)
  - [KNN](#knn)
  - [Decision Tree](#decision-tree)
  - [Logistic Regression](#logistic-regression)
  - [SVM](#svm)
- [Report](#report)
- [About The Dataset](#about-the-dataset)

## Instructions

1. **Install Required Libraries:**
   Install the necessary Python libraries using `pip` or `piplite`.

2. **Import Data:**
   Download and import the dataset for analysis.

3. **Data Preprocessing:**
   Perform one hot encoding for categorical variables and other necessary preprocessing steps.

4. **Split Data:**
   Split the dataset into training and testing sets.

5. **Train Models:**
   Train different machine learning models and evaluate their performance.

6. **Generate Report:**
   Compile the results of all models and present them in a tabular format.

## About the Data

The dataset used in this project contains weather observations from 2008 to 2017 collected by the Australian Government's Bureau of Meteorology. The dataset includes various weather metrics, and the target variable is `RainTomorrow`, which indicates whether it will rain the next day.

The dataset can be downloaded from [this source](https://bitbucket.org/kayontoga/rattle/src/master/data/weatherAUS.RData).

## Importing Data

```python
from pyodide.http import pyfetch

async def download(url, filename):
    response = await pyfetch(url)
    if response.status == 200:
        with open(filename, "wb") as f:
            f.write(await response.bytes())
path='https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-ML0101EN-SkillUp/labs/ML-FinalAssignment/Weather_Data.csv'
await download(path, "Weather_Data.csv")
filename ="Weather_Data.csv"
df = pd.read_csv("Weather_Data.csv")
df.head()
```
