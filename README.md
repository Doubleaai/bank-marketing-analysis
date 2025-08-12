# Bank Marketing Analysis  

Bank Marketing Analysis is a comprehensive data analysis and prediction tool aimed at understanding customer behaviour and improving the success rate of term deposit marketing campaigns. The project uses Python for data preparation, statistical analysis, visualisation, and machine learning.  

---

## Dataset Content  

- **Rows:** ~45,000 records  
- **Columns:** 17 features including `age`, `job`, `marital`, `education`, `contact`, and `duration`.  
- **Data source:** UCI Machine Learning Repository – Bank Marketing Dataset (`bank.csv`).  

---

## Business Requirements  

The business goal is to:  
1. Identify customer segments most likely to subscribe to a term deposit.  
2. Provide insights into the most effective marketing channels.  
3. Build a predictive model to support targeted marketing strategies.  

---

## Hypotheses and Validation  

- **H1:** Job type and term deposit subscription are dependent.  
- **H2:** Age group and term deposit subscription are dependent.  
- **H3:** Contact method and term deposit subscription are dependent.  
- **H4:** Housing loan status and term deposit subscription are dependent.  

**Validation Method:**  
Chi-square tests of independence on the feature-engineered dataset, supported by visualisations.  

---

## Project Plan  

1. **ETL** – Load, clean, and preprocess `bank.csv`.  
2. **Feature Engineering** – Create new columns (e.g., `age_band`, `has_any_loan`, `was_previously_contacted`) and save both feature-engineered and ML-ready datasets.  
3. **EDA** – Explore data patterns and relationships using visualisations.  
4. **Hypothesis Testing** – Statistically validate observed EDA relationships.  
5. **Machine Learning** – Train and evaluate models for prediction.  
6. **Dashboard** – Build an interactive Tableau/Streamlit dashboard for insights.  

---

## Mapping Business Requirements to Data Visualisations  

- **Target customer segments** → Bar plots showing subscription rates by job, and a line graph showing subscription rate trends by age group.  
- **Best marketing channels** → Pie charts comparing contact method effectiveness.  
- **Predictive modelling** → Feature importance plots after model training.  

---

## Analysis Summary  

Exploratory Data Analysis revealed clear patterns:  
- **Retired** and **student** customers subscribed at much higher rates.  
- **Middle-aged and older** customers subscribed more than younger ones.  
- **Cellular contact** outperformed telephone outreach.  

Chi-square testing confirmed significant associations (p < 0.05) for all hypotheses.  

**Recommendations:**  
- Target high-performing job and age segments.  
- Prioritise cellular contact methods.  
- Explore investment opportunities with customers without housing loans.  

**References:**  
- OpenAI. (2025). *ChatGPT*. https://chat.openai.com  
- GitHub. (2025). *GitHub Copilot*. https://github.com/features/copilot  

---

## Analysis Techniques Used  

- **EDA:** Pandas, Matplotlib, Seaborn  
- **Statistical Testing:** Chi-square tests with SciPy  
- **Machine Learning:** Logistic Regression, Random Forest, XGBoost  

---

**Limitations:**  
Some features are campaign-specific and may not generalise to future marketing efforts. Certain variables (e.g., `duration`) may require exclusion for prediction as they are only known after contact.  

---

## Machine Learning  

I initially implemented a Logistic Regression model during my feature engineering stage to create a baseline for predicting whether a customer would subscribe to a term deposit. While this provided interpretable results, I wanted to explore more advanced algorithms to see if predictive performance could be improved.  

For this, I trained and evaluated two additional supervised learning models:  

### 1. Random Forest Classifier  
The Random Forest model was chosen for its ability to handle mixed data types, capture non-linear relationships, and provide feature importance scores. It performed reliably, producing balanced precision and recall values, and highlighted that previous contact history, month of contact, and specific job categories were among the most influential predictors.  

### 2. XGBoost Classifier  
I also implemented XGBoost, a gradient boosting algorithm known for strong performance on structured/tabular data. After cleaning my column names for compatibility, XGBoost achieved slightly higher recall on the positive class compared to Random Forest, making it particularly useful for identifying potential subscribers. Like Random Forest, it confirmed the importance of features such as previous outcome, call intensity, and age bands.  

**Evaluation and Insights:**  
Both models were evaluated using accuracy, precision, recall, F1-score, and confusion matrices.  

- **Random Forest:** Balanced predictions with clear interpretability of top features.  
- **XGBoost:** Slightly better recall, valuable in marketing scenarios where identifying potential subscribers is more important than avoiding false positives.  

Feature importance analysis from both models will directly inform my dashboard recommendations, helping stakeholders focus on the most influential customer attributes.  

---

## Ethical Considerations  

- No personally identifiable information (PII) is present.  
- Bias awareness: Job, age, and education-based targeting could unintentionally cause discrimination. Recommendations will be reviewed for fairness.  

---
## Dashboard Access  

The interactive Tableau dashboard for this project is available here: [View Dashboard](YOUR_TABLEAU_LINK_HERE)

It contains:  
- Overview of subscription rate trends and customer segmentation  
- Demographics breakdown by job, age_band, and marital status  
- Contact method effectiveness (cellular vs telephone)  
- Predictive modelling results integrated into a visual interface

## Dashboard Design  

**Pages:**  
1. **Overview** – Subscription rate trends and customer segmentation.  
2. **Demographics** – Visualisation by job, age_band, and marital status.  
3. **Contact Method** – Effectiveness of cellular vs telephone.  
4. **Prediction Tool** – Input fields for model prediction.  

---

## User Personas and Dashboard Mapping  

To ensure the dashboard addresses the needs of different stakeholders, I have identified three key personas and mapped their goals to specific Tableau visuals.  

### 1. Sarah Thompson — Marketing Manager  
Responsible for overseeing the bank’s retail marketing campaigns and allocating budgets to the most effective channels. Needs quick, clear insights on customer groups and outreach methods.  

**Relevant Visuals:**  
- Subscription Rates by Job Type (**Horizontal Bar Chart**)  
- Contact Method Success Rate (**Pie Chart**)  

### 2. David Khan — Product Manager (Savings & Investments)  
Designs and manages term deposit products with the aim of increasing uptake and tailoring features to customer needs.  

**Relevant Visuals:**  
- Subscription Rates by Age Group (**Line Graph**)  
- Housing Loan Status vs. Subscription Rate (**Heat Map**)  

### 3. Priya Desai — Data Analyst  
Supports decision-making by providing in-depth analysis of customer and campaign data. Needs detailed, accurate visuals to validate statistical findings and create internal reports.  

**Relevant Visuals:**  
- Combined Tableau Dashboard with Interactive Filters  

---

## Agile User Stories (Linked to Tableau Visual Types)  

- As a **Marketing Manager**, I want to view subscription rates by job type (**Horizontal Bar Chart**) and contact method success rates (**Pie Chart**), so that I can focus my marketing budget on the most responsive customer groups and channels.  
- As a **Product Manager**, I want to view subscription rates by age group (**Stacked Column Chart**) and housing loan status vs. subscription rate (**Heat Map**), so that I can design tailored term deposit products and cross-sell to the right customers.  
- As a **Data Analyst**, I want access to all four visuals in a Tableau Dashboard with interactive filters, so that I can validate statistical findings and generate detailed reports for stakeholders.  

---
### Limitations
While the dashboard offers interactive filtering and drill-down features, performance issues were encountered during development. When multiple filter actions were applied across several large worksheets simultaneously, Tableau occasionally became unresponsive or crashed. This is likely due to the size of the dataset and the processing load from applying multiple cross-sheet filters at once. To maintain stability, the final dashboard uses a simplified set of filter actions, balancing interactivity with performance.

---

## How Were Data Insights Communicated  

Plots and statistical summaries were designed to be understandable for both technical and non-technical stakeholders, pairing visual results with plain language interpretations.  

---
### Bugs & Fixes  

During development, several technical issues were identified and resolved. Some numeric columns, such as `age` and `balance`, were incorrectly loaded as strings due to automatic type inference during CSV import, which was fixed by explicitly converting them using `pd.to_numeric()` and `.astype()`. Categorical columns like `job` contained inconsistent capitalisation (e.g., "management" vs "Management"), which was resolved by converting all text values to lowercase for consistency. Visualisations initially failed to render correctly in Jupyter Notebook due to missing `%matplotlib inline` and inadequate figure sizing, both of which were addressed to improve clarity and readability. Finally, Logistic Regression training failed at first because string-based categorical variables were present in the dataset, which was corrected by applying one-hot encoding with `pd.get_dummies()` to ensure all model inputs were numeric.

---

## Unfixed Bugs  

No current unfixed bugs. All scripts run successfully in Jupyter Notebook.  

---

## Development Roadmap  

- Finalise Logistic Regression model and evaluate accuracy.  
- Build Streamlit dashboard for interactive exploration.  
- Deploy project online.  

---

## Deployment  

- Deployment will be on GitHub for notebooks and datasets.  
- The dashboard will be deployed via Heroku once complete.  

---

## Main Data Analysis Libraries  

- Pandas – Data cleaning and manipulation  
- Matplotlib / Seaborn – Visualisations  
- SciPy – Statistical testing (Chi-square)  
- Scikit-learn – Machine learning models  
- XGBoost – Gradient boosting  

---

## Credits  

**Content:**  
- Dataset from UCI Machine Learning Repository  
- Statistical methods inspired by SciPy documentation  
- Visualisation styling guided by Seaborn examples  

**Media:**  
- No external media used  

**Acknowledgements:**  
- Special thanks to ChatGPT (OpenAI, 2025) and GitHub Copilot (GitHub, 2025) for assisting in ideation, design thinking, and code optimisation  