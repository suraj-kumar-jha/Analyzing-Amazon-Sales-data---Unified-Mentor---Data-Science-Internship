# Amazon Sales Data Analysis -- [E-Commerce Project]
_____________________________________________________

#### Associated with Unified Mentor Private Limited

### Tools Used:-
--------------------------

1. Tableau: For data visualization and interactive dashboards.
   
2. MySQL: For database management and data querying.
   
3. MS Excel: For data cleaning and analysis.
   
4. MS Word: For documenting findings and creating reports.

---------------------------
### TABLE OF CONTENTS:-
__________________________

- [KPI'S REQUIREMENT](#kpis-requirement)
- [CHARTS REQUIREMENT](#charts-requirement)
- [AMAZON SALES SQL QUERIES](#amazon-sales-sql-queries)
- [SALES CHARTS](#sales-charts)
- [CONCLUSION](#conclusion)
- [IMPROVING SALES AND PROFITABILITY](#improving-sales-and-profitability)
- [DASHBOARD 1](#dashboard-1)
- [DASHBOARD 2](#dashboard-2)

---------------------------
### PROBLEM STATEMENT:-
___________________________

In the fast-paced realm of modern business, effectively managing sales has become paramount for companies seeking to reduce costs, maximize profits, and outshine competitors. Today, sales management stands as the cornerstone of commercial success, demanding keen attention and innovative strategies to navigate the complexities of the contemporary market landscape.

---------------------------
### KPI’S REQUIREMENT
_______________________

#### 1. Total Orders:-

• The number of orders received within a specific time.

• Just count how many orders were placed during the chosen time period.

#### 2. Total Quantity Sold:-

• The total amount of products sold within a specific time.

• Add up the quantities of all items sold during the chosen time period.

#### 3. Total Revenue:-

• The total money earned from sales within a specific time.

• Multiply the price of each item sold by the quantity sold, then add up all these values.

#### 4. Total Cost:-

• The total amount spent on producing or acquiring the goods sold.

• Add up all the costs related to making, buying, marketing, and distributing the products sold during the specified time.

#### 5. Total Profit:-

• The overall profit earned from sales after deducting all costs.

• Subtract the Total Cost from the Total Revenue. This gives you the profit made from all sales.

#### 6. Average Order Value:-

• The average amount of money spent in each order.

• Divide the Total Revenue by the Total Orders. This gives you the average amount of money customers spend in each order.

<img width="636" alt="Screenshot 2024-05-20 at 8 38 43 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/ea4f3467-532b-4d25-a5b2-0d1c22595dae">

---------------------------
### CHARTS REQUIREMENT
_________________________

#### 1. Month vs Total Revenue & Total Profit:-
• Analyzing monthly revenue and profit trends helps understand seasonal variations and overall business performance.

#### 2. Sales Channel vs Total Revenue:
• Comparing revenue from different sales channels informs resource allocation and marketing strategies to maximize sales.

#### 3. Sales Channel vs Total Profit:
• Evaluating profit by sales channel guides decisions on channel optimization to enhance overall profitability.

#### 4. Item Types vs Total Revenue:
• Analyzing revenue by product category informs inventory management and pricing strategies.

#### 5. Item Types vs Total Profit:
• Comparing profitability of product categories guides decisions on pricing and resource allocation.

#### 6. Region vs Total Items Sold:
• Analyzing sales volume by region helps tailor marketing and stocking decisions to regional demand.

#### 7. Region vs Total Revenue & Total Profit:
• Comparing revenue and profit by region guides strategic decisions on market penetration and resource allocation.

---------------------------
### AMAZON SALES SQL QUERIES
___________________________

### KPI’S VALUES:-

#### 1. TOTAL ORDERS:-
```
SELECT COUNT(distinct(`ORDER ID`)) AS TOTAL_ORDERS FROM `AMAZON SALES DATA`;
```
<img width="144" alt="Screenshot 2024-05-20 at 9 05 46 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/e00b5532-43d3-4aaf-bd1d-b48c7b3fd97e">

#### 2.TOTAL QUANTITY SOLD:-
```
SELECT SUM(`UNITS SOLD`) AS TOTAL_QUANTITY FROM `AMAZON SALES DATA`;
```
<img width="199" alt="Screenshot 2024-05-20 at 9 06 11 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/16de1a5d-db04-41e3-8403-223230dddba6">

#### 3. TOTAL REVENUE:-
```
SELECT SUM(`TOTAL REVENUE`) AS TOTAL_REVENUE FROM `AMAZON SALES DATA`;
```
<img width="202" alt="Screenshot 2024-05-20 at 9 06 36 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/fa51b830-f37e-45b2-819c-9920584fa164">

#### 4. TOTAL COST:-
```
SELECT SUM(`TOTAL COST`) AS TOTAL_COST FROM `AMAZON SALES DATA`;
```
<img width="197" alt="Screenshot 2024-05-20 at 9 07 01 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/cdf32b97-f3e7-41ca-8c6c-cec12c48b69f">

#### 5. TOTAL PROFIT:-
```
SELECT SUM(`TOTAL PROFIT`) AS TOTAL_PROFIT FROM `AMAZON SALES DATA`;
```
<img width="197" alt="Screenshot 2024-05-20 at 9 07 27 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/167fd931-8cce-4f27-a9af-efca701a66c1">

#### 6. AVERAGE ORDER VALUE:-
```
SELECT CAST(SUM(`TOTAL REVENUE`) / COUNT(DISTINCT(`ORDER ID`)) AS DECIMAL(10,2)) AS AVERAGE_ORDER_VALUE
FROM `AMAZON SALES DATA`;
```
<img width="233" alt="Screenshot 2024-05-20 at 9 08 00 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/96e0c70e-35d4-4982-961a-de0644acd769">

---------------------------
### SALES CHARTS
________________________

#### 1. MONTH VS TOTAL REVENUE & TOTAL PROFIT:-
```
SELECT MONTHNAME(`ORDER DATE`) AS MONTH,
CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE, CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT 
FROM `AMAZON SALES DATA`
GROUP BY MONTH
ORDER BY TOTAL_PROFIT DESC;
```
<img width="351" alt="Screenshot 2024-05-20 at 8 43 31 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/49fdb9bb-9497-4565-addf-ca73d1e374be">

<img width="591" alt="Screenshot 2024-05-20 at 8 45 05 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/57770a57-3c18-4227-bcc8-b6cbaee4f577">

<img width="593" alt="Screenshot 2024-05-20 at 8 46 57 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/139ce61f-3681-4a00-9baf-7bf7d1c15116">

---------------------------

#### 2. SALES CHANNEL VS TOTAL REVENUE:-
```
SELECT `SALES CHANNEL` AS SALES_CHANNEL,CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE
FROM `AMAZON SALES DATA` 
GROUP BY SALES_CHANNEL 
ORDER BY TOTAL_REVENUE DESC;
```

#### 3. SALES CHANNEL VS TOTAL PROFIT:-
```
SELECT `SALES CHANNEL` AS SALES_CHANNEL,CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT
FROM `AMAZON SALES DATA` 
GROUP BY SALES_CHANNEL 
ORDER BY TOTAL_PROFIT DESC;
```
<img width="288" alt="Screenshot 2024-05-20 at 8 57 27 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/3cf93642-f6d2-4ff6-8ee7-ffa6f979076c">

<img width="285" alt="Screenshot 2024-05-20 at 8 58 55 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/90053ede-afa5-4c14-bc44-15e7f9204438">

<img width="528" alt="Screenshot 2024-05-20 at 8 51 25 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/50eea3de-1d88-429d-9377-b67408bc55e1">


---------------------------

#### 4. ITEM TYPES VS TOTAL REVENUE:-
```
SELECT `ITEM TYPE` AS ITEM_TYPES,CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE
FROM `AMAZON SALES DATA`
GROUP BY ITEM_TYPES
ORDER BY TOTAL_REVENUE DESC;
```

<img width="313" alt="Screenshot 2024-05-20 at 8 53 51 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/d1d1cd61-f967-4328-be5a-bfaa663bbc2a">

<img width="546" alt="Screenshot 2024-05-20 at 8 54 20 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/73a30ca5-62e8-495e-bf3f-36a43564652f">

---------------------------

#### 5. ITEM TYPES VS TOTAL PROFIT:-
```
SELECT `ITEM TYPE` AS ITEM_TYPES,CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT
FROM `AMAZON SALES DATA`
GROUP BY ITEM_TYPES
ORDER BY TOTAL_PROFIT DESC;
```
<img width="265" alt="Screenshot 2024-05-20 at 9 00 35 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/f606621e-9d5e-4d89-b539-9297f9d6991f">

<img width="535" alt="Screenshot 2024-05-20 at 9 01 03 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/6b4d89a9-b902-4482-990e-7ba23aaef4e8">

---------------------------

#### 6. REGION VS TOTAL ITEMS SOLD:-
```
SELECT (`REGION`) AS REGION,SUM(`UNITS SOLD`) AS TOTAL_ITEMS_SOLD FROM `AMAZON SALES DATA`
GROUP BY REGION
ORDER BY TOTAL_ITEMS_SOLD DESC;
```
<img width="465" alt="Screenshot 2024-05-20 at 9 02 14 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/f1bd2240-57c1-4fe9-8430-2f5a18bdc62e">

<img width="613" alt="Screenshot 2024-05-20 at 9 02 43 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/4ed0e382-cba2-4d5b-ab87-c7b86c3f3714">

---------------------------

#### 7. REGION VS TOTAL REVENUE & TOTAL PROFIT:-
```
SELECT (`REGION`) AS REGION,
CAST(SUM(`TOTAL COST`) AS DECIMAL(10,2)) AS TOTAL_COST, CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE, CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT FROM `AMAZON SALES DATA`
GROUP BY REGION
ORDER BY TOTAL_PROFIT DESC;
```
<img width="593" alt="Screenshot 2024-05-20 at 9 03 46 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/3e31b0eb-d9be-4ed1-9aba-efd3a90aca3e">

<img width="629" alt="Screenshot 2024-05-20 at 9 04 09 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/8f25683e-20fe-4f5a-aa48-34a932847cd6">

----------------
### Dashboard 1
________________

<img width="639" alt="Screenshot 2024-05-20 at 9 13 13 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/def5f561-3300-4bb9-a53b-6828d19390e5">

----------------
### Dashboard 2
________________

<img width="634" alt="Screenshot 2024-05-20 at 9 13 49 AM" src="https://github.com/suraj-kumar-jha/Analyzing_Amazon_Sales_data---Unified_Mentor---Data_Science-Internship/assets/155900363/3fdf93ee-5345-4048-a36b-a36aed81b8ec">

-------------------
### CONCLUSION
___________________

§  The analysis reveals that February and November are peak months for both total revenue and total profit, suggesting the need for targeted strategies during these periods.

§  Offline sales consistently outperform online channels in terms of both total revenue and profit, highlighting the importance of maintaining a strong offline presence.

§  Cosmetics and office products drive the highest total revenue, while cosmetics and household products lead in generating the highest total profit, indicating potential areas for further investment and optimization.

§  Sub-Saharan Africa stands out for surpassing other regions in total cost and total quantity sold, signaling both challenges and opportunities in this region.

§  Sub-Saharan Africa and Europe emerge as the regions with the highest total revenue and total profit, emphasizing the need to focus resources and strategies on these regions for sustained profitability.

-------------------------------------------
### IMPROVING SALES AND PROFITABILITY
___________________________________________

§  Implement targeted marketing campaigns during peak months (February and November) to capitalize on increased consumer spending.

§  Enhance the online sales channel by investing in website optimization, digital advertising, and user experience improvements to better compete with offline sales.

§  Conduct market research to identify emerging trends and consumer preferences in cosmetics, office products, and household items, and develop innovative product offerings to drive sales and profitability.

§  Explore cost-saving measures and supply chain optimizations to reduce total costs, particularly in regions with high expenditures such as Sub-Saharan Africa.

§  Expand market presence and distribution networks in Sub-Saharan Africa and Europe through strategic partnerships, localized marketing strategies, and tailored product o=erings to maximize revenue potential.

§  Continuously monitor sales data, customer feedback, and market trends to identify opportunities for further optimization and refinement of sales and profitability strategies.



--------------------------******************************-----------------------------


