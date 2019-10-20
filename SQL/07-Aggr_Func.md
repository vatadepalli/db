# Aggregate Functions

## count()
* NON-NULL values will be counted.
* **General Syntax**

        SELECT COUNT (aggregate_expression)  
        FROM table_name  
        [WHERE conditions];  

* **Example**

        SELECT COUNT(officer_name)  
        FROM officers;  

## sum()

* **General Syntax**

        SELECT SUM(aggregate_expression)  
        FROM tables  
        [WHERE conditions];  

* **Example**

        SELECT SUM (working_hours) AS "Total working hours"  
        FROM employees  
        WHERE working_hours > 5;  


## avg()

* **General Syntax**

        SELECT AVG(aggregate_expression)  
        FROM tables  
        [WHERE conditions];  

* **Examples**

        SELECT AVG(working_hours) AS "Avg working hours"  
        FROM employees  
        WHERE working_hours > 5;  

## min()

* **General Syntax**

        SELECT MIN (aggregate_expression)  
        FROM tables  
        [WHERE conditions];  

* **Example**

        SELECT MIN (working_hours) AS "Minimum working hours"  
        FROM employees;  

## max()

* **General Syntax**

        SELECT MAX(aggregate_expression)  
        FROM tables  
        [WHERE conditions];  


* **Example**

        SELECT MAX (working_hours) AS "Maximum working hours"  
        FROM employees;  


## first
* Return the first value of the selected column.

* **General Syntax**

        SELECT column_name  
        FROM table_name  
        LIMIT 1;  

* **Examples**

        SELECT officer_name   
        FROM officers  
        LIMIT 1;  


        SELECT officer_name   
        FROM officers  
        LIMIT 2;  

## last

* **General Syntax**

        SELECT column_name  
        FROM table_name  
        ORDER BY column_name DESC  
        LIMIT 1;  

* **Example**

        SELECT officer_name   
        FROM officers  
        ORDER BY officer_id DESC  
        LIMIT 1;  

