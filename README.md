# Blinkit-Sales-Dashboard-Power-BI-Project
---------------------------------------------------------------------------------------------------------------------------
A dynamic retail analytics dashboard built in Power BI to uncover sales patterns and business drivers across Blinkit’s diverse outlet network. Blinkit operates across multiple outlet types, sizes, and locations, offering hundreds of products. This dashboard highlights key drivers—from outlet performance to consumer preferences so the company can make sharper decisions about stocking, marketing, and expansion.
---------------------------------------------------------------------------------------------------------------------------
## Project Objective
---------------------------------------------------------------------------------------------------------------------------
To analyze Blinkit’s retail performance across multiple dimensions - item types, outlet types, locations, and time-enabling stakeholders to make informed decisions about inventory, marketing, and regional operations.

---------------------------------------------------------------------------------------------------------------------------
## Dataset Summary
---------------------------------------------------------------------------------------------------------------------------
Source: Simulated Blinkit retail sales data

Total Items Sold: 8,523

Time Span: 2010–2022

Metrics Tracked:

Total Sales

Average Sales per Item

Average Ratings

Number of Items Sold

Item Visibility

---------------------------------------------------------------------------------------------------------------------------
## Process
---------------------------------------------------------------------------------------------------------------------------
- Data cleaning for anamolies in Excel.
- Made sure Data is clean and consistent with respect to data type, data format, values used.
- Create measures and built KPI's - Total Sales, Average Sales, Average Ratings, Number of Items. Visualized them on the cards.
- Added Blinkit Logo and additional canvas background and colours.
- Added Line chart for Total Sales since Outlet Establishment year. Shaded the area of the line chart to showcase sales.
- Added Pie chart to visualize low fat to Regular fat products purchased by metrics.
- Added Clustered bar chart to visualize Fat content by outlet size further added metrics to filter it by Total Sales, Average Sales, Average Ratings, Number of Items.
- Added Pie chart to visualize outlet size and metrics for filtering the report.
- Added a funnel chart to visualize outlet location and metrics for filtering purpose.
- Added Matrix to view the details in the form of a table for Outlet Type, Total sales, No of Items purchased, Average Sales, Average Rating, Item visibility to customers. 
- Added Stacked bar chart to visualize Item type purchased by metrics.
  - Created a new column with the new KPIs and added a metrics column to add New Slicer (Multiple Slicers) to filter the dashboard by Total Sales, Average Sales, Average Ratings, Number of Items.
  - Added additional Slicers for filtering by Outlet Location Type, Outlet size, Item Type and Outlet Type.
---------------------------------------------------------------------------------------------------------------------------
## What the Dashboard Shows
----------------------------------------------------------------------------------------------------------------------------
- Sales Trends Over Time: A line chart tracking growth patterns and spotting seasonal peaks since establishment.
- Outlet Size & Tier Performance: Pie and bar charts revealing whether small, medium, or large outlets and Tier 1, 2, or 3 locations dominate revenue.
- Product Category Breakdown: Bar charts pinpointing which product types (e.g., snacks, fruits & vegetables, household items) generate the most revenue.
- 
Fat Content Analysis:
- A detailed breakdown of low-fat vs. regular-fat products across sales and ratings.
- Insights show low-fat products are more popular in Tier 1 cities, hinting at a health-conscious urban customer base.
- Conversely, regular-fat products sell more in Tier 2 and Tier 3 locations, indicating taste preference and price sensitivity might drive these markets.
- These insights can shape localized inventory strategies stocking more low-fat options in metro outlets while focusing on traditional products in smaller cities.
- Customer Ratings vs. Sales: Spotting if higher-rated items always convert into higher sales and where there’s untapped potential

---------------------------------------------------------------------------------------------------------------------------
### Product Relationship Analysis: Visibility vs. Sales
---------------------------------------------------------------------------------------------------------------------------

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

# Load data
df = pd.read_excel("BlinkIT Grocery Data.xlsx")

# Prepare features and target
X = df[["Item Weight", "Item Visibility", "Rating"]].fillna(0)
Y = df["Sales"]

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, Y, test_size=0.2, random_state=42)

# Linear regression model
model = LinearRegression()
model.fit(X_train, y_train)

# Predictions and evaluation
y_pred = model.predict(X_test)
print("R2 Score:", round(r2_score(y_test, y_pred), 3))

### R² Score: 0.001
---------------------------------------------------------------------------------------------------------------------------
Interpretation:
---------------------------------------------------------------------------------------------------------------------------
The chosen variables-Item Weight, Item Visibility, and Rating do not significantly predict sales. Visibility Optimization is a must to showcase product options to the consumer as per their individual preference.
---------------------------------------------------------------------------------------------------------------------------
## Business Insights
---------------------------------------------------------------------------------------------------------------------------
Tier 1 locations consistently outperform in total sales across outlet types.

Supermarket Type1 and Grocery Stores show higher average sales and ratings.

Snack foods, fruits & vegetables, and household items lead in contribution by item type.

Low-fat products are preferred in Tier 1 regions, highlighting potential for tailored assortment strategies.

---------------------------------------------------------------------------------------------------------------------------
Business Value
---------------------------------------------------------------------------------------------------------------------------
Inventory Optimization: Stocking the right products, in the right place, at the right time.
Targeted Marketing: Campaigns built around local tastes and lifestyle trends.
Strategic Expansion: Identifying high-performing tiers and outlet sizes to replicate success.

---------------------------------------------------------------------------------------------------------------------------
## Tools Used
---------------------------------------------------------------------------------------------------------------------------
Power BI for data cleaning, modeling and visualization

DAX for calculated measures and KPIs

Excel for initial data preprocessing

---------------------------------------------------------------------------------------------------------------------------
## How to Use
---------------------------------------------------------------------------------------------------------------------------
Clone or download this repo.

Open the .pbix file in Power BI Desktop.

Use slicers and filters to dynamically explore sales across dimensions.

---------------------------------------------------------------------------------------------------------------------------
## Skills Demonstrated
---------------------------------------------------------------------------------------------------------------------------
Exploratory Data Analysis (EDA)

Dynamic dashboarding with DAX

Retail performance analysis

KPI storytelling & data-driven insight delivery

Power BI interactivity best practices
