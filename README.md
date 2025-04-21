# RetentionProject

## Problem

- How can we extract useful insights to improve a healthcare company's client retention rate from a dataset filled with various attributes?
- A synthetic dataset was used to preserve privacy while testing the ability to extract valuable insights, ensuring ethical standards were met.

## Methodology

1. **Dataset Selection**  
   Explored healthcare.gov and attempted to use their API, but found it unfit for this purpose. Switched to a synthetic dataset from Kaggle with 8000 rows and 60 columns, then downloaded it as CSV.

2. **SQL Integration**  
   Imported CSV into MySQL. Fixed column formatting errors. Used `LOAD DATA INFILE` for reliable imports. Cleaned and filtered the dataset in SQL before importing to Python.

3. **Data Preparation in Python**  
   - Loaded cleaned SQL data into Python using SQLAlchemy and dotenv.
   - Converted objects and booleans into integers for model readiness.
   - Dropped irrelevant or inconsistent columns.

4. **Train/Test Split**  
   Used `train_test_split()` with 80% training and 20% testing data. Retention column used as the target (`y`), remaining as features (`X`).

5. **Model Building**  
   - Used TensorFlow’s Sequential API.  
   - Activation functions: `relu` for hidden layers, `sigmoid` for output.  
   - Loss function: `binary_crossentropy`.  
   - Optimizer: `adam`. Accuracy used for metric tracking.

6. **Training and Evaluation**  
   - Trained the model for 30 epochs.
   - Achieved 84% accuracy.  
   - Noted the average predicted retention probability was 50%.

7. **Linear Regression Comparison**  
   - Built a regression model for interpretability.  
   - Found that clients in Washington D.C. had the lowest churn rate.

8. **Visualization (Tableau)**  
   - Imported results and created visual dashboards.
   - Highlighted states patterns, age group trends, and retention features.

9. **Insights and Recommendations**  
   - Clients around the age 64, living in Washington D.C., with specific coverage types were more likely to stay.
   - Identified average values and characteristics of top 10 retained clients.
   - Findings can guide strategic retention planning in healthcare firms.

---

### Tools Used

- **SQL** (MySQL Workbench)
- **Python** (Pandas, Scikit-learn, TensorFlow)
- **Jupyter Notebook**
- **Tableau** (for visualization)

