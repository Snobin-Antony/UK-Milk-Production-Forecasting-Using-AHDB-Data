# UK Milk Production Forecasting Using AHDB Data

![Project Status](https://img.shields.io/badge/status-in_progress-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)

A data science project to forecast daily milk production in the United Kingdom using historical data from the Agriculture and Horticulture Development Board (AHDB). This repository contains the code and methodology for building a predictive time-series model with XGBoost.



---

## Overview

The goal of this project is to build a reliable machine learning model that can accurately predict future milk production volumes. By leveraging time-series analysis techniques, the model learns from historical trends, seasonality, and other patterns to generate forecasts. This can be valuable for farmers, dairy processors, and policy-makers for planning and resource management.

The core of the project is a Jupyter Notebook that walks through the entire data science workflow, from data cleaning to model evaluation.

---

## Methodology & Workflow

The forecasting process is broken down into four key stages:

1.  **Data Collection & Loading**: The dataset from AHDB is loaded into a pandas DataFrame. Initial cleaning steps are performed to handle data types and formatting issues.
2.  **Feature Engineering**: New features are created from the date index to help the model understand time-based patterns. This includes:
    * **Time-based features**: Year, month, week of the year, day of the week.
    * **Lag features**: Production values from previous days (e.g., 7 days ago).
    * **Rolling window features**: Averages or other stats over a time window (e.g., 7-day rolling mean).
3.  **Model Training**: An XGBoost (Extreme Gradient Boosting) model is trained on the historical data. The data is split chronologically into a training set and a test set to ensure the model is validated on unseen future data.
4.  **Evaluation & Visualization**: The trained model's performance is evaluated by comparing its predictions on the test set against the actual production values. The results are visualized in a plot to provide a clear understanding of the forecast accuracy.

---

## Getting Started

To run this project on your local machine, follow these steps.

### Prerequisites

You need Python 3.8+ and pip installed on your system.

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Snobin-Antony/UK-Milk-Production-Forecasting-Using-AHDB-Data.git
    cd UK-Milk-Production-Forecasting-Using-AHDB-Data
    ```

2.  **Install the required libraries:**
    The necessary libraries.
    ```bash
    pip install pandas scikit-learn xgboost matplotlib
    ```
---

## Usage

1.  Place the AHDB milk production CSV file in the `/` directory.
2.  Open the Jupyter Notebook `milk-production-forecast.ipynb`.
3.  Run the cells in the notebook sequentially to see the workflow from data loading to final prediction.

---

## Results

The final model is able to capture the primary trend and seasonality in the milk production data. The plot below shows the model's predictions (forecast) against the actual production values for the test period.

*(Here you can add an image of your final forecast plot)*
`![Forecast Plot](images/forecast_plot.png)`

The model achieves a **Root Mean Squared Error (RMSE)** of 0.54 on the test set, indicating the average prediction error in million litres.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
