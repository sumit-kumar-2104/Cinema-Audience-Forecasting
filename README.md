# Cinema-Audience-Forecasting
A time-series forecasting problem centered around cinema audience attendance.

A machine learning project for predicting cinema audience counts using multi-source behavioral and temporal data.

## Project Overview

This project predicts daily audience counts for cinema theaters by leveraging booking patterns, theater characteristics, and temporal features. The solution combines data from online booking platforms and point-of-sale systems to create robust forecasting models.

## Problem Statement

Predict the daily audience count for cinema theaters using historical booking data, theater metadata, and temporal features. The task involves regression modeling to forecast continuous audience values based on multi-session behavioral patterns.

## Dataset Description

The project uses multiple data sources:

### Booking Data
- **booknow_visits.csv**: Historical audience counts per theater and date (214,046 records)
- **booknow_booking.csv**: Online booking transactions with timestamps (68,336 records)
- **cinePOS_booking.csv**: Point-of-sale ticket sales data (1,641,966 records)

### Theater Metadata
- **booknow_theaters.csv**: Theater information from online platform (829 theaters)
- **cinePOS_theaters.csv**: Theater information from POS system (4,690 theaters)
- **movie_theater_id_relation.csv**: Mapping between booking and POS theater IDs (150 mappings)

### Temporal Data
- **date_info.csv**: Calendar information with day of week (547 dates)
- **sample_submission.csv**: Submission format template (38,062 predictions)

### Key Features
- Session details: booking timestamps, show times
- Theater characteristics: type, area, geographic coordinates
- Temporal features: day of week, date patterns
- Booking behavior: advance booking time, ticket quantities

## Methodology

### Workflow
1. Data loading and initial exploration
2. Data cleaning and preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature engineering and selection
5. Model training and evaluation
6. Prediction generation
7. Results interpretation

### Feature Engineering
- Temporal features: day of week, month, date components
- Booking patterns: advance booking time, booking velocity
- Aggregated statistics: rolling averages, lag features
- Theater-level features: historical audience patterns
- Geographic features: location-based encodings

### Models Used
- XGBoost Regressor
- LightGBM Regressor
- Random Forest Regressor
- Ensemble methods

### Evaluation Metric
R² Score (Coefficient of Determination) - measures the proportion of variance in audience counts explained by the model.

## Requirements

### Python Libraries
numpy
pandas
matplotlib
seaborn
xgboost
lightgbm
scikit-learn
scipy
statsmodels


### Environment
- Python 3.8+
- Jupyter Notebook / Kaggle Notebooks
- Sufficient memory for processing 2M+ records



## Usage

### Data Preparation
Place all CSV files in the appropriate directory:
- For Kaggle: `/kaggle/input/Cinema_Audience_Forecasting_challenge/`
- For local execution: Update `BASE` path in the notebook

### Running the Notebook
The notebook automatically detects the environment
and loads data from the correct paths
Execute all cells sequentially or run:
jupyter nbconvert --execute notebook.ipynb


### Making Predictions
The notebook generates predictions in the required submission format:
- Predictions saved to `submission.csv`
- Format: `ID,audience_count`
- Ready for competition submission

## Project Structure

cinema-audience-forecasting/
├── README.md
├── requirements.txt
├── 22f3002869-notebook-t32025.ipynb
├── data/
│ ├── booknow_visits.csv
│ ├── booknow_booking.csv
│ ├── cinePOS_booking.csv
│ ├── booknow_theaters.csv
│ ├── cinePOS_theaters.csv
│ ├── movie_theater_id_relation.csv
│ ├── date_info.csv
│ └── sample_submission.csv
└── output/
└── submission.csv

## Key Insights

- Strong temporal patterns in audience behavior
- Theater location and type significantly impact attendance
- Advance booking patterns provide predictive signals
- Day of week is a crucial feature for forecasting
- Integration of online and offline booking data improves predictions

## Performance

The model achieves competitive R² scores on the validation set through:
- Comprehensive feature engineering
- Ensemble modeling approaches
- Cross-validation strategies
- Careful handling of temporal dependencies

## Competition Details

- Course: CS2008p (Machine Learning Practices Project)
- Program: BS in Data Science and Applications, IIT Madras
- Competition Link: https://www.kaggle.com/t/f36be8a7aee7492683e5b709ab8082eb

## Author

Sumit Kumar
- Roll Number: 22f3002869
- Email: 22f3002869@ds.study.iitm.ac.in

## Reproducibility

All experiments use fixed random seeds (SEED=42) for reproducibility. The notebook includes detailed documentation of:
- Library versions
- Model hyperparameters
- Data preprocessing steps
- Feature engineering logic

## License

This project is part of academic coursework for IIT Madras BS program.


- IIT Madras BS Program
- CS2008p Course Instructors
- Kaggle Competition Platform
