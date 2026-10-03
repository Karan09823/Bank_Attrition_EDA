# 🏦 Bank Customer Attrition — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat\&logo=python\&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat\&logo=pandas\&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=flat\&logo=numpy\&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=flat)
![EDA](https://img.shields.io/badge/Project-EDA-orange?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-success?style=flat)

> **An exploratory data analysis project focused on identifying the demographic, financial, product, and engagement factors associated with bank customer attrition.**

---

## 📌 Project Overview

Customer attrition is a major challenge for financial institutions because acquiring a new customer can be significantly more expensive than retaining an existing one.

This project analyzes **bank customer attrition data** to identify the major characteristics and behavioral patterns associated with customers leaving the bank.

The analysis explores:

* 👥 Customer demographics
* 🌍 Geographic patterns
* 💰 Income and account balances
* 📊 Credit scores
* 💳 Product ownership
* 🏦 Loans and fixed deposits
* ⭐ Satisfaction and loyalty
* 📢 Customer complaints
* 📱 Customer engagement
* ⏳ Customer tenure

The objective is to uncover actionable patterns that can help organizations design **targeted retention strategies, improve product offerings, and enhance customer experience**.

---

## 🎯 Problem Statement

> **Identify the key indicators and behavioral drivers of customer attrition to recommend targeted, data-driven retention campaigns, optimize current product offerings, and improve the overall customer experience to reduce churn.**

---

## 📂 Dataset Description

The dataset contains customer-level information covering demographic, financial, product, engagement, and feedback-related attributes.

### 👤 Customer Identification

| Feature       | Description                |
| ------------- | -------------------------- |
| `row_number`  | Row identifier             |
| `customer_id` | Unique customer identifier |
| `first_name`  | Customer's first name      |

### 👥 Demographics

| Feature              | Description               |
| -------------------- | ------------------------- |
| `state`              | Customer's state          |
| `region`             | Geographic region         |
| `gender`             | Customer gender           |
| `age`                | Customer age              |
| `employment_type`    | Employment category       |
| `residential_status` | Residential/living status |

### 💰 Financial Features

| Feature           | Description                          |
| ----------------- | ------------------------------------ |
| `salary`          | Customer income                      |
| `credit_score`    | Customer credit score                |
| `tenure`          | Length of relationship with the bank |
| `balance`         | Account balance                      |
| `hascrcard`       | Whether customer has a credit card   |
| `card_type`       | Credit card category                 |
| `hasloan`         | Whether customer has a loan          |
| `hasfd`           | Whether customer has a fixed deposit |
| `num_of_products` | Number of banking products held      |

### 📱 Engagement & Activity

| Feature             | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| `isactivemember`    | Indicates whether the customer is an active member            |
| `point_earned`      | Loyalty/reward points earned                                  |
| `preferred_channel` | Preferred banking channel such as app, branch, or call center |

### 😊 Customer Feedback

| Feature              | Description                                |
| -------------------- | ------------------------------------------ |
| `complain`           | Whether the customer submitted a complaint |
| `count_of_complains` | Number of complaints                       |
| `satisfaction_score` | Customer satisfaction score                |

### 🎯 Target Variable

| Feature  | Description                  |
| -------- | ---------------------------- |
| `exited` | Customer attrition indicator |
| `0`      | Customer stayed              |
| `1`      | Customer exited              |

---

# 🧹 Data Cleaning & Preprocessing

Before performing exploratory analysis, the dataset was cleaned and standardized to improve data quality and consistency.

### 🔧 Cleaning Steps

1. **Standardized column names**

   * Converted column names to lowercase.
   * Replaced spaces and inconsistent naming with underscores.

2. **Missing-value assessment**

   * Checked all columns for missing values.
   * Evaluated missing values before selecting appropriate imputation strategies.

3. **Gender**

   * Removed **6 rows** containing missing `gender` values.

4. **Salary**

   * Missing salary values were imputed using the **median salary**.

5. **Balance**

   * Missing balance values were replaced with **0**.

6. **Satisfaction Score**

   * Missing satisfaction scores were imputed using the **median score**.

7. **Card Type**

   * Missing `card_type` values were imputed using the **mode**.

8. **Salary Outliers**

   * Salary outliers were identified using the **IQR method**.
   * Extreme values were capped at the lower and upper IQR boundaries.

---

# 📊 Exploratory Data Analysis

## 👥 1. Demographics & Geography

### Gender Distribution

The customer base contains a higher number of male customers:

| Gender | Customers |
| ------ | --------: |
| Male   | **9,028** |
| Female | **5,966** |

This difference was considered while analyzing churn patterns across demographic segments.

---

### 🌍 Regional & State-Level Patterns

Customer attrition varies considerably across geographic locations.

**Maharashtra** exhibits the highest churn variation, followed by:

1. Karnataka
2. Tamil Nadu
3. Delhi
4. West Bengal

An additional pattern emerges when comparing gender-specific churn across regions:

* **Eastern & Western regions:** Male churn exceeds female churn.
* **Northern & Southern regions:** Female churn exceeds male churn.

This indicates that geographic segmentation combined with demographic characteristics can provide more useful insights than looking at overall churn alone.

---

## 🎂 Age Dynamics

Age emerged as one of the strongest demographic dimensions associated with attrition.

### Key observation

* Customers approximately **25–50 years old** demonstrate relatively strong retention.
* Customers approximately **65–80 years old** consist predominantly of exited customers.

This suggests that retention strategies may need to be adapted to different age segments rather than applying a single strategy across the entire customer base.

---

## 💼 Employment

Across the major employment categories:

* Self-employed
* Salaried
* Business owners

the **absolute number of retained customers remains higher than exited customers**.

Employment type therefore provides useful segmentation context, but should be interpreted alongside financial and behavioral variables.

---

# 💰 2. Financial Health & Product Holdings

## 💵 Salary & Account Balance

The analysis reveals two important patterns:

### Salary

Higher average salaries are associated with stronger customer retention.

### Balance

Customers with **low account balances** demonstrate substantially higher attrition risk, regardless of their salary tier.

> **Key insight:** Income alone does not explain customer retention. Account balance provides an additional and important signal of potential attrition.

---

# 📊 Credit Score

Credit score demonstrates a strong relationship with customer attrition.

### Observed pattern

| Credit Score | Observed Pattern                  |
| ------------ | --------------------------------- |
| **< 600**    | Higher propensity to exit         |
| **600–799**  | More mixed retention behavior     |
| **800+**     | Strong association with retention |

Customers with credit scores below 600 show substantially greater attrition, while customers with scores above 800 are more strongly associated with retention.

---

# 🛍️ Product Cross-Selling & Retention

The **600–799 credit-score segment** reveals an interesting relationship between product ownership and retention.

Among customers in this middle credit-score range:

> Customers who remain with the bank tend to hold **more products on average** than customers who exit.

The relationship is particularly noticeable among customers with **0–10 years of tenure**.

This suggests that deeper product relationships may be associated with stronger customer retention.

---

# 💳 Credit Cards, Loans & Fixed Deposits

### Credit Cards

A large proportion of exited customers held credit cards, with **Silver and Gold** being the most common card categories among them.

However, credit-card ownership by itself should not be interpreted as a direct cause of attrition.

### Loans

The majority of customers do not hold loans.

### Fixed Deposits

A significant portion of customers do not have Fixed Deposit accounts.

One of the more notable findings is:

> Customers retaining Fixed Deposits demonstrate a strong association with staying with the bank.

This makes Fixed Deposits a potentially important product relationship to investigate further.

---

# 😊 3. Customer Satisfaction & Engagement

## ⭐ The Loyalty Paradox

One of the most interesting observations in the analysis involves the relationship between **satisfaction** and **loyalty points**.

Normally, higher customer satisfaction would be expected to correspond with better retention.

However, the `point_earned` metric reveals a different pattern:

> Customers with high reward points demonstrate elevated churn risk, even when reported satisfaction is relatively high.

This creates a potential **loyalty paradox**:

**High engagement → High points → Yet elevated attrition**

This pattern warrants deeper investigation into the structure and effectiveness of the loyalty program.

Possible explanations could include:

* Short-term reward seekers
* Customers accumulating points without long-term attachment
* Poor redemption experience
* Rewards not aligned with customer needs
* Customers using points before leaving
* Product or pricing issues not captured by satisfaction scores

These possibilities would require additional analysis before establishing causality.

---

# 📢 Customer Complaints

The analysis shows that the majority of customers who registered a complaint ultimately remained with the bank.

This suggests that:

> **A complaint in isolation is not necessarily a strong indicator of customer attrition.**

Complaint behavior should therefore be considered alongside other factors such as:

* Complaint frequency
* Satisfaction score
* Account balance
* Product ownership
* Credit score
* Customer tenure

---

# 😊 Satisfaction by Age

Older customers, particularly those aged **46+**, generally report higher average satisfaction scores.

This is an interesting contrast with the observed age-related attrition pattern and suggests that satisfaction alone may not explain why certain older customers leave.

---

# 🔍 Key Findings at a Glance

| Area              | Key Finding                                                                        |
| ----------------- | ---------------------------------------------------------------------------------- |
| 👥 Gender         | Customer base is predominantly male                                                |
| 🌍 Geography      | Attrition patterns vary significantly by state and region                          |
| 🎂 Age            | Older customers show substantially higher attrition                                |
| 💰 Salary         | Higher average salary is associated with stronger retention                        |
| 🏦 Balance        | Low account balances are strongly associated with attrition                        |
| 📊 Credit Score   | Scores below 600 show higher attrition                                             |
| 🛍️ Products      | Greater product ownership is associated with stronger retention                    |
| 💳 Credit Cards   | Many exited customers hold Silver/Gold cards                                       |
| 🏦 Fixed Deposits | FD ownership is strongly associated with retention                                 |
| ⭐ Loyalty Points  | High points are associated with elevated churn                                     |
| 📢 Complaints     | Complaints alone do not appear to drive most attrition                             |
| 😊 Satisfaction   | Higher satisfaction generally supports retention, but does not fully explain churn |

---

# 💡 Strategic Recommendations

## 1. ⭐ Investigate & Revamp the Loyalty Program

The relationship between high reward points and elevated attrition deserves further investigation.

The bank could evaluate:

* Reward redemption behavior
* Point expiration
* Reward relevance
* Customer lifetime value
* Loyalty-program usage frequency
* Post-redemption churn

The objective should be to determine whether the existing rewards structure encourages **long-term customer relationships** or primarily short-term engagement.

---

## 2. 🛍️ Targeted Cross-Selling for the Middle Credit-Score Segment

Customers with credit scores between **600–799** appear particularly sensitive to product holdings.

Potential initiatives include targeted offers for relevant secondary products such as:

* Fixed Deposits
* Savings products
* Credit products
* Investment products

Cross-selling should be based on customer suitability and behavior rather than applying the same offer to every customer.

---

## 3. 💰 Proactive Low-Balance Interventions

Low account balances appear to be an important attrition indicator regardless of salary.

Potential retention initiatives could include:

* Automated engagement campaigns
* Low-balance alerts
* Fee-waiver programs
* Low-fee account options
* Personalized financial products
* Relationship-manager outreach

The objective would be to identify potentially vulnerable accounts before attrition occurs.

---

## 4. 💳 Evaluate Fee Structures for Lower-Income Customers

Since higher salaries are associated with stronger retention, the bank could investigate whether pricing and account requirements disproportionately affect lower- and middle-income customers.

Potential approaches include:

* Low-fee account tiers
* Reduced minimum-balance requirements
* Targeted offers
* Flexible account packages
* Personalized banking plans

Further analysis would be required to determine whether fees are actually contributing to the observed relationship.

---

# 🧰 Tools & Technologies

| Technology              | Purpose                         |
| ----------------------- | ------------------------------- |
| 🐍 **Python**           | Data analysis and preprocessing |
| 🐼 **Pandas**           | Data manipulation               |
| 🔢 **NumPy**            | Numerical analysis              |
| 📊 **Matplotlib**       | Data visualization              |
| 📈 **Seaborn**          | Statistical visualization       |
| 📓 **Jupyter Notebook** | Interactive analysis            |

---

# 🔬 Analysis Workflow

```text
Raw Dataset
     │
     ▼
Data Loading
     │
     ▼
Data Inspection
     │
     ▼
Data Cleaning
     │
     ├── Missing Values
     ├── Duplicate/Invalid Data Checks
     ├── Column Standardization
     └── Outlier Treatment
     │
     ▼
Exploratory Data Analysis
     │
     ├── Demographic Analysis
     ├── Geographic Analysis
     ├── Financial Analysis
     ├── Product Analysis
     └── Engagement Analysis
     │
     ▼
Attrition Pattern Identification
     │
     ▼
Business Insights
     │
     ▼
Retention Recommendations
```

---

# 📈 Business Impact

The analysis can support banking teams in identifying customer segments associated with elevated attrition and developing more targeted retention strategies.

Potential applications include:

* 🎯 Customer churn segmentation
* 📩 Personalized retention campaigns
* 🛍️ Product cross-selling
* 💰 Low-balance customer monitoring
* ⭐ Loyalty-program optimization
* 💳 Product portfolio analysis
* 😊 Customer experience improvement

---

# ⚠️ Important Analytical Note

This project is an **Exploratory Data Analysis (EDA)** and identifies associations and patterns within the dataset.

The observed relationships should **not automatically be interpreted as causal relationships**.

For example:

> High reward points are associated with higher attrition, but this does not prove that reward points cause customers to leave.

Further analysis could include:

* Statistical hypothesis testing
* Feature importance analysis
* Logistic regression
* Decision trees
* Random Forest
* Gradient boosting
* Customer segmentation
* Churn prediction modeling
* Survival analysis

These methods could help validate and quantify the observed relationships.

---

# 🚀 Future Scope

The project can be extended from descriptive analytics into predictive analytics.

### 🔮 Churn Prediction

Develop a machine-learning model to estimate the probability that an individual customer will exit.

### 🎯 Customer Segmentation

Use clustering techniques such as **K-Means** to identify customer groups with similar financial and behavioral characteristics.

### 📊 Feature Importance

Use tree-based models or explainability techniques such as **SHAP** to identify the strongest predictors of attrition.

### ⏳ Survival Analysis

Analyze **when** customers are likely to leave rather than only whether they leave.

### 📈 Retention Dashboard

Build an interactive **Power BI dashboard** to allow business users to monitor:

* Attrition rate
* Attrition by age
* Attrition by state
* Credit-score segments
* Product ownership
* Balance ranges
* Loyalty points
* Satisfaction
* Customer tenure

---

# 👨‍💻 Project Structure

```text
Bank_Attrition_EDA/
│
├── Bank_Attrition_EDA.ipynb
├── Bank_attrition_Data.xlsx
├── README.md
└── bankattrition_eda.py
```

---

# 📌 Conclusion

The analysis demonstrates that customer attrition is influenced by a combination of **demographic, financial, product, and engagement-related factors**.

Several patterns stand out, particularly:

* **Age and credit score** as important segmentation variables
* **Low account balances** as an important attrition signal
* **Product depth** as an indicator associated with retention
* **Fixed Deposit ownership** as a notable retention-related characteristic
* **High reward points** as an unexpected churn-related pattern
* **Geographic and gender differences** in attrition behavior

These insights provide a foundation for developing more targeted retention strategies and can be further validated through statistical analysis and machine-learning models.

---

## ⭐ If you found this project useful

Feel free to **star ⭐ the repository** and explore the analysis.

**Built with Python 🐍 | Pandas 🐼 | NumPy 🔢 | Matplotlib 📊 | Seaborn 📈**
