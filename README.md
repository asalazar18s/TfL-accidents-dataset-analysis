# AI in Industry – City of London Accidents: Causal Analysis

This project investigates the causes that determine the **severity of road accidents** in the Greater City of London using machine learning techniques and a dataset from Transport for London (TfL).

## Dataset

- Source: [TfL Open Data](https://api.tfl.gov.uk)
- Year: 2019
- Features: `id`, `Latitude`, `Longitude`, `Location`, `Date`, `Severity`, `Borough`, `Casualties`, `Vehicles`

## Project Goal

Identify and analyze the key **factors influencing accident severity** using:
1. Data preprocessing
2. Exploratory feature analysis
3. Classification modeling (target: Severity)
4. Feature importance evaluation
5. SHAP interpretability

## ⚙️ Preprocessing

- Removed: Unused features like `Location`
- Added: Derived features like `Time_of_Day` and `Month`
- Encoding:
  - Categorical: One-Hot-Encoding (e.g., `Borough`, `Time_of_Day`)
  - Ordinal: Mapped `Severity`, `Day_of_the_week`, and `Month`
- Removed: Outcome-focused features (e.g., `Vehicles`, `Casualties`)

## Model

- Algorithm: **XGBoost** (Gradient Boosting)
- Trials:
  - Baseline XGBoost
  - XGBoost + Sample Weights
  - XGBoost + Sample Weights + ADASYN + GridSearch (best model)
- Evaluation:
  - Classification report
  - AUC score
  - Feature and Permutation importance

### Best Model
- **AUC Score**: 0.92
- **Hyperparameters**: `learning_rate=0.3`, `max_depth=25`, `subsample=0.8`

## Risk Level Re-categorization

- Borough-level risk score introduced:
  - `risk_score = 0.3 * total_accidents + 0.7 * avg_severity`
- Replaced one-hot boroughs with ordinal `risk_level_encoded`

## SHAP Analysis

Used SHAP to interpret model decisions:
- Most influential: `Location` and `Time_of_Day` (especially afternoons)
- Provided granular view of how features impact predictions

## Conclusions

- The model effectively captures spatial and temporal accident patterns
- Borough features less impactful in one-hot form; risk-level encoding improved interpretability

## Future Work

- Refine risk level encoding to better balance severity and accident count
- Generate geospatial heatmaps of accident risk across London

---

**Authors**: Federico Faccioli, Aaron Stephan Salazar Jaramillo, Mohammed Oubia  
**Presentation**: "AI in Industry – City of London Accidents Causal Analysis"
