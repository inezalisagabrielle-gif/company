# Window function and Joins
Course: Database Development with PL/SQL (INSY 8311)  
Student Name:INEZA Lisa Gabrielle
Student ID: 28527
Group: A
## Business Problem
This project analyzes car sales for a dealership that sells brands such as BMW ,TESLA and etc.
The goal is to identify top customers, analyze sales trends, detect unsold cars, and segment customers for marketing decisions.
## Database Schema and ER Diagram
Tables: CUSTOMER, PRODUCT, TRANSACTION  
Relationships: CUSTOMER.C_ID → TRANSACTION.C_ID, PRODUCT.P_ID → TRANSACTION.P_ID

![ER Diagram]<img width="1920" height="1080" alt="er_diagram" src="https://github.com/user-attachments/assets/69571e27-c7aa-4221-a246-02a09f06818d" />

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
![INNER JOIN]<img width="1904" height="924" alt="INNER JOIN" src="https://github.com/user-attachments/assets/0a9a8abc-37d7-467d-8aa9-c9d7d1df5fce" />

## LEFT JOIN – Customers Without Purchases
Identifies customers who never bought any car.
![LEFT JOIN]<img width="1906" height="921" alt="LEFT JOIN" src="https://github.com/user-attachments/assets/50d205ed-2f72-425b-be19-ed1fd30ed8cc" />

## RIGHT JOIN – Cars Without Sales
Shows car brands with no transactions.
![RIGHT JOIN]<img width="1911" height="874" alt="right join null" src="https://github.com/user-attachments/assets/78b95df1-e965-442d-8124-73babdb2d2e7" />

## RIGHT JOIN – Cars With Sales
Shows car brands that have been purchased.
![RIGHT JOIN]<img width="1894" height="916" alt="RIGHT JOIN" src="https://github.com/user-attachments/assets/ae19a6de-eb5f-4308-9d8e-971bb300f28a" />

## FULL OUTER JOIN – All Records
Shows matched and unmatched customers and transactions.
![FULL JOIN]<img width="1894" height="941" alt="FULL OUTER JOIN" src="https://github.com/user-attachments/assets/77bc68d5-f460-44a7-98f7-2c3613f4e14b" />

## RANK – Top Customers by Spending
![RANK]<img width="1903" height="909" alt="RANK" src="https://github.com/user-attachments/assets/65d3f078-0c40-4496-baae-180341997155" />

## SUM() OVER – Running Total of Sales
![Running Total]<img width="1896" height="941" alt="aggregate" src="https://github.com/user-attachments/assets/bd1579d5-72d9-42c4-8737-4c84ee1e7b25" />

## LAG – Sales Comparison
![LAG]<img width="1891" height="859" alt="navigation" src="https://github.com/user-attachments/assets/5ce8f7cd-c2d0-47e3-9799-46aa4a7dfd0f" />

## NTILE – Customer Segmentation
![NTILE]<img width="1908" height="890" alt="NTILE" src="https://github.com/user-attachments/assets/709c70db-9507-4980-ab4a-b4611fb3854c" />

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

