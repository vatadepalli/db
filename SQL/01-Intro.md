# MySQL

## Database

* **Create Database**

        CREATE DATABASE database_name;

* **Drop Database**

        DROP DATABASE database_name;

* **Rename Database**

        RENAME DATABASE old_db_name TO new_db_name;

* **Select Database**

        USE DATABASE database_name;

## Table

* **Create Table**

        CREATE TABLE cus_table(
            cus_id INT NOT NULL AUTO_INCREMENT.
            cus_firstname VARCHAR(100) NOT NULL,
            cus_surname VARCHAR(100) NOT NULL,
            PRIMARY KEY(cus_id)
        );

* **Add a Column**

        ALTER TABLE table_name  
        ADD new_column_name column_definition  
        [ FIRST | AFTER column_name ];  


        ALTER TABLE cus_tbl
        ADD cus_age VARCHAR(40) NOT NULL;

* **Add Multiple Columns**

        ALTER TABLE table_name  
        ADD new_column_name column_definition  
        [ FIRST | AFTER column_name ],  
        ADD new_column_name column_definition  
        [ FIRST | AFTER column_name ],  
        ...  
        ;  


        ALTER TABLE cus_tbl  
        ADD cus_address VARCHAR(100) NOT NULL  
        AFTER cus_surname,  
        ADD cus_salary INT(100) NOT NULL  
        AFTER cus_age; 
     
* **Modify Column In The Table**

        ALTER TABLE table_name  
        MODIFY column_name column_definition  
        [ FIRST | AFTER column_name ];  

        
        ALTER TABLE cus_tbl  
        MODIFY cus_surname VARCHAR(50) NULL;  

* **Drop Column In Table**

        ALTER TABLE table_name  
        DROP COLUMN column_name;  


        ALTER TABLE cus_table
        DROP COLUMN cus_address;

* **Rename Column in Table**

        ALTER TABLE table_name  
        CHANGE COLUMN old_name new_name   
        column_definition  
        [ FIRST | AFTER column_name ];


        ALTER TABLE cus_tbl
        CHANGE COLUMN cus_surname cus_title
        VARCHAR(20) NOT NULL;

* **Rename Table**

        ALTER TABLE table_name  
        RENAME TO new_table_name;  


        ALTER TABLE cus_tbl  
        RENAME TO cus_table;

* **Truncate Table**
    * MYSQL TRUNCATE statement removes the complete data without removing its structure.
    * Delete the complete data from a table without removing the table structure.

            TRUNCATE TABLE table_name;

* **Drop Table**

        DROP TABLE  table_name;  

        DROP TABLE  cus_tbl;  

## Views

* **Create View**

        CREATE [OR REPLACE] VIEW view_name AS  
        SELECT columns  
        FROM tables  
        [WHERE conditions]; 


        CREATE VIEW trainer AS  
        SELECT course_name, course_trainer   
        FROM courses;  


* **Update View**

        ALTER VIEW view_name AS  
        SELECT columns  
        FROM table  
        WHERE conditions;  

        ALTER VIEW trainer AS  
        SELECT course_name, course_trainer, course_id  
        FROM courses; 

* **Drop View**

        DROP VIEW [IF EXISTS] view_name;

        DROP VIEW trainer;  

