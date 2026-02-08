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
<img width="1904" height="924" alt="INNER_JOIN" src="https://github.com/user-attachments/assets/6ec31c0a-cc28-4c90-a971-ae97f00b367f" />
![INNER JOIN](screenshots/INNER_JOIN.png)

## LEFT JOIN – Customers Without Purchases
Identifies customers who never bought any car.
<img width="1906" height="921" alt="LEFT_JOIN" src="https://github.com/user-attachments/assets/06a5edff-d0ca-4883-bfce-b2cf17027c19" />
![LEFT JOIN](screenshots/LEFT_JOIN.png)

## RIGHT JOIN – Cars Without Sales
Shows car brands with no transactions.
<img width="1911" height="874" alt="right_join_null" src="https://github.com/user-attachments/assets/b594190f-c2c0-4984-8d8a-9449140b9c0b" />
![RIGHT JOIN](screenshots/RIGHT_JOIN_NULL.png)

## RIGHT JOIN – Cars With Sales
Shows car brands with purchase.
<img width="1894" height="916" alt="RIGHT_JOIN" src="https://github.com/user-attachments/assets/03263519-5e7f-44b6-bc16-099607d412ab" />
![RIGHT JOIN](screenshots/RIGHT_JOIN.png)

## FULL OUTER JOIN – All Records
Shows matched and unmatched customers and transactions.
<img width="1894" height="941" alt="FULL_OUTER JOIN" src="https://github.com/user-attachments/assets/86e28def-17bc-45c3-82f5-e06a41f1f991" />
![FULL JOIN](screenshots/FULL_OUTER-JOIN.png)

## RANK – Top Customers by Spending
The RANK() window function is used to rank customers based on their total car spending.
This helps identify high-value customers for loyalty programs.
<img width="1903" height="909" alt="RANK" src="https://github.com/user-attachments/assets/644f6b19-b9c9-4f0a-8097-f727d8fb9a6a" />
![RANK Result](screenshots/RANK.png)

## AGGREGATE FUNCTION-Running Total of Car Sales
The SUM() OVER() function calculates cumulative car sales over time.
This allows analysis of overall sales growth.
<img width="1896" height="941" alt="aggregate" src="https://github.com/user-attachments/assets/b309ebf9-0fe9-4c2a-a2c7-17efc7ba7ff8" />
![Running Total Result](screenshots/aggregate.png)

## NAVIGATION FUNCTION-Sales Comparison Using LAG
The LAG() function compares each transaction with the previous one.
It helps detect increases or decreases in sales.
<img width="1891" height="859" alt="navigation" src="https://github.com/user-attachments/assets/851c6a8f-b0c1-4ac0-8a4b-3db86bb7fca2" />
![LAG Result](screenshots/navigation.png)

## NTILE FUNCTION-Customer Segmentation Using NTILE
The NTILE(4) function divides customers into four spending groups.
This helps apply targeted marketing strategies.
<img width="1908" height="890" alt="NTILE" src="https://github.com/user-attachments/assets/b8f842f7-a27d-45cd-8c08-08e7f8251b7e" />

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

