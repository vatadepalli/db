# Conditions

## AND
* Used with SELECT, INSERT, UPDATE, DELETE

        WHERE condition1  
        AND condition2  
        ...  
        AND condition_n;  


        SELECT *  
        FROM cus_tbl  
        WHERE cus_firstname = 'Ajeet'  
        AND cus_id > 3;  


## OR

        SELECT *  
        FROM cus_tbl  
        WHERE cus_firstname = 'Ajeet'  
        OR cus_id > 100;  


## AND OR

        SELECT *  
        FROM students  
        WHERE (course_name = 'Java' AND student_name = 'Aryan')  
        OR (student_id < 2); 

## LIKE
* LIKE condition is used to perform pattern matching to find the correct result. 
* It is used in SELECT, INSERT, UPDATE and DELETE statement 
    * with the combination of WHERE clause.

* **%**

        SELECT officer_name  
        FROM officers  
        WHERE address LIKE 'Luck%'; 
        
        // Lucknow

* **_**

        SELECT officer_name  
        FROM officers  
        WHERE address LIKE 'Luc_now';  
        
        // Lucknow

* **NOT**

        SELECT officer_name  
        FROM officers  
        WHERE address NOT LIKE 'Luck%';  


## IN
* Reduce the use of Multiple OR

        SELECT *  
        FROM officers  
        WHERE officer_name IN ('Ajeet', 'Vimal', 'Deepika');  

## NOT
* **NOT IN**

        SELECT *  
        FROM officers  
        WHERE officer_name NOT IN ('Ajeet','Vimal','Deepika');  

* **NOT NULL**

        SELECT *  
        FROM officers  
        WHERE officer_name IS NOT NULL;  

* **NOT LIKE**

        SELECT *  
        FROM officers  
        WHERE officer_name NOT LIKE 'A%';  

* **NOT BETWEEN**

        SELECT *  
        FROM officers  
        WHERE officer_id NOT BETWEEN 3 AND 5;  

## IS NULL

* **NULL**

        SELECT *  
        FROM officers  
        WHERE officer_name IS NULL;  

* **NOT NULL**

        SELECT *  
        FROM officers  
        WHERE officer_name IS NOT NULL;  

## BETWEEN
* Bounds inclusive

* **Between**

        SELECT *  
        FROM officers  
        WHERE officer_id BETWEEN 1 AND 3;  

* **Between Date**

        SELECT *  
        FROM employees  
        WHERE working_date BETWEEN 
        CAST ('2015-01-24' AS DATE) AND CAST ('2015-01-25' AS DATE);