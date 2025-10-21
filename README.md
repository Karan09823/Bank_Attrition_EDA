# Bank_Attrition_EDA
## Overview
This dataset contains bank customer attrition data, which is widely used in the banking and financial industry to analyze customer behavior and identify drivers of churn.
By examining this data, organizations can gain insights into which customer segments are most likely to leave, the products and services associated with attrition, and other key factors influencing customer retention.
These insights help banks develop targeted retention strategies, optimize product offerings, and improve overall customer experience to reduce churn.

## Dataset Description
1. Customer Identification
      row_number, customer_id, first_name → Unique identifiers (mostly for reference, not analysis).

2. Demographics
      state, region → Geographic information; can analyze regional patterns.
      gender, age → Basic demographics; useful for segmenting customers.
      employment_type, residential_status → Employment and living situation; can be linked to financial behavior.

3. Financial Features
      salary → Income level; often correlates with product adoption.
      credit_score → Risk assessment; important for loan/credit analyses.
      tenure → How long the customer has been with the bank.
      balance → Account balance; shows wealth/engagement.
      hascrcard, card_type, hasloan, hasfd, num_of_products → Financial products held; useful for product mix and cross-selling analysis.

4. Engagement & Activity
      isactivemember → Active vs inactive status; can indicate retention risk.
      point_earned → Loyalty or reward points; measure of engagement.
      preferred_channel → Usage behavior (app, branch, call center).

5. Customer Feedback
      complain, count_of_complains → Customer issues; can relate to churn or satisfaction.
      satisfaction_score → Direct measure of customer happiness.

6. Outcome / Target
      exited → Churn indicator (1 = left, 0 = stayed); primary variable for churn analysis.

## Data Cleaning & Preprocessing
- check null values
- drop rows where gender is missing
- fill null columns of salary with median salary
- fill null columns of balance with zero
- fill null columns of  satisfaction score with median satisfaction score
- fill null columns of card type with mode of card type
- find outliers and cap the outliers which is required for the analysis

## Exploratory data analysis

### Number of Female customers are higher than male customers.
<img width="740" height="597" alt="image" src="https://github.com/user-attachments/assets/ebde5428-ef31-41c9-a835-3a0de43634c5" />

### most of the customers have silver card followed by gold card,platinum card and rest are not applicable for any card.
<img width="731" height="591" alt="image" src="https://github.com/user-attachments/assets/7e3b3ece-00e7-4fe6-af51-e19c7453bc9f" />

### Majorly customers dont have loans
<img width="743" height="581" alt="image" src="https://github.com/user-attachments/assets/e3e1a22b-7225-4c27-8633-afd7254b5052" />

### Most of the customers dont have Fixed Deposit account but a significant number of customers have Fixed Deposit Account.
<img width="733" height="570" alt="image" src="https://github.com/user-attachments/assets/ec0e47f4-66af-471e-b9c0-3175318dc513" />

### Customers with a credit score less than 600 has relatively less balance as compared to the customers with a credit score higher than 600
<img width="751" height="571" alt="image" src="https://github.com/user-attachments/assets/0fcbb29d-f93d-4ec0-a8ad-d89b8d30cbcf" />

### The number of customers in the salary ranges of less than 200,000 (Very High), 150,000 (High), and 100,000 (Medium) is higher compared to those in the low salary category (less than 50,000) and very high salary category (above 200,000). This indicates that most customers fall in the medium-to-high salary range, while very low and extremely high-income groups are less represented.
<img width="731" height="581" alt="image" src="https://github.com/user-attachments/assets/acc77fcc-328f-4786-a62a-31a4da6933dd" />

### customers who stayed in the bank has higher average salary as compared to the exited customers of bank.
<img width="753" height="552" alt="image" src="https://github.com/user-attachments/assets/16ccfc16-914c-4458-ac05-8134c00883c6" />

### customers who stayed in the bank has higher average number of products as compared to the exited customers.
<img width="758" height="549" alt="image" src="https://github.com/user-attachments/assets/38513a40-f40b-4936-b455-66e993f4c095" />

### large number of customers are connected to the bank as compared to the exited customers.
<img width="508" height="519" alt="image" src="https://github.com/user-attachments/assets/669dd1ee-392d-4e1e-a5f7-1775d117c864" />

### Maharashtra has highest churn variation followed by Karnataka,Tamil Nadu,Delhi,West Bengal
<img width="639" height="529" alt="image" src="https://github.com/user-attachments/assets/cc5e3ea3-677c-4173-a152-d0ad05835e7c" />

### Younger Customers (approx. 25-50): This age group consists entirely of "Non-churned" customers.Older Customers (approx. 65-80): This age group consists entirely of "Churned" customers.Middle-Aged (approx. 50-65): This is the only age range where both "Churned" and "Non-churned" customers are present.
<img width="721" height="584" alt="image" src="https://github.com/user-attachments/assets/ec0c91f9-a6b4-466f-bcf8-1fbe3e4f45b8" />

### comparatively equal number male and female customers are present in churn distribution
<img width="725" height="575" alt="image" src="https://github.com/user-attachments/assets/6ff6cf3f-cefc-443d-9c55-6634f8a3af3f" />

### churn rate across different states of different gender is very different with different states.
<img width="783" height="436" alt="image" src="https://github.com/user-attachments/assets/e61028dc-f397-49e4-8869-3f6db722b4a8" />

### Most of the customers lies under the income group of 30k
<img width="780" height="567" alt="image" src="https://github.com/user-attachments/assets/3f056ec1-1d83-4792-b943-f05244bc98a5" />

### people in the age group greater than 46 has high average satisfaction score
<img width="714" height="571" alt="image" src="https://github.com/user-attachments/assets/36193d0b-615b-455b-81cd-8272a424efdf" />

### In Each category of employment type like self employed,salaried,business owner the number of stayed customer is higher than exited customers.
<img width="781" height="430" alt="image" src="https://github.com/user-attachments/assets/9c5547f1-b283-406b-9607-c3eb1cf0c969" />

### In Eastern and western region the churn rate of males are greater than female customers apart from that in northern and southern region the churn rates female customer is higher than male customers.
<img width="706" height="578" alt="image" src="https://github.com/user-attachments/assets/f6965856-0ab5-402f-8ab9-001818382eaf" />

### the customers who exited majorly have a credit card
<img width="729" height="572" alt="image" src="https://github.com/user-attachments/assets/5af45c8c-5ef2-47b1-b558-cc5fbbd455d4" />

### Churned vs Non-Churned Customers by Credit Card Ownership
<img width="752" height="565" alt="image" src="https://github.com/user-attachments/assets/09711f12-7c23-47d3-a3fb-a0cf7bdb153f" />

### Credit Card type distribution across churn status
<img width="735" height="577" alt="image" src="https://github.com/user-attachments/assets/42abc498-e16d-4be5-b522-fdf88c8717ed" />

### Loan Ownership vs churned customers
<img width="727" height="561" alt="image" src="https://github.com/user-attachments/assets/735341b1-9e0b-4870-aa31-4bd301024b5a" />

### The churned customers mostly have silver and gold credit cards and very less have gold card
<img width="724" height="568" alt="image" src="https://github.com/user-attachments/assets/bb025a09-5dc3-4ede-9d94-86d914d5ea6b" />

### Among the stayed customers 9622 customers have credit card,2565 have loan and 6041 has fixed deposits and the among the exited customers 2179 have credit card,910 have a loan and 600 have fixed deposits.
<img width="782" height="545" alt="image" src="https://github.com/user-attachments/assets/913dabd4-4efa-4188-b88d-1b050ad1febb" />

### Overall Trend: In all visible tenure groups (0-15 years), customers who did not churn (Blue / "Exited: No") have a higher average number of products than customers who did churn (Orange / "Exited: Yes").Newer Customers (0-10 Years): The difference is quite noticeable for customers with 0-5 years and 5-10 years of tenure. Non-churned customers hold significantly more products on average.Longer-Term Customers (10-15 Years): For customers with 10-15 years of tenure, the gap narrows. The average number of products for both churned and non-churned customers becomes very similar.
#### Data Limitation: The chart only shows data for customers with up to 15 years of tenure. There is no data displayed for any group beyond 15 years.
<img width="781" height="312" alt="image" src="https://github.com/user-attachments/assets/8295acfb-4dcb-476b-a253-66cca57c7a3d" />

### Low credit score(below 600) almost guarantees churn,high credit score(above 800) almost guarantee retention and in the middle ground(600-799) where churn is contested,having more products is correlated with retention.
<img width="779" height="400" alt="image" src="https://github.com/user-attachments/assets/d6c4728f-cd64-4bae-9290-2457bddaa601" />

### If a customer's satisfaction is low, they will churn.If a customer's satisfaction is high, they might stay, but only if their "Points earned" are also low.High "Points earned" appears to be a stronger predictor of churn than high satisfaction is of retention. Any customer with high points is a major churn risk, regardless of how satisfied they claim to be.
<img width="777" height="504" alt="image" src="https://github.com/user-attachments/assets/0072c7e0-fb05-4d78-8a07-2092c4d96301" />

### Majority of the customers who complained stayed
<img width="517" height="518" alt="image" src="https://github.com/user-attachments/assets/46577a99-ca59-49ea-977a-6fbdc4195714" />

### customers with a low balance are at a much higher risk of churning,regardless of their salary.Customers with a high balance are very likely to be retained.
<img width="770" height="572" alt="image" src="https://github.com/user-attachments/assets/e7bc1a0f-0eec-4b9b-987e-593c765dace2" />

### customers who have a fixed amount majorly stayed.
<img width="535" height="516" alt="image" src="https://github.com/user-attachments/assets/9adb8a67-5fe9-4f70-b068-a00cd5c57730" />







