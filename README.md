# Heart_numeric_exploration

The dataset contains 1,025 entries and 14 columns. Here's a summary of its structure:

**Columns:**

age – Age of the patient

sex – Sex (1 = male; 0 = female)

cp – Chest pain type (0–3)

trestbps – Resting blood pressure (mm Hg)

chol – Serum cholesterol (mg/dl)

fbs – Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)

restecg – Resting ECG results (0–2)

thalach – Maximum heart rate achieved

exang – Exercise-induced angina (1 = yes; 0 = no)

oldpeak – ST depression induced by exercise relative to rest

slope – Slope of the peak exercise ST segment (0–2)

ca – Number of major vessels colored by fluoroscopy (0–4)

thal – Thalassemia (0 = normal; 1 = fixed defect; 2 = reversible defect; some versions use 1–3)

target – Target variable (1 = heart disease, 0 = no heart disease)

All columns are numeric, and there are no missing values.

**Interpretation of the data Exploration:**

1. Correlation Matrix
   
Insight:

The correlation matrix revealed that thalach (maximum heart rate) has a positive correlation with target (presence of heart disease), while oldpeak (ST depression) and exang (exercise-induced angina) have negative correlations. This implies that higher heart rate is associated with healthier patients, while stress indicators are linked to heart disease.

2. Cholesterol Levels vs. Heart Disease (t-test)
   
Result:
p-value: 0.0014 (significant)

Insight:

There is a statistically significant difference in cholesterol levels between those with and without heart disease. This suggests cholesterol plays a key role in cardiac risk, but it's not the only factor, as overlaps exist.

3. Sex and Heart Disease (Chi-Square Test)

Result:p-value: ~6.66e-19 (highly significant)

Insight:

Heart disease prevalence significantly differs by sex. The dataset indicates males are more likely to have heart disease, which aligns with known epidemiological trends.

4. Age vs. Max Heart Rate (Linear Regression)

Result:
Slope: -0.99

p-value: extremely low (1.27e-38)

Insight:

There's a strong inverse relationship between age and max heart rate — as age increases, heart rate capacity drops. This aligns with basic cardiovascular physiology.

5. Chest Pain Type vs. Heart Disease (ANOVA)

Result:

p-value: 1.25e-70 (extremely significant)

Insight:

Chest pain type is a very strong predictor of heart disease. Patients with cp=3 (asymptomatic) are far more likely to have heart disease than those with typical angina or no pain.

6. Resting Blood Pressure vs. Cholesterol (Correlation)

Result:

Correlation: 0.13

p-value: 3.97e-05

Insight:

There’s a weak but statistically significant positive correlation between resting blood pressure and cholesterol. Although related, this link isn’t strong enough for prediction by itself.

7. Number of Colored Vessels vs. Heart Disease (ANOVA)

Result:

p-value: 1.23e-62 (highly significant)

Insight:

The number of major vessels visualized (ca) is strongly associated with heart disease. Fewer visualized vessels often correspond to abnormal or blocked arteries, reinforcing diagnostic value.

**Visualization insights:**

1. Heatmap of Correlation Matrix

📊 What it shows:
This heatmap visualizes how strongly features are correlated (both positively and negatively).

🔍 Insights:

thalach (maximum heart rate) has a positive correlation with target (presence of heart disease), meaning healthier individuals tend to reach higher heart rates.

oldpeak, exang, and ca have negative correlations with target, meaning those with heart disease tend to have higher stress test abnormalities and more blocked vessels.

Helps detect multicollinearity and guides feature selection for machine learning.

2. Heart Disease Count by Sex

📊 What it shows:
A grouped bar chart comparing how many males and females have or don’t have heart disease.

🔍 Insights:

A greater number of males in the dataset have heart disease compared to females.

This supports the statistical findings that sex is a significant risk factor.

It also highlights the gender imbalance in the dataset, which might need attention in model training.

3. Boxplot of Cholesterol Levels by Heart Disease

📊 What it shows:
This boxplot compares the distribution of cholesterol for people with and without heart disease.

🔍 Insights:

Individuals without heart disease have a wider spread and more outliers with very high cholesterol.

Surprisingly, median cholesterol levels don’t drastically differ, suggesting cholesterol alone may not be a strong standalone predictor.

Useful for identifying skewness and outlier behavior.

4. Pairplot of Key Features

📊 What it shows:
Pairwise scatter plots between selected features (age, trestbps, chol, thalach) colored by heart disease status.

🔍 Insights:

Reveals patterns, clusters, and separability of features by target.

thalach and oldpeak clearly show separation between the two classes.

This helps visualize how well features might perform in a classification model.

5. Distribution of Max Heart Rate by Heart Disease

📊 What it shows:
Histogram with KDE (smoothed curve) comparing thalach distributions by target.

🔍 Insights:

People with heart disease tend to have lower maximum heart rates.

Those without heart disease peak at higher thalach values.

This supports the physiological notion that healthy individuals can sustain higher cardiac effort.
