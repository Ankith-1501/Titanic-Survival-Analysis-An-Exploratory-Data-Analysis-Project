# Titanic Survival Analysis: An Exploratory Data Analysis Project

## Overview
This project explores survival patterns aboard the RMS Titanic using the Titanic dataset. The analysis aims to uncover factors influencing survival rates through data cleaning, feature engineering, statistical testing, and data visualization. The insights gained align with historical accounts and provide a deeper understanding of the disaster.

---

## Objectives
- Perform data cleaning to handle missing values and prepare the dataset for analysis.
- Engineer features to enhance the dataset's predictive value.
- Conduct Exploratory Data Analysis (EDA) to identify survival patterns and trends.
- Validate relationships between variables using statistical testing.

---

## Dataset
The dataset contains information about Titanic passengers, including:
- **Survived**: Survival status (1 = survived, 0 = not survived).
- **Pclass**: Passenger class (1st, 2nd, 3rd).
- **Name**: Name of the passenger.
- **Sex**: Gender of the passenger.
- **Age**: Age of the passenger.
- **SibSp**: Number of siblings/spouses aboard.
- **Parch**: Number of parents/children aboard.
- **Fare**: Ticket fare paid.
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).

Dataset Source: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic/data)

---

## Key Steps

### 1. Data Cleaning
- Filled missing values for `Age` (median) and `Embarked` (mode).
- Dropped the `Cabin` column due to excessive missing values.
- Ensured no duplicate rows were present.

### 2. Feature Engineering
- **FamilySize**: Sum of `SibSp` and `Parch` to represent family size.
- **AgeCategory**: Grouped `Age` into categories (Child, Adult, Senior).
- **Title**: Extracted titles (e.g., Mr., Mrs., Miss) from passenger names.

### 3. Exploratory Data Analysis (EDA)
- Univariate Analysis: Analyzed distributions of age and fare.
- Bivariate Analysis: Explored survival rates by gender, class, and other features.
- Advanced Visualizations: Used violin plots, stacked bar charts, and heatmaps for deeper insights.

### 4. Statistical Analysis
- **Chi-Square Test**:
  - Tested the relationship between `Sex` and `Survived`.
  - **Result**: Significant relationship (p-value < 0.05).
- **T-Test**:
  - Compared the mean age of survivors and non-survivors.
  - **Result**: No significant difference (p-value > 0.05).

---

## Key Findings
1. **Gender**: Female passengers had a significantly higher survival rate (~74%) compared to males (~19%).
2. **Class**: First-class passengers had the highest survival rate (~63%), while third-class passengers had the lowest (~24%).
3. **Age**: Children (<18) had higher survival rates (~59%) compared to adults and seniors.
4. **Family Size**: Passengers with family members aboard were more likely to survive than those traveling alone.
5. **Fare**: Higher ticket fares were associated with better survival chances, reflecting socio-economic influences.

---

## Visualizations
- **Age Distribution**: Histogram showing the spread of passenger ages.
- **Survival by Class**: Count plot comparing survival across passenger classes.
- **Survival by Gender**: Count plot highlighting the survival rate disparity between males and females.
- **Correlation Heatmap**: Revealed relationships between numerical features.

---

## Future Work
1. **Feature Refinement**:
   - Analyze additional features such as ticket numbers and cabin allocations.
2. **Predictive Modeling**:
   - Train machine learning models to predict survival using the engineered dataset.
3. **Deeper Analysis**:
   - Examine group dynamics, such as ticket sharing, and their impact on survival.

---

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/titanic-survival-analysis.git
   ```
2. Open the project notebook in Google Colab or Jupyter Notebook.
3. Install required libraries:
   ```bash
   pip install pandas numpy seaborn matplotlib
   ```
4. Run each code cell sequentially to reproduce the analysis and visualizations.

---

## Contributions
Feel free to contribute to this project by submitting issues or pull requests. Suggestions for new analyses or visualizations are always welcome!


