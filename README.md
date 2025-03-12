# Fraud Detection in Bank Transactions

Fraud detection is essential to protect financial institutions and their customers from significant losses. This project analyzes a dataset of **2,512 bank transactions** containing **16 features** to detect fraudulent activity using multiple machine learning techniques. By combining clustering methods with anomaly detection algorithms, we aim to build a robust system for flagging potentially fraudulent transactions.

## Table of Contents

- [Introduction](#introduction)
- [Basic Dataset Information](#basic-dataset-information)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Data Preprocessing](#data-preprocessing)
- [Clustering & Fraud Detection with K-Means](#clustering--fraud-detection-with-k-means)
- [Clustering & Fraud Detection with DBSCAN](#clustering--fraud-detection-with-dbscan)
- [Fraud Detection with Isolation Forest](#fraud-detection-with-isolation-forest)
- [Fraud Detection Comparison Across Algorithms](#fraud-detection-comparison-across-algorithms)
- [Setup Instructions](#setup-instructions)
- [Results & Future Work](#results--future-work)
- [License](#license)

## Introduction

This project focuses on detecting fraudulent transactions within a bank transaction dataset. The dataset includes **2,512 transactions** with **16 features** covering transaction details, customer information, and device/location data. Our goal is to analyze this dataset, identify anomalies, and build predictive models to flag potential fraud.

## Basic Dataset Information

Before diving into modeling, we begin with an initial exploration to understand the dataset's structure:

- **Dataset Overview:**  
  Use `df.info()` to inspect data types and non-null counts.
- **Summary Statistics:**  
  Use `df.describe()` to compute measures such as mean, median, and standard deviation for numerical features.

## Data Cleaning

Data cleaning ensures the reliability of our analysis. In this phase, we:

- **Handle Missing and Duplicated Values:**  
  Identify and correct missing data and remove duplicate records.
- **Standardize Data Formats:**  
  Convert dates and other fields to appropriate formats.
- **Detect Outliers:**  
  Identify and treat outliers that may skew analysis.
- **Ensure Categorical Consistency:**  
  Verify that categorical variables have consistent and valid entries.

## Exploratory Data Analysis (EDA)

EDA helps uncover underlying patterns and relationships in the data:

- **Univariate Analysis:**  
  Visualize individual features using histograms, boxplots, and density plots.
- **Bivariate Analysis:**  
  Examine relationships between pairs of variables with scatterplots and correlation matrices.
- **Multivariate Analysis:**  
  Explore complex interactions using pair plots and heatmaps.

## Feature Engineering

Enhancing the dataset with engineered features can improve model performance. We focus on:

- **Time-Based Features:**  
  - *TimeSinceLastTransaction:* Time difference between consecutive transactions.
  - *TransactionHour:* Extracted hour from the transaction timestamp.
- **Transaction Frequency:**  
  - *TransactionFrequency:* Total transactions per account.
- **Device and IP Usage:**  
  - *DeviceUsage* and *IPUsage:* Usage patterns based on device IDs and IP addresses.
- **Merchant Preferences:**  
  - *MerchantPreference:* Count of transactions per account for each merchant.

## Data Preprocessing

Preprocessing prepares the data for machine learning by ensuring consistency and scalability:

- **Categorical Encoding:**  
  Convert categorical variables (e.g., `TransactionType`, `Channel`, `CustomerOccupation`) using mapping and one-hot encoding.
- **Feature Selection & Scaling:**  
  Select relevant features and apply standard scaling to normalize the data.

## Clustering & Fraud Detection with K-Means

We use K-Means clustering to segment transactions and identify anomalies:

- **Elbow Method:**  
  Determine the optimal number of clusters by evaluating inertia.
- **K-Means Clustering:**  
  Cluster the preprocessed data and assign each transaction a cluster label.
- **Distance Calculation & Thresholding:**  
  Compute distances from cluster centroids and flag transactions that exceed a defined threshold as potential fraud.
- **Visualization:**  
  Display clusters, centroids, and flagged transactions through visual plots.

## Clustering & Fraud Detection with DBSCAN

DBSCAN is used to detect anomalies based on density:

- **k-Distance Plot:**  
  Determine an optimal epsilon value by analyzing the 5th nearest neighbor distances.
- **DBSCAN Clustering:**  
  Cluster the scaled data and label noise points as potential fraud.
- **Dimensionality Reduction:**  
  Use PCA to reduce data dimensions for visualization.
- **Visualization:**  
  Highlight potential frauds with distinct markers in a unified dark-themed plot.

## Fraud Detection with Isolation Forest

Isolation Forest isolates anomalies to detect potential fraud:

- **Model Training:**  
  Train the Isolation Forest model on scaled data with a contamination rate of 2%.
- **Fraud Flagging:**  
  Map predictions to 'Fraud' or 'Not Fraud' labels.
- **Dimensionality Reduction:**  
  Apply PCA to reduce dimensions for visualization.
- **Visualization:**  
  Plot normal transactions as borderless circles and fraud cases as red 'X' markers within a unified dark theme.
- **Outcome:**  
  Display the count of transactions flagged as fraud by the model.

## Fraud Detection Comparison Across Algorithms

This section compares the three fraud detection methods (K-Means, DBSCAN, and Isolation Forest):

- **Fraud Subset Extraction:**  
  Isolate transactions flagged as fraudulent by each algorithm.
- **Fraud Count Calculation:**  
  Compare the number of fraud cases detected by each method.
- **Intersection Analysis:**  
  Identify common fraud cases among the different methods.
- **Visualization:**  
  Use bar charts and other visual tools to compare the performance of the algorithms.

## Setup Instructions

To run this project locally, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/fraud-detection-bank-transactions.git
   cd fraud-detection-bank-transactions
