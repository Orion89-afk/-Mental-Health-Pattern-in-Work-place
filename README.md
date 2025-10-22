# -Mental-Health-Pattern-in-Work-place

![Image](https://github.com/user-attachments/assets/5ac817db-8d97-436a-99d6-348b00c8ce2a)
Understanding the Factors that Affects Mental Health. This dataset records a global survey conducted to track trends in mental health. The data covers a range of variables such as levels of stress, depression, anxiety, subjective well-being, and use of mental health services. 
# 🧠 Mental Health Data Analysis — Excel, Power Query & Power BI

## 📋 Project Overview
This project explores the key factors influencing **mental health status and treatment-seeking behavior** among individuals.  
The dataset was sourced from [Kaggle’s Mental Health Dataset](https://www.kaggle.com/datasets/divaniazzahra/mental-health-dataset/data) and analyzed using **Microsoft Excel**, **Power Query**, and **Power BI**.

The goal of this project is to:
- Identify the most important predictors of mental health conditions.
- Understand the relationships between **stress, mood, family history,** and **treatment-seeking behavior**.
- Develop interactive Power BI visuals to communicate insights effectively.

---

## 🧰 Tools & Technologies
| Tool | Purpose |
|------|----------|
| 🟢 **Microsoft Excel** | Data cleaning, exploratory data analysis, and regression modeling |
| 🔵 **Power Query** | Automated data transformation and preprocessing |
| 🟣 **Power BI** | Data visualization and storytelling dashboard creation |

---

## 📂 Project Workflow
### 🔹 1. Data Collection & Cleaning
- Imported dataset into **Excel**.
- Used **Power Query** for:
  - Removing duplicates and missing values.
  - Standardizing categorical responses (Yes/No, Gender, Country, etc.).
  - Converting ordinal variables into numerical codes for analysis.

### 🔹 2. Exploratory Data Analysis (Excel)
Performed descriptive and inferential analysis using Excel functions and charts:
- Summary statistics (AVERAGE, STDEV, COUNTIF)
- Correlation tests between stress, mood, and coping variables.
- Built multiple regression models to identify predictors of:
  - Mental Health History
  - Treatment-Seeking Behavior

## 📈 Regression Models & Findings

### 🧩 Model 1 — Predictors of Mental Health History
**Variables:** Stress, Mood, Coping Struggles  
- All three predictors were statistically significant but with **small effect sizes**.  
- **Interpretation:** Psychological indicators (like stress and mood swings) show a link to mental health history but are not dominant predictors.

### 👪 Model 2 — Family History & Stress → Mental Health History
**Key Finding:**  
- **Family History** was the strongest predictor (β = 0.375, p < 0.001).  
- Stress had a small positive effect.  
✅ **Conclusion:** People with a family history of mental illness are **significantly more likely** to report mental health issues.

### 💬 Model 3 — Predictors of Treatment-Seeking Behavior
**Variables:** Awareness (Interview Score), Stress, Family History, Work Culture  
| Factor | Effect | Significance | Insight |
|--------|---------|--------------|----------|
| Family History | Strong positive | ✅✅✅ | Main driver of treatment-seeking |
| Stress | Weak positive | ✅ | Small but real influence |
| Interview (Awareness) | Negative | ✅ | Higher awareness linked to lower treatment-seeking (possible stigma) |
| Work Interest | Neutral | ❌ | No measurable impact |

**R² = 0.136** → Model explains 13.6% of treatment behavior variability.

---

## 📈 Regression Analyses Details
All regression models were computed using **Excel’s Data Analysis Toolpak** on the cleaned dataset. Below are the three main regression models we ran, their numeric outputs, and plain-language interpretations you can paste into your report or dashboard.

> **Note:** coefficients, R², p-values and other metrics are reported exactly as obtained from Excel outputs.

---

### 🔁 Model 1 — Psychological Indicators → *Mental Health History*
**Purpose:** Test whether personal psychological indicators (Growing Stress, Mood Swings, Coping Struggles) are predictive of having a mental health history.

**Key statistics**
- Observations: **292,364**  
- Multiple R: **0.0451**  
- R²: **0.0020** (0.20%)  
- Adjusted R²: **0.0020**  
- Standard Error: **0.4651**  
- ANOVA F-statistic: **198.45**, **p < 1e-120** (model significant overall)

**Coefficients**
| Predictor | Coef (β) | Std. Error | t Stat | P-value |
|----------:|---------:|-----------:|-------:|--------:|
| Intercept | 0.257377 | 0.002663 | 96.664  | 0.000 |
| Stress_Score | **0.014332** | 0.001061 | 13.504 | 1.52e-41 |
| Mood_Score | **0.021105** | 0.001064 | 19.828 | 1.95e-87 |
| Struggle_Score | **0.009175** | 0.001724 | 5.322  | 1.03e-07 |

**Interpretation :**
- All three predictors are **statistically significant** (p ≪ 0.05).  
- **Effect sizes are very small** (combined they explain ~0.2% of variance).  
- Conclusion: *Stress, mood swings, and coping struggles relate to mental health history, but they are weak predictors by themselves — useful as signals but not sufficient for reliable prediction.*

---

### 🔁 Model 2 — Family History & Stress → *Mental Health History*
**Purpose:** Measure the relative importance of family history vs. current stress for predicting mental health history.

**Key statistics**
- Observations: **292,364**  
- Multiple R: **0.3668**  
- R²: **0.1345** (13.45%)  
- Adjusted R²: **0.1345**  
- Standard Error: **0.4651**  
- ANOVA F-statistic: **22,726.02**, **p < 0.001**

**Coefficients**
| Predictor | Coef (β) | Std. Error | t Stat | P-value |
|----------:|---------:|-----------:|-------:|--------:|
| Intercept | 0.353886 | 0.001546 | 228.89 | 0.000 |
| Family_History_Score | **0.375064** | 0.001760 | 213.15 | 0.000 |
| Stress_Score | **0.002708** | 0.001061 | 2.553 | 0.0107 |

**Interpretation :**
- **Family history is by far the strongest predictor** (β ≈ 0.375, p < 0.001).  
- Stress is statistically significant but its effect is very small.  
- The model explains **~13.5%** of variation — a moderate amount for behavioral/social data.  
- Conclusion: *Family history is a dominant signal of mental health history; stress adds a small incremental effect.*

---

### 🔁 Model 3 — Awareness, Stress, Family History, Work Culture → *Treatment-Seeking*
**Purpose:** Identify which factors best explain whether someone seeks treatment (awareness/interview comfort, stress, family history, work interest/culture).

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/7b166c7b-b972-44e5-81c2-cc3a98586d16" />



## 📊 Power BI Dashboard

### **Dashboard Sections**
| Section | Description |
|----------|--------------|
| **Overview Page** | Dataset summary, KPIs (R², F-Value, Significance) |
| **Predictors Page** | Bar chart comparing coefficients of Stress, Mood, and Coping |
| **Family & Stress Page** | Stacked column chart showing effect strength; scatter plot highlighting clusters |
| **Treatment Drivers Page** | Key Influencers visual + Lollipop chart ranking predictors |
| **Insight Summary** | Narrative visuals summarizing “Who is most likely to seek help?” |


## 💡 Key Insights
- **Family History** is the most consistent and powerful predictor across models.
- **Stress** increases likelihood of both mental health issues and treatment-seeking, though modestly.
- **Awareness (Interview Confidence)** can *reduce* treatment-seeking — possibly due to stigma or self-sufficiency.
- **Work Culture** variables showed minimal impact on mental health decisions.



**Key statistics**
- Observations: **292,364**  
- Multiple R: **0.3693**  
- R²: **0.1364** (13.64%)  
- Adjusted R²: **0.1363**  
- Standard Error: **0.4646**  
- ANOVA F-statistic: **11,540.16**, **p < 0.001**

**Coefficients**
| Predictor | Coef (β) | Std. Error | t Stat | P-value |
|----------:|---------:|-----------:|-------:|--------:|
| Intercept | 0.364546 | 0.001870 | 194.94 | 0.000 |
| Interview_Score | **-0.087211** | 0.003524 | -24.75 | 4.29e-135 |
| WorkInterest_Score | 0.002005 | 0.002135 | 0.939 | 0.3478 (ns) |
| Family_History_Score | **0.372126** | 0.001762 | 211.22 | 0.000 |
| Stress_Score | **0.002545** | 0.001061 | 2.399 | 0.0164 |

**Interpretation :**
- **Family History** again is the **strongest positive predictor** of treatment-seeking (β ≈ 0.372, p < 0.001).  
- **Interview_Score** (a proxy for awareness/comfort or perceived stability) is **negatively** associated with treatment-seeking (β ≈ -0.087, p < 0.001) — suggesting people who present as confident/less vulnerable are less likely to seek help.  
- **Stress** has a small but statistically significant positive effect.  
- **Work Interest** shows **no significant effect** on treatment-seeking (p ≈ 0.348).  
- Overall model explains **~13.6%** of variance in treatment decisions.

**Conclusion:**  
> Family history is the dominant factor driving treatment decisions. People with high family history scores are much more likely to seek treatment; stress supports this tendency slightly; awareness/appearance (Interview_Score) can be inversely related to help-seeking, and work-interest does not meaningfully predict treatment.

---

## 🔎 How I Ran These Models
- Data cleaned and standardized in **Excel** using **Power Query** (removing duplicates, standardizing categorical labels, creating numeric score columns).  
- Ordinal variables (e.g., Mood_Swings: Low/Medium/High) were encoded to numeric scores for regression.  
- Regressions computed with **Excel Data Analysis Toolpak → Regression**. Regression outputs (ANOVA, coefficients, p-values) are saved in `excel/Regression_Models.xlsx`.
- 

##  Summary
- **Family history** is the most consistent and powerful predictor for **both** having a mental health history and seeking treatment.  
- **Stress** is positively related to both outcomes but with small effect size.  
- **Mood swings** and **coping struggles** are statistically significant indicators of mental health history but explain little variance on their own.  
- **Awareness/Interview performance** may reduce reported treatment-seeking (negative association) — this can reflect stigma, self-reliance, or social desirability bias.  
- **Work interest / culture** (as operationalized here) did not significantly affect treatment-seeking.


## 📁 Files to include in the repo (recommended)
- `data/Mental Health Dataset.csv` (raw)  
- `excel/Data_Cleaning.xlsx` (Power Query steps & transformations)  
- `excel/Regression_Models.xlsx` (full regression outputs / ANOVA tables)  
- `powerbi/Mental_Health_Dashboard.pbix` (Power BI report)  
- `visuals/` (PNG screenshots of charts & regression tables)  


## 🧾 Author
Joy Olabode 
📧 joyolabode89@gmail.com | 🔗 [LinkedIn](https://www.linkedin.com) | 🔗 [GitHub](https://github.com/yourusername)



