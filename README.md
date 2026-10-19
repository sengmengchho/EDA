# 📊 Exploratory Data Analysis (EDA) Learning Roadmap

This roadmap is designed to help you learn **Exploratory Data Analysis (EDA)** from **basic to advanced level** in 4 weeks.

The goal is not only to memorize Pandas or visualization commands, but to learn how to:

- Understand a dataset
- Check data quality
- Explore distributions
- Find relationships between variables
- Detect outliers and unusual patterns
- Use statistics to support conclusions
- Prepare data for machine learning

---

# 🎯 Main Learning Path

```text
Understand Data
      ↓
Clean Data
      ↓
Explore One Variable
      ↓
Explore Relationships
      ↓
Detect Problems
      ↓
Discover Patterns
      ↓
Form Conclusions
      ↓
Prepare for Modeling
```

---

# 🗓️ 4-Week EDA Timetable

## Week 1 — EDA Fundamentals 🟢

**Goal:** Understand datasets, Pandas, data types, and basic data cleaning.

| Day | Topic | Practice |
|---|---|---|
| Day 1 | What is EDA? | Load a CSV and understand rows and columns |
| Day 2 | Pandas Basics | `head()`, `tail()`, `shape`, `columns`, `info()` |
| Day 3 | Data Types | Numeric, categorical, datetime, text, ID |
| Day 4 | Descriptive Statistics | `describe()`, mean, median, min, max, std |
| Day 5 | Missing Values | `isnull()`, missing percentage, handling missing data |
| Day 6 | Duplicates & Invalid Values | `duplicated()`, `drop_duplicates()`, validation |
| Day 7 | Review | Repeat everything using a new dataset |

### Example

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.head())
print(df.shape)
print(df.columns)
print(df.info())
```

### By the end of Week 1, you should be able to answer:

- What is this dataset about?
- How many rows and columns does it have?
- What are the variables?
- Which columns are numerical?
- Which columns are categorical?
- Are there missing values?
- Are there duplicates?
- Are there suspicious or invalid values?

---

## Week 2 — Visualization & Univariate Analysis 🟡

**Goal:** Understand individual variables and their distributions.

| Day | Topic | Practice |
|---|---|---|
| Day 8 | Numerical Variables | Mean, median, standard deviation, quartiles |
| Day 9 | Distribution | Histogram |
| Day 10 | Box Plot | Distribution and outliers |
| Day 11 | Categorical Variables | `value_counts()` |
| Day 12 | Bar Chart | Compare categories |
| Day 13 | Skewness | Normal, left-skewed, right-skewed |
| Day 14 | Review Project | Analyze 5–10 columns |

### Example: Histogram

```python
import matplotlib.pyplot as plt

df["price"].hist()

plt.xlabel("Price")
plt.ylabel("Frequency")
plt.show()
```

### Example: Box Plot

```python
df.boxplot(column="price")
```

### Important Skill

Do not only create a graph.

You should also explain what the graph means.

Bad explanation:

> Price is right-skewed.

Better explanation:

> Most values are concentrated in the lower price range, while a small number of very expensive observations create a long right tail.

---

## Week 3 — Relationships & Intermediate EDA 🟠

**Goal:** Understand relationships between variables.

| Day | Topic | Practice |
|---|---|---|
| Day 15 | Numerical vs Numerical | Scatter plots |
| Day 16 | Correlation | Pearson correlation |
| Day 17 | Spearman Correlation | Pearson vs Spearman |
| Day 18 | Category vs Numerical | `groupby()` |
| Day 19 | Category vs Category | `crosstab()` |
| Day 20 | Outlier Detection | IQR |
| Day 21 | Review Project | Full relationship analysis |

### Numerical vs Numerical

```python
df.plot.scatter(
    x="area",
    y="price"
)
```

### Correlation

```python
df[["area", "price"]].corr()
```

### Category vs Numerical

```python
df.groupby("district")["price"].median()
```

### Category vs Category

```python
pd.crosstab(
    df["district"],
    df["property_type"]
)
```

### Questions to Ask

- Does larger area increase price?
- Which district has the highest median price?
- Does property type affect price?
- Are there unusual observations?
- Are two variables strongly related?

---

## Week 4 — Advanced EDA 🔵

**Goal:** Prepare datasets for statistics and machine learning.

| Day | Topic | Practice |
|---|---|---|
| Day 22 | Advanced Outliers | IQR and Z-score |
| Day 23 | Transformations | Log transformation |
| Day 24 | Multivariate EDA | Analyze 3 or more variables |
| Day 25 | Hypothesis Testing | t-test and Chi-square |
| Day 26 | ML-Oriented EDA | Target and feature relationships |
| Day 27 | Data Leakage & Multicollinearity | Detect dangerous features |
| Day 28 | Final EDA Project | Complete EDA from scratch |

### Log Transformation

```python
import numpy as np

df["log_price"] = np.log1p(df["price"])
```

### IQR Outlier Detection

```python
Q1 = df["price"].quantile(0.25)
Q3 = df["price"].quantile(0.75)

IQR = Q3 - Q1

lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR

outliers = df[
    (df["price"] < lower) |
    (df["price"] > upper)
]
```

---

# 🚀 Final EDA Project Workflow

On Day 28, choose one dataset and complete the full workflow.

```text
Dataset
   ↓
1. Understand the Problem
   ↓
2. Load the Data
   ↓
3. Check Shape and Columns
   ↓
4. Check Data Types
   ↓
5. Check Missing Values
   ↓
6. Check Duplicates
   ↓
7. Check Invalid Values
   ↓
8. Descriptive Statistics
   ↓
9. Numerical Distributions
   ↓
10. Categorical Distributions
   ↓
11. Outlier Analysis
   ↓
12. Correlation Analysis
   ↓
13. Feature Relationships
   ↓
14. Multivariate Analysis
   ↓
15. Important Findings
   ↓
16. Recommendations
```

---

# 🕒 Recommended Daily Study Schedule

Study around **1.5 hours per day**.

| Time | Activity |
|---|---|
| 7:30 PM – 7:50 PM | 📖 Learn the concept |
| 7:50 PM – 8:10 PM | 👀 Study examples |
| 8:10 PM – 8:50 PM | 💻 Coding practice |
| 8:50 PM – 9:00 PM | 📝 Write a short summary |

### Sunday Review

Spend around **30–60 minutes** reviewing previous lessons.

```text
Review Previous Lessons
        ↓
Redo Difficult Exercises
        ↓
Practice Without Looking at Notes
        ↓
No New Topic
```

---

# 🧠 Skills to Master

By the end of this roadmap, you should be comfortable with:

## Python Libraries

- Pandas
- NumPy
- Matplotlib
- SciPy
- Scikit-learn basics

## Data Understanding

- Rows and columns
- Numerical variables
- Categorical variables
- Ordinal variables
- Datetime variables
- Text variables
- ID columns
- Target variables

## Data Quality

- Missing values
- Duplicate rows
- Invalid values
- Wrong data types
- Inconsistent categories

## Descriptive Statistics

- Mean
- Median
- Mode
- Minimum
- Maximum
- Standard deviation
- Variance
- Quartiles
- IQR

## Visualization

- Histogram
- Box plot
- Bar chart
- Scatter plot
- Correlation matrix

## Relationships

- Numerical vs Numerical
- Numerical vs Categorical
- Categorical vs Categorical
- Grouped analysis
- Crosstab analysis

## Advanced Topics

- Pearson correlation
- Spearman correlation
- Skewness
- Outliers
- IQR
- Z-score
- Log transformation
- Multivariate analysis
- Hypothesis testing
- t-test
- Chi-square test
- Multicollinearity
- Data leakage
- Feature-target analysis

---

# 📌 Important EDA Mindset

For every graph, statistic, or result, always ask:

```text
1. What do I see?
2. Why might this happen?
3. What should I investigate next?
```

Example:

```python
df["price"].skew()
```

Possible result:

```text
2.7
```

Weak interpretation:

> Skewness is 2.7.

Better interpretation:

> Price is strongly right-skewed.

Strong interpretation:

> Most prices are concentrated in the lower-to-middle range, while a small number of very expensive observations create a long right tail. These high-price observations should be inspected, and a log transformation may be useful.

---

# 📈 Learning Progress

```text
WEEK 1
EDA + Pandas + Data Cleaning
            ↓
WEEK 2
Statistics + Visualization
            ↓
WEEK 3
Relationships + Correlation + Outliers
            ↓
WEEK 4
Advanced EDA + Statistics + ML Preparation
            ↓
        🚀 FINAL PROJECT
```

---

# ✅ Final Goal

After completing this roadmap, you should be able to take a new dataset and independently:

1. Understand it
2. Clean it
3. Explore it
4. Visualize it
5. Detect problems
6. Find important patterns
7. Explain your findings clearly
8. Prepare the data for machine learning

The most important goal is not just knowing the code.

The goal is to become able to **think like a data analyst or data scientist when looking at data**. 📊🚀
