# er_diagram_sql_customer_employee_relationship
Established a relationship between customers, employees, departments, invoices etc., using MySQL

Initial understanding of data:
From the given datasets, I normalized them to arrive at individual table structures as mentioned in the data dictionary. I converted the given .txt files into .csv and followed the data dictionary to normalize each table into individual .csv files. I was able to get 10 tables namely BRAND, CUSTOMER, DEPARTMENT, EMPLOYEE, INVOICE, LINE, PRODUCT, SALARY_HISTORY, SUPPLIES and VENDOR. From the initial understanding, the data represents a relationship between a company with its customers and vendors, with a set of employees working with companies to satisfy their requirements with the help of vendors. There are few dependencies between tables.

Data Munging / Cleaning:
Some tables need munging with respect to various factors like duplicate values, bad characters, missing data and date formats. 

Duplicate values: I observed lot of duplicate values in almost all the tables. I was able to get rid of them using Excel’s “Remove duplicate” option. 

Bad characters: In PRODUCT table, under PROD_QOH column, there were some bad characters, which were removed to reflect the true values.
  
Missing values: There were a few missing fields (“-”) in SALARY_HISTORY table under SAL_END column. Maybe that means the employee is still working with the company. I tried replacing “-” with NULL values but Mysql was only accepting Date formats for that particular column. So, I replaced those missing values with ‘2018-12-12’. 
 
Date format: I found that date fields in EMPLOYEE, INVOICE, SALARY_HISTORY tables under EMP_HIREDATE, INV_DATE, SAL_FROM and SAL_END fields are not in defined data format. So, I changed the format of those fields to YYYY-MM-DD.
 

DDL & ER Diagram (Logical and Physical):
I established a csv database connection with Dbeaver to access the cleaned files to create logical ER diagram. I assigned necessary CONSTRAINTS, PRIMARY AND FOREIGN KEYS for each table and was able to obtain the below logical ER diagram. When I used csv database connection, each column was imported as string datatype. Since, I was creating a logical model, I didn’t find a necessity to change the data types yet.
 
For physical mode, I worked on creating DDL file with all the constraints clearly mentioned. The tables were created with CONSTRAINTS, PRIMARY AND FOREIGN KEYS. I created a MySql database connection and created DDL, I defined primary, foreign keys and constraints for each table and created the ER diagram. 

Inserting values:
Once the DDL is ready, I wanted to convert csv tables to sql queries using an online tool: http://convertcsv.com/csv-to-sql.htm . This tool accepts individual csv file and gives us the INSERT VALUES from commands for each row in respective tables. It made my job very easy to insert all the values displaying sql queries. I was able to insert all values into Mysql. After importing the data into respective tables, I started working on the queries.
