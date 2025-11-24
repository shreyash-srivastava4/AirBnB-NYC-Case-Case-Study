# Airbnb NYC Statistical Analysis & Hypothesis Testing

This project explores an Airbnb bookings dataset for New York City and uses
**exploratory data analysis (EDA)** and **statistical hypothesis testing** to
understand pricing patterns, neighbourhood differences, and guest behaviour.

The analysis is implemented in a Colab Notebook:  
`Airbnb_Stats_Project.ipynb`

---

## Project Overview

The goal of this project is to:

- Clean and understand the Airbnb NYC dataset  
- Explore relationships between price, neighbourhoods, and room types  
- Perform **formal statistical tests** to answer business-style questions such as:
  - Do average room prices differ across neighbourhood groups?
  - Is there a significant price difference between Brooklyn and Manhattan?
  - Is there an association between neighbourhood group and chosen room type?

The project is structured as a case-study style notebook with explanations, code,
and outputs together.

---

## Dataset

- **Name:** Airbnb NYC listings dataset  
- **Rows:** ~49,000  
- **Columns:** 16  
- **Examples of columns:**
  - `id`, `name`, `host_id`, `host_name`
  - `neighbourhood_group`, `neighbourhood`
  - `latitude`, `longitude`
  - `room_type`
  - `price`
  - `minimum_nights`, `number_of_reviews`
  - `last_review`, `reviews_per_month`
  - `availability_365`

> Place the dataset CSV (e.g. `Airbnb_data.csv`) in the same folder as the notebook,
> or update the path in the notebook accordingly.

---

## Data Cleaning & Preparation

Key data preparation steps in the notebook:

- Renaming columns to more readable names  
- Handling missing values (e.g., checking nulls in review-related columns)  
- Checking and dealing with duplicates  
- Inspecting outliers in `price` (via boxplots) and reasoning about whether to remove them  
- Converting data types where necessary (dates, numeric fields)

These steps ensure the dataset is suitable for both EDA and statistical testing.

---

## 🔍 Exploratory Data Analysis (EDA)

The notebook includes visual and descriptive analysis such as:

- Distributions of **price** and **availability**  
- Price trends across **neighbourhood groups** and **room types**  
- Top neighbourhoods by listing count  
- Relationships between:
  - `neighbourhood_group` vs `price`
  - `room_type` vs `price`
  - `number_of_reviews` and `price` (basic relationship checks)

Plots are created using **Matplotlib / Seaborn** (e.g., boxplots, bar charts).

---

## 📐 Statistical Analysis

The project focuses on three main statistical questions:

1. **Do average prices differ across neighbourhood groups?**  
   - Method: **One-way ANOVA**  
   - Tool: `scipy.stats.f_oneway`  
   - Idea: Compare mean price across multiple neighbourhood groups (Manhattan, Brooklyn, Queens, Staten Island, Bronx).

2. **Is there a significant difference in average prices between Brooklyn and Manhattan?**  
   - Method: **Independent samples t-test**  
   - Tool: `scipy.stats.ttest_ind` (with unequal variances)  
   - Idea: Compare mean price for two specific neighbourhood groups.

3. **Is there an association between neighbourhood group and room type?**  
   - Method: **Chi-square test of independence**  
   - Tool: `scipy.stats.chi2_contingency`  
   - Idea: Use a contingency table of `neighbourhood_group` vs `room_type` to test if they are independent.

For each hypothesis, the notebook:

- States the **null and alternative hypotheses**  
- Computes the test statistics and **p-values**  
- Interprets the results in plain language (accept/reject the null hypothesis)

---

## 🛠 Tech Stack

- **Language:** Python  
- **Environment:** Jupyter Notebook (`.ipynb`)  
- **Core Libraries:**
  - `pandas` – data manipulation
  - `numpy` – numerical operations
  - `matplotlib`, `seaborn` – visualizations
  - `scipy.stats` – statistical tests (ANOVA, t-test, chi-square)

---

## ▶️ How to Run This Project

1. **Clone or download** this repository.
2. Make sure you have **Python 3.x** installed.
3. Install the required libraries (in a virtual env if you prefer):

   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
