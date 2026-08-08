# Customer-Analysis
A simple project where I cleaned customer shopping data using Python, stored it in MySQL, and built a Power BI dashboard to explore the results.

# Customer Shopping Behavior Analysis

## Overview
I built this project to explore how customers shop — what they buy, how much they spend, whether they're subscribed, and how they rate their purchases. It covers the full workflow: cleaning raw data in Python, storing and querying it in MySQL, and visualizing the results in an interactive Power BI dashboard.

## Dataset
The dataset (`"C:\Users\prajwal\Downloads\customer_shopping_behavior.csv"`) contains 3,900 customer records, with details like age, gender, item purchased, category, purchase amount, location, shipping type, subscription status, discount usage, and review ratings.

## Tools Used
- **Python (Pandas)** – for cleaning and preparing the data
- **Jupyter Notebook** – where the Python code was written and run
- **MySQL** – to store the cleaned data and run SQL queries
- **SQLAlchemy & PyMySQL** – to connect Python to MySQL
- **Power BI** – to build the final dashboard

## Steps
Here's what I did, step by step:

1. **Loaded the data** into a pandas DataFrame from the CSV file.
2. **Explored the data** – checked the structure, summary statistics, and looked for missing values.
3. **Cleaned the data** – filled in missing review ratings using the median rating for each product category, so the fix stayed relevant to that type of product.
4. **Standardized column names** – made everything lowercase with underscores so it would work smoothly with SQL later.
5. **Created new features** – added an `age_group` column (splitting customers into four age bands) and a `purchase_frequency_days` column (turning purchase frequency into a number of days).
6. **Removed a duplicate column** – found that `discount_applied` and `promo_code_used` always matched, so I dropped the extra one.
7. **Loaded the cleaned data into MySQL** using SQLAlchemy, so it could be queried with SQL.
8. **Wrote SQL queries** to answer real business questions – revenue by gender, top-rated products, discount trends, customer segmentation (new/returning/loyal), top products per category, and revenue by age group.
9. **Connected Power BI to MySQL** and built a dashboard on top of the cleaned data.

## Dashboard
The Power BI dashboard gives a quick, visual summary of customer behavior:
- KPI cards for total customers, average purchase amount, and average review rating
- A breakdown of subscribed vs. non-subscribed customers
- Revenue and sales comparisons across product categories
- Revenue and sales comparisons across age groups
- Filters for subscription status, gender, category, and shipping type, so anyone viewing it can explore the data their own way


![Dashboard]<img width="1327" height="726" alt="image" src="https://github.com/user-attachments/assets/23052b8e-bd44-47e4-af48-b0defe6c1b08" />


## Results
A few things that stood out from the analysis:
- Clothing brings in the most revenue and the most sales, followed by Accessories, Footwear, and Outerwear.
- Only about 27% of customers are on a subscription — most are one-time or occasional shoppers.
- Revenue is fairly evenly spread across age groups, since customers were split into four equal-sized age bands.
- Some products rely much more heavily on discounts to sell than others.

## How to Run
1. Clone this repository.
2. Install the required packages: `pandas`, `sqlalchemy`, `pymysql`.
3. Open the Jupyter notebook and update the MySQL username and password to match your own setup.
4. Run the notebook — it will clean the data and load it into your MySQL database.
5. Run the SQL queries against the `customer` table to reproduce the analysis.
6. Open the Power BI file and connect it to your MySQL database to view the dashboard.
