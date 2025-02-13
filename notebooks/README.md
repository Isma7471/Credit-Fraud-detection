# Task 1: Data Preprocessing and Exploratory Data Analysis (EDA)

## Overview

This task involves the preprocessing and exploratory data analysis (EDA) of datasets related to fraud detection. The steps include loading datasets, handling missing values, cleaning the data, conducting univariate and bivariate analyses, performing geolocation-based analysis, and engineering features for further modeling.

## Datasets Used

*   `creditcard_data`: Contains credit card transaction information.
*   `fraud_data`: Includes details on fraudulent and non-fraudulent transactions.
*   `ip_data`: Maps IP address ranges to corresponding countries for geolocation analysis.

## Steps Performed

1.  **Loading Data:**
    The datasets are loaded using `pandas.read_csv()` from the following paths:

    *   `data/raw/creditcard.csv`
    *   `data/raw/Fraud_Data.csv`
    *   `data/raw/IpAddress_to_Country.csv`

2.  **Handling Missing Values:**
    *   Dropped columns with more than 50% missing values.
    *   Filled missing values with the median of the respective columns.

3.  **Data Cleaning:**
    *   Removed duplicate entries.
    *   Converted `transaction_time` to datetime format for time-based analysis.

4.  **Exploratory Data Analysis (EDA):**

    *   **Univariate Analysis:**
        *   Class Distribution: Plotted the count of fraudulent vs. non-fraudulent transactions.
        *   Transaction Amount Distribution: Visualized the distribution of transaction amounts.

    *   **Bivariate Analysis:**
        *   Transaction Amount by Class: Used boxplots to compare transaction amounts for fraudulent and non-fraudulent transactions.
        *   Transactions by Hour of Day: Analyzed transaction frequency by hour to identify patterns in fraudulent activities.

5.  **Geolocation Analysis:**
    *   Converted IP addresses to integers for easier merging.
    *   Merged `fraud_data` with `ip_data` based on IP address ranges.
    *   Visualized the top 10 countries by transaction count to identify geographical fraud patterns.

6.  **Feature Engineering:**
    *   **Time Features:** Extracted the day of the week and calculated time differences between consecutive transactions.
    *   **Scaling:** Standardized numerical features like `transaction_amount` and `time_diff` using `StandardScaler`.
    *   **Categorical Encoding:** Encoded categorical features (`device_type`, `browser`, `country`) using `LabelEncoder`.

7.  **Saving Processed Data:**
    Saved the processed datasets for further modeling:

    *   `data/processed/fraud_data_processed.csv`
    *   `data/processed/creditcard_data_processed.csv`

## Visualizations

*   **Class Distribution:** Bar plot showing the proportion of fraud vs. non-fraud.
*   **Transaction Amounts:** Histogram depicting the distribution of transaction values.
*   **Transaction Patterns:** Boxplot comparing transaction amounts across classes and histogram for transaction frequency by hour.
*   **Country Analysis:** Bar plot showcasing the top 10 countries with the highest number of transactions.

## Dependencies

The following Python libraries are required:

*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `sklearn`