Presentation Schedule
1. Data Overview (No Pre Processing)
    - London Accidents
    - Divided in 3 main severities
    - Categorized by vehichle type, borough, age range

2. Goal of the project
    - Main intentions
    - main ways of approaching the problem

3. Pre Processing
    - Main goals for data preprocessing
    - Data analysis and Review
    - Normalization and Encoding
    - Categorizing and grouping by ranges

4. Further Feature Analysis
    - Determining purpose
        - Analysis of causation rather than aftermath
        - Feature Cleanup

5. Model Training
    - XGBoost (Default Vals)
        - Understanding inbalance of severities
    - XGBoost (Sample Weights)
        - ADASYN as a support to class imbalance with Sample Weights
    
6. Restructure data
    - Review importance of borough Encoding
    - Explore different types of Encoding
    - Risk Level Encoding
    - Encode and cleanup Dataset

7. Finalize Analysis
    - Re run analysis of XGBoost (Sample Weights) with new Risk encoded Dataset
    - Further analyse using SHAP
        - Understand SHAP
        - SHAP by category

8. Future enhancements
    - Based on initial discovery
    - Based on final discovery.