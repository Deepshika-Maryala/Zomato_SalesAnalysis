# A Deep Dive into Zomato’s Performance: Insights with Power BI
### Project Overview
This project aims to create a Power BI dashboard for Zomato, offering real-time insights into key metrics such as total sales, average order value, customer ratings and performance in different cities. The dashboard will consolidate data from various sources, providing actionable insights.
### Purpose and Performance Targets:
- Design and develop an interactive sales overview performance, customer insight and geographic performance dashboard.
- Provide real-time access to sales metrics, segmented by region.
- Improve forecasting accuracy through trend analysis and predictive models.
### Data Source
The dataset used for the analysis are "food.xlsx", "order.xlsx", "order_type.xlsx", "menu.xlsx", "restaurant.xlsx", and "user.xlsx" files, containing detail information about food items and types, menu, orders, restaurant and the users.
### Tools:
- Excel spreadsheets – Data cleaning
- SQL – Data Analysis
- Power BI Desktop [version 2.126.927.0] – Creating report
### Data Cleaning and Preparation:
- Data loading and Inspection
- Handling missing values
- Data cleaning and formatting
### Exploratory Data Analysis:
EDA involved exploring the sales data to answer the key questions such as:
- What are the sales trends year-over-year?
- How do sales vary across different regions or cities?
- What percentage of customers are repeat customers vs first-time users?
### Data Analysis:
- Analyzing Total sales , total quantity, overall rating and total orders using SQL.
```sql
	Select sum(sales_amount) as Total_Sales from orders;
```
```sql
	Select sum(sales_qty) as Total_quantity from orders;
```
```sql
	Select count(rating) as Overall_Rating from restaurant;
```
```sql
	Select count(order_id) as Total_Orders from order_type;
```
- Analyzing total users and active users using SQL
```sql 
Select count(user_id) as Total_Users from user;
```
```sql
Select count(distinct(user_id as Active_Users from user;
```
- Finding total gain customers this year and total lost customers this year using Dax functions
```dax
Gaincust = var filteruser= FILTER( SUMMARIZE(users,users[user_id]),AND([preyrsales]<=0,[curyrsales]>0)) return CALCULATE([Total User],filteruser)
```
![Screenshot 2024-09-26 193848](https://github.com/user-attachments/assets/103ac553-40e8-4d7f-99c3-5a7edd7421da)

```DAX
Lostcust = var filteruser= FILTER( SUMMARIZE(users,users[user_id]),AND([curyrsales]<=0,[preyrsales]>0)) return CALCULATE([Total User],filteruser)
```
![Screenshot 2024-09-26 193904](https://github.com/user-attachments/assets/a3af59f5-6371-44bc-95d6-49fa1b182a68)

### Insights and Findings:
- Sales have been increasing mainly during weekends and holidays.
- The data revealed that the active users and between the ages 20 to 30 years.
- The data also revealed that the demand for vegetarian dishes is increasing than the rest.
- The sales from the metropolitan cities are massively increasing.
### Analyzed Matrics:
- Total sales
- Total Quantity
- Total orders
- Overall Rating
- Active Users
- Total Users
- Customer gain
- Customer Lost
### Visuals and Dashboards:
#### Perormance Dashboard:
- KPI: Total sales, total quantity, overall rating, total orders, non-veg sales and rating, Veg sales and rating , and other dishes sales and rating.
- Top 10 performance cities: Analyzing the performance of zomato in top 10 cities.
- Yearly sales trend : Analyzing the sales on yearly basis.
#### Area Analysis Dashboard:
- KPI: Total sales, total quantity, overall rating, and total orders.
- Total Sales by cities: Analyzing city-wise total sales.
- Overall rating by cities: Analyzing city-wise overall rating.
- Active users by cities: Analyzing city-wise active users.
- A table containing the complete city-wise information of total sales, orders and active users.
#### User Analysis Dashboard:
- KPI CARD: Total users, active users, overall rating, and total orders.
- Gain customers by gender: Analyzing the new customers by gender.
- Lost customers by gender: Analyzing the inactive customers by gender. 
- Total Users by age: Analyzing the total customers by age. 
### User Interactive features:
- Filters: Allows the user to filter by city.
- Slicers: Provides options such as amount and quantity wise sales.
### Recommendations:
- Implement promotions focused on high-demand cuisines during peak sales periods.
- Use demographic insights to personalize marketing efforts and enhance customer loyalty.
### Project Phases and Milestones:
- Data Collection and Preparation: May 2024 -June 2024
- Dashboard Design and Development: July 2024 -September 2024
## Report Snapshots (Power BI Desktop)

![Screenshot 2024-09-26 193759](https://github.com/user-attachments/assets/983a91d8-70e5-4d61-949d-083c8403f283)

![Screenshot 2024-09-26 193816](https://github.com/user-attachments/assets/9134147d-36e5-49fe-81a8-c8b540f310fe)

![Screenshot 2024-09-26 193834](https://github.com/user-attachments/assets/7c3c922f-c4a8-4218-a1c9-d24700197cac)




