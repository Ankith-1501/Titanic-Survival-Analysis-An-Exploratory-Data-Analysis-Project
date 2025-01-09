# **Titanic Survival Analysis: An Exploratory Data Analysis Project**

## **Project Overview**
The Titanic dataset provides information on the passengers of the RMS Titanic, focusing on their survival status along with other attributes such as age, sex, passenger class, fare, and family details. The goal of this project is to analyze survival patterns and relationships between features through Exploratory Data Analysis (EDA).

### **Key Objectives**
- Understand the factors influencing passenger survival.
- Identify patterns, trends, and anomalies in the data.
- Use statistical analysis to validate insights.

---

## **Data Cleaning**

1. **Missing Values**:
   - `Age`: Filled with the median value to handle missing entries.
   - `Embarked`: Filled with the most frequent value ('S').
   - `Cabin`: Dropped due to excessive missing data.

2. **Duplicates**:
   - Checked for duplicate rows. No duplicates were found.

### **Code Example**:
```python
# Handle missing values
df['Age'].fillna(df['Age'].median(), inplace=True)
df['Embarked'].fillna(df['Embarked'].mode()[0], inplace=True)
df.drop(columns=['Cabin'], inplace=True)
```

---

## **Feature Engineering**

1. **Family Size**:
   - Created a new feature, `FamilySize`, as the sum of `SibSp` and `Parch`.
2. **Age Category**:
   - Grouped passengers into categories: Child (<18), Adult (18-60), and Senior (>60).
3. **Title Extraction**:
   - Extracted titles (e.g., Mr., Mrs., Miss.) from passenger names.

### **Code Example**:
```python
# Feature engineering
df['FamilySize'] = df['SibSp'] + df['Parch']

def age_category(age):
    if age < 18:
        return 'Child'
    elif 18 <= age <= 60:
        return 'Adult'
    else:
        return 'Senior'

df['AgeCategory'] = df['Age'].apply(age_category)
df['Title'] = df['Name'].apply(lambda x: x.split(',')[1].split('.')[0].strip())
```

---

## **Exploratory Data Analysis (EDA)**

### **1. Univariate Analysis**
- **Age Distribution**: Most passengers were adults, with fewer children and seniors.
- **Fare Distribution**: Fare was heavily skewed, with outliers representing higher-class passengers.

#### **Visuals**:
```python
sns.histplot(df['Age'], kde=True)
sns.histplot(df['Fare'], kde=True)
```

---

### **2. Bivariate Analysis**
- **Survival by Class**:
  - First-class passengers had the highest survival rates, while third-class had the lowest.
- **Survival by Sex**:
  - Female passengers had significantly higher survival rates than males.

#### **Visuals**:
```python
sns.countplot(x='Pclass', hue='Survived', data=df)
sns.countplot(x='Sex', hue='Survived', data=df)
```

---

### **3. Correlation Analysis**
- Strong negative correlation between `Fare` and `Pclass` (higher-class passengers paid more).
- Moderate positive correlation between `Fare` and survival.

#### **Visual**:
```python
sns.heatmap(corr, annot=True, cmap='coolwarm', fmt='.2f')
```

---

### **4. Advanced Visualizations**
- **Violin Plot**: Visualized age distribution by survival and class, showing that children in first and second class had the highest survival rates.
- **Stacked Bar Plot**: Revealed the proportion of survivors across different classes.

---

## **Statistical Analysis**

1. **Chi-Square Test**:
   - Tested the relationship between `Sex` and `Survived`.
   - **Result**: Significant relationship (p-value < 0.05).
   - The test indicates that survival significantly depends on the gender of the passenger.

   ```python
   contingency_table = pd.crosstab(df['Survived'], df['Sex'])
   chi2, p, dof, expected = chi2_contingency(contingency_table)
   print(f'Chi-Square Statistic: {chi2}, P-value: {p}')
   ```
   - **Chi-Square Statistic**: `260.717`
   - **P-value**: `1.1973570627755645e-58`

2. **T-Test**:
   - Compared the average age of survivors and non-survivors.
   - **Result**: The difference in average age is not statistically significant (p-value > 0.05).

   ```python
   t_stat, p_value = ttest_ind(survived, non_survived)
   print(f'T-statistic: {t_stat}, P-value: {p_value}')
   ```
   - **T-statistic**: `-1.939`
   - **P-value**: `0.05276`

---

## **Key Insights**

1. **Gender**:
   - Female passengers had a survival rate of ~74%, compared to ~19% for males. This reflects the "women and children first" policy.

2. **Class**:
   - First-class passengers had the highest survival rate (~63%), while third-class passengers had the lowest (~24%).

3. **Age**:
   - Children (<18) had a higher survival rate (~59%) compared to adults and seniors.

4. **Family Size**:
   - Passengers with family members aboard were more likely to survive than those traveling alone.

5. **Fare**:
   - Higher fares were associated with better survival chances, indicating socio-economic influence.

---

## **Conclusion**

This analysis reveals how socio-economic status, gender, and age influenced survival aboard the Titanic. These findings align with historical accounts of the disaster.

---

## **Future Work**
1. **Feature Refinement**:
   - Analyze the impact of extracted titles and port of embarkation.
2. **Predictive Modeling**:
   - Use machine learning to predict survival based on engineered features.
3. **Additional Analysis**:
   - Examine other variables, such as group sizes or ticket sharing, for deeper insights.

