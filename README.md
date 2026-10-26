# PM2.5 Forecasting Using Machine Learning

## Project Overview

This project explores predicting PM2.5 (fine particulate matter) concentrations using machine learning techniques and historical air-quality and weather data.

The project uses the Beijing Multi-Site Air Quality dataset to develop a forecasting workflow using a Random Forest Regressor.

**Project Status:** Prototype in progress. Data validation is still required, and performance in European countries has not yet been tested.

## Objectives

- Analyze historical PM2.5 measurements.
- Prepare air-quality and weather data for machine learning.
- Create time-based features, including previous-hour PM2.5 readings.
- Train a Random Forest regression model.
- Evaluate predictions using standard regression metrics.
- Compare model performance against a previous-hour baseline.

## Dataset

**Dataset:** Beijing Multi-Site Air Quality Data

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/501/beijing+multi+site+air+quality+data)

The dataset contains hourly air-quality measurements from multiple monitoring stations, including PM2.5, other pollutants, and meteorological variables.

A separate 12-row CSV was explored during development but was not used as a confirmed PM2.5 dataset because its pollutant identity was unclear.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib
- Jupyter Notebook

## Features Used

### Weather Features
- Temperature (`TEMP`)
- Atmospheric pressure (`PRES`)
- Dew point (`DEWP`)
- Rainfall (`RAIN`)
- Wind speed (`WSPM`)

### Air Quality Features
- Sulfur dioxide (`SO2`)
- Nitrogen dioxide (`NO2`)
- Carbon monoxide (`CO`)
- Ozone (`O3`)
- PM10

### Time Features
- Hour
- Month
- Previous-hour PM2.5 concentration

**Target variable:** `PM2.5`

## Methodology

1. Load and combine the station CSV files.
2. Process timestamps and station identifiers.
3. Inspect missing values and duplicate station-time records.
4. Create the previous-hour PM2.5 feature.
5. Split data chronologically into 80% training and 20% testing sets.
6. Train a Random Forest Regressor.
7. Generate predictions on the test data.
8. Evaluate the model and compare it with a previous-hour baseline.
9. Visualize prediction errors and feature importance.
10. Export predictions and evaluation results.

## Model Evaluation

The model is evaluated using the following metrics:

| Metric | Purpose |
|---|---|
| MAE | Measures average absolute prediction error |
| RMSE | Penalizes larger prediction errors |
| R² Score | Measures how well the model explains variation |
| Baseline MAE | Evaluates the previous-hour prediction baseline |
| Baseline RMSE | Measures baseline prediction error |

Final metric values will be added after the dataset and model results have been validated.

## Project Files

```text
pm25-forecasting/
├── pm25_forecasting.ipynb
├── README.md
├── pm25_project_report.pdf
├── requirements.txt
└── results/
    ├── pm25_predictions.csv
    ├── pm25_evaluation.csv
    └── pm25_feature_importance.csv
```

Only include result files that were actually generated successfully.

## Installation

Install the required Python packages:

```bash
pip install pandas numpy matplotlib scikit-learn joblib jupyter
```

## How to Run

1. Download the dataset from the UCI Machine Learning Repository.
2. Place the station CSV files where the notebook expects them.
3. Open `pm25_forecasting.ipynb` in Jupyter Notebook or JupyterLab.
4. Restart the kernel and execute the notebook cells in order.
5. Review the data-quality checks before training the model.
6. Examine the evaluation metrics and generated visualizations.

## Limitations

- The current development dataset is from Beijing.
- Performance in Czechia, Hungary, Germany, France, and Italy has not been validated.
- Duplicate station-time records and unexpected extra columns must be investigated.
- Data leakage must be ruled out before the reported metrics can be trusted.
- The final model performance must be reproduced using a clean dataset and chronological test split.

## Future Improvements

- Validate the data and model evaluation pipeline.
- Obtain suitable European PM2.5 observations.
- Test the model on European air-quality data.
- Compare additional machine learning models.
- Develop a dashboard to visualize forecasts and historical air quality.

## References

- [UCI Machine Learning Repository: Beijing Multi-Site Air Quality Data](https://archive.ics.uci.edu/dataset/501/beijing+multi+site+air+quality+data)
- [European Environment Agency Datahub](https://www.eea.europa.eu/en/datahub)
- [Scikit-learn Documentation](https://scikit-learn.org/)

## Author

**Name:** Add your name here  
**Course:** Add your course here  
**Institution:** Add your institution here
