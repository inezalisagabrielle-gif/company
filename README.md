# Window function and Joins
Course: Database Development with PL/SQL (INSY 8311)  
Student Name:INEZA Lisa Gabrielle
Student ID: 28527
Group: A
## Business Problem
This project analyzes car sales for a dealership that sells brands such as BMW ,TESLA .
The goal is to identify top customers, analyze sales trends, detect unsold cars, and segment customers for marketing decisions.
## Database Schema and ER Diagram
Tables: CUSTOMER, PRODUCT, TRANSACTION  
Relationships: CUSTOMER.C_ID → TRANSACTION.C_ID, PRODUCT.P_ID → TRANSACTION.P_ID

![ER Diagram](ER_DIAGRAM/er_diagram.png)

## Success Criteria

1. Identify top customers by total car spending → RANK()  
   *(Ranks customers based on their total spending to find top buyers)*

2. Analyze cumulative car sales over time → SUM() OVER()  
   *(Calculates running totals of sales to show growth trends)*

3. Measure sales changes between transactions → LAG()  
   *(Compares each transaction to the previous one to find changes)*

4. Segment customers into spending groups → NTILE(4)  
   *(Divides customers into 4 quartiles based on total spending)*

5. Rank customers by demand level → DENSE_RANK()  
   *(Ranks customers without skipping ranks for ties, useful for demand analysis)*
   

## INNER JOIN – Valid Car Sales
Shows actual car sales with customer and product details.
![INNER JOIN](screenshots/INNER_JOIN.png)

## LEFT JOIN – Customers Without Purchases
Identifies customers who never bought any car.
![LEFT JOIN](screenshots/LEFT_JOIN.png)

## RIGHT JOIN – Cars Without Sales
Shows car brands with no transactions.
![RIGHT JOIN](screenshots/RIGHT_JOIN_NULL.png)

## RIGHT JOIN – Cars With Sales
Shows car brands with purchase.
![RIGHT JOIN](screenshots/RIGHT_JOIN.png)

## FULL OUTER JOIN – All Records
Shows matched and unmatched customers and transactions.
![FULL JOIN](screenshots/FULL_OUTER-JOIN.png)

## RANK – Top Customers by Spending
The RANK() window function is used to rank customers based on their total car spending.
This helps identify high-value customers for loyalty programs.
![RANK Result](screenshots/RANK.png)

## AGGREGATE FUNCTION-Running Total of Car Sales
The SUM() OVER() function calculates cumulative car sales over time.
This allows analysis of overall sales growth.
![Running Total Result](screenshots/aggregate.png)

## NAVIGATION FUNCTION-Sales Comparison Using LAG
The LAG() function compares each transaction with the previous one.
It helps detect increases or decreases in sales.
![LAG Result](screenshots/navigation.png)

## NTILE FUNCTION-Customer Segmentation Using NTILE
The NTILE(4) function divides customers into four spending groups.
This helps apply targeted marketing strategies.
![NTILE Result](screenshots/NTILE.png)

## Results Analysis

**Descriptive Analysis:**  
The results show which customers bought the most cars and which car brands such as BMW and TESLA were sold more frequently. The running total query shows how total sales increased over time.

**Diagnostic Analysis:**  
Customers with higher demand values appear more often in the transaction table and have higher total spending. Some car types appear in many transactions, which explains why they have higher sales.

**Prescriptive Analysis:**  
The dealership should reward high-spending customers with loyalty offers and focus marketing on customers with high demand values. Car models that appear rarely in transactions should be promoted to increase sales.

## References

Oracle Corporation. (2024). Oracle Database SQL Language Reference.  
https://docs.oracle.com/en/database/oracle/oracle-database/23/sqlrf/

Oracle Corporation. (2024). Analytic (Window) Functions.  
https://docs.oracle.com/en/database/oracle/oracle-database/23/sqlrf/Analytic-Functions.html

Oracle Corporation. (2024). Oracle SQL Developer User Guide.  
https://docs.oracle.com/en/database/oracle/sql-developer/

Oracle Corporation. (2024). Oracle Database Reserved Words.  
https://docs.oracle.com/en/database/oracle/oracle-database/23/sqlrf/Reserved-Words.html

