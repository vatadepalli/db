# CRUD Operations

## INSERT

* **Insert Into Table (Partial Fields Fields)**

        INSERT INTO table_name 
        ( field1, field2,...fieldN )  
        VALUES  
        ( value1, value2,...valueN );  

        
        INSERT INTO emp
        (id,name) 
        VALUES 
        (7, 'Sonoo');  


* **Insert Into Table (All Fields)**

        INSERT INTO table_name 
        VALUES 
        ( value1, value2,...valueN );  


        INSERT INTO emp 
        VALUES 
        (7, 'Sonoo', 40000);  

* **Insert Multiple Records**

        INSERT INTO cus_tbl  
        (cus_id, cus_firstname, cus_surname)  
        VALUES  
        (5, 'Ajeet', 'Maurya'),  
        (6, 'Deepika', 'Chopra'),  
        (7, 'Vimal', 'Jaiswal');  

## SELECT

* **Select All From Table**

        SELECT *  
        FROM table_name;

* **Select Specific Columns**

        SELECT officer_name, address  
        FROM officers  

* **Select With Conditions**

        SELECT * 
        FROM table_name 
        [WHERE conditions];

* **Multiple Tables**

        SELECT officers.officer_id, students.student_name  
        FROM students  
        INNER JOIN officers  
        ON students.student_id = officers.officer_id; 


## UPDATE 

        UPDATE table_name   
        SET field1=new-value1, field2=new-value2, ...  
        [WHERE Clause]  


        UPDATE cus_tbl  
        SET cus_surname = 'Ambani'  
        WHERE cus_id = 5;  

## DELETE

        DELETE FROM table_name   
        WHERE  
        (Condition specified);  


        DELETE FROM cus_tbl  
        WHERE cus_id = 6;  


