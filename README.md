# 🚢 Titanic Survival Analysis
This project performs data cleaning and exploratory data analysis (EDA) on the Titanic dataset to visualize survival patterns based on demographic and travel-related features such as gender, passenger class, and age.

## 📁 Dataset
The dataset is the Titanic training set from the Kaggle Titanic competition, stored as:

```bash
train[1].csv
```

## 🧰 Libraries Used
**Pandas** – for data loading and manipulation

**Seaborn** – for advanced data visualization

**Matplotlib** – for customizing and displaying plots

## 📊 Workflow Summary
### **1. Load the Dataset**
```python
df = pd.read_csv('train[1].csv')
```
Initial data exploration with `.head()` and `.info()` to understand structure and data types.

### **2. Data Cleaning**

**Age:** Missing values are filled with the median age.

**Cabin:** The column is dropped due to too many missing values.

**Embarked:** Missing values are filled with the most frequent value (mode).

```python
df['Age'] = df['Age'].fillna(df['Age'].median())
df.drop('Cabin', axis=1, inplace=True)
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])
```

### **3. Exploratory Data Analysis (EDA)**

Visualizations are generated to explore relationships between features and survival rate.

**📌 Survival Rate by Sex**

Shows how male and female passengers had different survival probabilities.

**📌 Survival Rate by Passenger Class (Pclass)**

Explores how class (1st, 2nd, 3rd) influenced survival chances.

**📌 Age Distribution of Passengers**

Displays the overall age distribution with KDE overlay.

**📌 Age Distribution by Survival Status**

Box plot showing how age varied between those who survived and those who didn't.

## 🖼️ Example Plots
Plots are displayed using `plt.show()` after each visualization for clear output. All visualizations use seaborn for aesthetics and consistent styling.
