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
