# RMR Data Analysis

This project analyzes RMR business transaction data and customer data to provide insights and predictions using various machine learning techniques. The aim is to optimize operational strategies and decision-making processes for RMR.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Preprocessing Steps](#preprocessing-steps)
- [Machine Learning Methods](#machine-learning-methods)
- [Results and Insights](#results-and-insights)
- [Technologies Used](#technologies-used)
- [Usage Instructions](#usage-instructions)

---

## Introduction
This project focuses on leveraging machine learning to extract valuable insights from RMR transaction and customer data. The goals include:
1. Predicting future donation and expenses.
2. Analyzing customer highest demand and how they know about RMR.
3. Identifying clusters of customer behavior and donation patterns.

---

## Dataset
The dataset used contains the following fields:
- `Menu_dan_Porsi`: The menu for each date and how much they serve this menu.
- `Menu`: The name of the menu and how much they serve this menu each month.
- `Survey RMR`: The survey for each visitor of RMR.
- `Pengeluaran`: How much expense each much RMR have.
- `Pemasukan`: How much donation does RMR get.

The data represents monthly transactions for RMR.

---

## Preprocessing Steps
1. **Date Conversion**:
   - `Per Tanggal` converted to datetime format.
   - Extracted `Bulan Index` for grouping data by the month.
   - All data from `Pekerjaan/Status` that contains a keyword such as "driver online" or "driver gojek" converted to "mitra ojek online"
   - All data from `Pekerjaan/Status` that contains a keyword such as "pensiunan" converted to "pensiun"
2. **Feature Engineering**:
   - Calculated monthly totals for:
     - Total donation of each person (`Frekuensi`).
     - Total donation (`Total Donasi Bulanan`).
   - Added `MonthIndex` to represent months numerically.
3. **Encoding**:
   - Encoded `Label` as binary (`1` for `Loyal`, `0` for `Biasa`).

---

## Machine Learning Methods
Four machine learning methods were applied:

### 1. **Linear Regression**
   - Used for predicting monthly donation based on `Total Donasi` and `MonthIndex`.
   - Output: Scatter plot comparing actual vs. predicted donation.

### 2. **Time-Series Forecasting**
   - Used for predicting future expenses based on `Pengeluaran Tiap Bulan` dan `Growth Rate`.
   - Output: Prediction of next month expenses.

### 3. **Naive Bayes**
   - Used for classification two types of donors such as 'Loyal' and 'Biasa' donors based on `Frekuensi` and `Average Donation`.
   - Output: List of all the donors with the classification.

---

## Results and Insights
1. **Donation Prediction**:
   - Linear regression provided a reasonable prediction of monthly donation, showing alignment between actual and predicted values.
2. **Expenses Prediction**:
   - Time-series forecasting provided a reasonable prediction of monthly expenses, showing the growth rate of each expenses.
3. **Classification of Donors**:
   - Naive Bayes effectively classified each donors with its class.

---

## Technologies Used
- **Programming Language**: Python
- **Libraries**:
  - Data Analysis: `pandas`, `numpy`
  - Visualization: `matplotlib`, `seaborn`
  - Machine Learning: `scikit-learn`

---

## Usage Instructions
1. Clone the repository:
   ```bash
   https://github.com/SalomoAgung/Big-Data-Analytics-for-Business-RMR.git
