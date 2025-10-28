# Lung Cancer Risk Prediction

This project develops and evaluates predictive models for lung cancer risk based on a large, imbalanced real-world dataset. 
The core focus is on data engineering, advanced sampling techniques, and robust model evaluation to achieve reliable prediction of the minority (cancer) class.

### Goal & Key Achievements

The primary goal was to create a highly accurate and unbiased model for lung cancer risk prediction by overcoming the common challenge of class imbalance (original ratio was 80:20).

- Model Performance: Achieved a peak *0.97* accuracy and a *0.97* macro F1-score (Random Forest) by utilizing Stratified Equal Sampling.
- Imbalance Resolution: Validated the effectiveness of SMOTE and Stratified Sampling to ensure models reliably predict the minority class, showcasing performance using the macro F1-score.
- Feature Analysis: Identified and confirmed the most critical predictors across all models: Mortality Risk (**~17%**), 5-Year Survival Probability (**~17%**), and Age (**~13%**).
- Methodology Deep Dive: Compared four distinct classification algorithms (Decision Tree, Random Forest, XGBoost, Neural Network) under four different sampling scenarios.

### Methodology & Techniques

- Data Preprocessing & Cleaning:
    -  Feature Engineering: Converted 20+ categorical features (e.g., Country, Smoking Status, Socioeconomic Status) to the category dtype and performed Label Encoding for model input.
    -  Missing Data Handling: Tested two robust strategies:
        - Population 1 (Row Removal): Dropping rows containing null values in Mutation_Type and Treatment_Access.
        - Population 2 (Column Removal): Dropping the two columns entirely.
     
    - Feature Analysis: Used the Chi-Square test to confirm dependency between categorical variables prior to modeling.

- Sampling Techniques:
  - The core of this project involved comparing model performance across four sampling strategies:
  - Random Sampling (Baseline)
  - Random Sampling with Replacement (Weighted)
  - Stratified Equal Sampling: Used to generate a perfectly balanced 1:1 class distribution.
  - SMOTE (Synthetic Minority Over-sampling Technique): Used to generate synthetic minority class samples, improving generalized performance.

- Modeling Algorithms:
  - Decision Tree:	Feature selection and baseline tree-based performance.
  - Random Forest:	Ensemble Bagging, testing performance with different sampling techniques.
  - XGBoost:	Ensemble Boosting, hypothesis testing on residual-based training under imbalance.
  - Neural Network (Keras):	Testing optimization-based deep learning performance on sampled datasets.

### Technologies
 - Python 3.x
 - Core Libraries: pandas, NumPy, matplotlib, scipy
 - Machine Learning: scikit-learn (Decision Tree, Random Forest, Evaluation Metrics)
 - Deep Learning: TensorFlow/Keras (Neural Networks, Adam Optimizer)
 - Sampling: imbalanced-learn (SMOTE)
 - Boosting: XGBoost
