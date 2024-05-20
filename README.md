# Amazon Sales Data Analysis -- [E-Commerce Project]
_____________________________________________________

#### Associated with Unified Mentor Private Limited

### TABLE OF CONTENTS:-
__________________________

- [KPI'S REQUIREMENT](#kpis-requirement)
- [CHARTS REQUIREMENT](#charts-requirement)
- [AMAZON SALES SQL QUERIES](#amazon-sales-sql-queries)
- [PIZZA SALES CHARTS](#pizza-sales-charts)
- [CONCLUSION](#conclusion)
- [IMPROVING SALES AND PROFITABILITY](#improving-sales-and-profitability)

### PROBLEM STATEMENT:-
___________________________

In the fast-paced realm of modern business, effectively managing sales has become paramount for companies seeking to reduce costs, maximize profits, and outshine competitors. Today, sales management stands as the cornerstone of commercial success, demanding keen attention and innovative strategies to navigate the complexities of the contemporary market landscape.

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

### AMAZON SALES SQL QUERIES
___________________________

### KPI’S VALUES:-

#### 1. TOTAL ORDERS:-
```
SELECT COUNT(distinct(`ORDER ID`)) AS TOTAL_ORDERS FROM `AMAZON SALES DATA`;
```

#### 2.TOTAL QUANTITY SOLD:-
```
SELECT SUM(`UNITS SOLD`) AS TOTAL_QUANTITY FROM `AMAZON SALES DATA`;
```

#### 3. TOTAL REVENUE:-
```
SELECT SUM(`TOTAL REVENUE`) AS TOTAL_REVENUE FROM `AMAZON SALES DATA`;
```

#### 4. TOTAL COST:-
```
SELECT SUM(`TOTAL COST`) AS TOTAL_COST FROM `AMAZON SALES DATA`;
```

#### 5. TOTAL PROFIT:-
```
SELECT SUM(`TOTAL PROFIT`) AS TOTAL_PROFIT FROM `AMAZON SALES DATA`;
```

#### 6. AVERAGE ORDER VALUE:-
```
SELECT CAST(SUM(`TOTAL REVENUE`) / COUNT(DISTINCT(`ORDER ID`)) AS DECIMAL(10,2)) AS AVERAGE_ORDER_VALUE
FROM `AMAZON SALES DATA`;
```

### PIZZA SALES CHARTS
________________________

#### 1. MONTH VS TOTAL REVENUE & TOTAL PROFIT:-
```
SELECT MONTHNAME(`ORDER DATE`) AS MONTH,
CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE, CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT 
FROM `AMAZON SALES DATA`
GROUP BY MONTH
ORDER BY TOTAL_PROFIT DESC;
```

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

#### 4. ITEM TYPES VS TOTAL REVENUE:-
```
SELECT `ITEM TYPE` AS ITEM_TYPES,CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE
FROM `AMAZON SALES DATA`
GROUP BY ITEM_TYPES
ORDER BY TOTAL_REVENUE DESC;
```

#### 5. ITEM TYPES VS TOTAL PROFIT:-
```
SELECT `ITEM TYPE` AS ITEM_TYPES,CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT
FROM `AMAZON SALES DATA`
GROUP BY ITEM_TYPES
ORDER BY TOTAL_PROFIT DESC;
```

#### 6. REGION VS TOTAL ITEMS SOLD:-
```
SELECT (`REGION`) AS REGION,SUM(`UNITS SOLD`) AS TOTAL_ITEMS_SOLD FROM `AMAZON SALES DATA`
GROUP BY REGION
ORDER BY TOTAL_ITEMS_SOLD DESC;
```

#### 7. REGION VS TOTAL REVENUE & TOTAL PROFIT:-
```
SELECT (`REGION`) AS REGION,
CAST(SUM(`TOTAL COST`) AS DECIMAL(10,2)) AS TOTAL_COST, CAST(SUM(`TOTAL REVENUE`) AS DECIMAL(10,2)) AS TOTAL_REVENUE, CAST(SUM(`TOTAL PROFIT`) AS DECIMAL(10,2)) AS TOTAL_PROFIT FROM `AMAZON SALES DATA`
GROUP BY REGION
ORDER BY TOTAL_PROFIT DESC;
```

### CONCLUSION
___________________

§  The analysis reveals that February and November are peak months for both total revenue and total profit, suggesting the need for targeted strategies during these periods.

§  Offline sales consistently outperform online channels in terms of both total revenue and profit, highlighting the importance of maintaining a strong offline presence.

§  Cosmetics and office products drive the highest total revenue, while cosmetics and household products lead in generating the highest total profit, indicating potential areas for further investment and optimization.

§  Sub-Saharan Africa stands out for surpassing other regions in total cost and total quantity sold, signaling both challenges and opportunities in this region.

§  Sub-Saharan Africa and Europe emerge as the regions with the highest total revenue and total profit, emphasizing the need to focus resources and strategies on these regions for sustained profitability.


### IMPROVING SALES AND PROFITABILITY
___________________________________________

§  Implement targeted marketing campaigns during peak months (February and November) to capitalize on increased consumer spending.

§  Enhance the online sales channel by investing in website optimization, digital advertising, and user experience improvements to better compete with offline sales.

§  Conduct market research to identify emerging trends and consumer preferences in cosmetics, office products, and household items, and develop innovative product offerings to drive sales and profitability.

§  Explore cost-saving measures and supply chain optimizations to reduce total costs, particularly in regions with high expenditures such as Sub-Saharan Africa.

§  Expand market presence and distribution networks in Sub-Saharan Africa and Europe through strategic partnerships, localized marketing strategies, and tailored product o=erings to maximize revenue potential.

§  Continuously monitor sales data, customer feedback, and market trends to identify opportunities for further optimization and refinement of sales and profitability strategies.



--------------------------------------------***************************************---------------------------------------------------


