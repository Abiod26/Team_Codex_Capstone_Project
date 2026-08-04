# Crop Yield Prediction Using Machine Learning
## Capstone Project – Team Codex
This repository contains our capstone project on crop yield prediction using machine learning. The project explores how environmental and agricultural factors influence crop yield and evaluates different regression models to identify the most suitable approach for prediction. The work covers the complete data science process, including data preparation, exploratory data analysis, model development, evaluation, and interpretation of results.

## Project Overview
Crop yield prediction is important for improving agricultural planning and reducing uncertainty in food production. By analysing historical agricultural data, this project identifies the key factors associated with crop yield and develops predictive models that can assist farmers and support agricultural planning.

The main objectives of this project were to:
- Explore and understand the dataset through exploratory data analysis (EDA).
- Identify the variables that have the greatest influence on crop yield.
- Build and evaluate regression models for crop yield prediction.
- Compare the performance of different machine learning models.
- Interpret the results and discuss their practical applications for farmers and policymakers.

## Dataset
**Source:** Kaggle – Crop Yield Prediction Dataset
The dataset contains historical crop production records collected from multiple countries over several years. It includes both environmental and agricultural variables used to predict crop yield.

### Dataset Summary
- Total records: **28,242**
- Records after cleaning: **25,932**
- Countries: **101**
- Crop types: **10**
- Years covered: **1990–2013**

### Variables
| Variable | Description |
|----------|-------------|
| Area | Country |
| Item | Crop type |
| Year | Production year |
| average_rain_fall_mm_per_year | Annual rainfall |
| pesticides_tonnes | Pesticide usage |
| avg_temp | Average temperature |
| hg/ha_yield | Crop yield (Target variable) |

## Data Preparation
Before building the models, the dataset was cleaned and prepared for analysis. The following steps were carried out:
- Removed the unnecessary index column (`Unnamed: 0`)
- Removed 2,310 duplicate records
- Checked for missing values (none were found)
- Examined outliers using the IQR method
- Retained genuine agricultural outliers because they represented real crop variations rather than errors
- Reset the dataframe index after cleaning
  
The final dataset contained **25,932 observations** with no missing values and was ready for analysis.

## Exploratory Data Analysis
The exploratory analysis highlighted several important findings:
- Crop yield has a strongly right-skewed distribution.
- Crop type is one of the strongest factors associated with yield.
- Geographic location also plays a major role in yield differences.
- Rainfall, temperature, and pesticide usage show relatively weak individual linear relationships with crop yield.
- The numerical variables exhibit low multicollinearity, making them suitable for predictive modelling.

These observations suggested that tree-based machine learning models would likely perform better than traditional linear regression.

## Machine Learning Models
Three regression models were developed and compared:
- Linear Regression
- Random Forest Regressor
- XGBoost Regressor

To improve model performance and reliability, the following techniques were also applied:
- One-Hot Encoding
- Train-Test Split (80:20)
- Hyperparameter Tuning using RandomizedSearchCV
- Five-Fold Cross-Validation
- Feature Importance Analysis
- Partial Dependence Plots
- Prediction Uncertainty Analysis

## Model Performance
| Model | R² | RMSE | MAE |
|------|------:|------:|------:|
| Random Forest (Tuned) | **0.985** | **10,522** | **3,963** |
| XGBoost | 0.943 | 20,399 | 12,146 |
| Linear Regression | 0.749 | 42,682 | 29,921 |

Among the models evaluated, the tuned Random Forest Regressor produced the best overall performance and was selected as the final prediction model.

## Key Findings
The project produced the following key findings:
- Crop type was the strongest predictor of crop yield.
- Geographic location had the second greatest influence.
- Pesticide usage contributed more to prediction than rainfall and temperature.
- Random Forest consistently outperformed both Linear Regression and XGBoost.
- Machine learning can provide useful insights for agricultural planning and decision-making.

## Practical Applications
### Farmers
The model can support farmers by helping them:
- Estimate expected crop yield before harvest.
- Make better decisions on fertilizer and pesticide use.
- Plan harvesting, storage, and marketing activities.
- Assess production risks before investing additional resources.

### Policymakers
The findings can also support policymakers through:
- Improved food security planning.
- Better allocation of agricultural resources.
- Early identification of potential production shortfalls.
- Evidence-based agricultural policy development.

## Repository Structure
```text
├── Team Codex Capstone Project Notebook.ipynb
├── yield_df.csv
├── Team Codex.pptx
├── README.md
└── requirements.txt

## Running the Project
Clone the repository:
```bash
git clone https://github.com/Abiod26/Abiod26/Team_Codex_Capstone_Project.git
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:
```bash
jupyter notebook
```
Open the notebook named:
```
Team Codex Capstone Project Notebook.ipynb
```
Run the notebook from the first cell to the last.

## Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

## Team
**Team Codex**
Machine Learning Capstone Project (2026)

## Acknowledgements
We appreciate Kaggle for making the dataset publicly available. We also acknowledge the guidance and support provided by our instructors and mentors throughout the capstone project.
---## License

Ths project was completed as part of a machine learning capstone programme and is intended for educational purposes.
