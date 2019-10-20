# Clauses

## WHERE
* Conditions.
    * Used with SELECT, INSERT, UPDATE, DELETE to filter results.

* **Single Condition**

        SELECT *  
        FROM officers  
        WHERE address = 'Mau';  

* **AND**

        SELECT *  
        FROM officers  
        WHERE address = 'Lucknow'  
        AND officer_id < 5;  

* **OR**

        SELECT *  
        FROM officers  
        WHERE address = 'Lucknow'  
        OR address = 'Mau';  

* **AND & OR**

        SELECT *  
        FROM officers  
        WHERE (address = 'Mau' AND officer_name = 'Ajeet')  
        OR (officer_id < 5);  

## DISTINCT
* Remove duplicate records. - Fetch only unique records.
* Note:
    * If you put only one expression in the DISTINCT clause, the query will return the unique values for that expression.
    * If you put more than one expression in the DISTINCT clause, the query will retrieve unique combinations for the expressions listed.
    * In MySQL, the DISTINCT clause doesn't ignore NULL values.
* **Single Expression**

        SELECT DISTINCT expressions  
        FROM tables  
        [WHERE conditions];  

* **Multiple Expressions**

        SELECT DISTINCT officer_name, address  
        FROM officers;  

## FROM
* Is used to select some records from a table.
* Also be used to retrieve records from multiple tables using JOIN condition.

* **General Syntax**

        SELECT *
        FROM table1  
        [ { INNER JOIN | LEFT [OUTER] JOIN | RIGHT [OUTER] JOIN } table2  
        ON table1.column1 = table2.column1 ]  

* **Data from One Table**

        SELECT *  
        FROM officers  
        WHERE officer_id <= 3;  

* **Two Tables - Inner Join**

        SELECT officers.officer_id, students.student_name  
        FROM students  
        INNER JOIN officers  
        ON students.student_id = officers.officer_id;  

* **Two Tables - Outer Join**

        SELECT officers.officer_id, students.student_name  
        FROM officers  
        LEFT OUTER JOIN students  
        ON officers.officer_id = students.student_id;  

## ORDER BY 

* Sort the records in ascending (default) or descending order.

* **General Syntax**

        SELECT expressions  
        FROM tables  
        [WHERE conditions]  
        ORDER BY expression [ ASC | DESC ]; 

* **Default ASC**

        SELECT *  
        FROM officers  
        WHERE address = 'Lucknow'  
        ORDER BY officer_name;  

* **ASC**

        SELECT *  
        FROM officers  
        WHERE address = 'Lucknow'  
        ORDER BY officer_name ASC;  

* **DESC**

        SELECT *  
        FROM officers  
        WHERE address = 'Lucknow'  
        ORDER BY officer_name DESC;  

* **ASC & DESC**

        SELECT officer_name, address  
        FROM officers  
        WHERE officer_id < 5  
        ORDER BY officer_name DESC, address ASC;  


## GROUP BY

* Collect data from multiple records and group the result by one or more column.
* Used With
    * Generally used in a SELECT statement.
    * Can also use some aggregate functions like COUNT, SUM, MIN, MAX, AVG etc. on the grouped column.
* Expresions in SELECT
    * Specifies the expressions that are not excapsulated within an aggregate function & must be included in the GROUP BY clause.

* **General Syntax**

        SELECT expression1, expression2, ... expression_n,   
        aggregate_function (expression)  
        FROM tables  
        [WHERE conditions]  
        GROUP BY expression1, expression2, ... expression_n;  

* **Group By with Count(\*)**

    * Shows distinct addresses, and number of officers in that address.

            SELECT address, COUNT(*)  
            FROM   officers   
            GROUP BY address;   

* **With Sum**

    * Will group all results by name. - Adds Hours with same name.

            SELECT emp_name, SUM(working_hours) AS "Total working hours"  
            FROM employees  
            GROUP BY emp_name;  

* **With Min**

    * Show min working hours of each employee.

            SELECT emp_name, MIN(working_hours) AS "Minimum working hour"  
            FROM employees  
            GROUP BY emp_name;  

* **With Avg**

    * Shows average of all hours / employee

            SELECT emp_name, AVG(working_hours) AS "Average working hour"  
            FROM employees  
            GROUP BY emp_name;  

## HAVING

* Used with GROUP BY clause. 
* It always returns the rows where condition is TRUE.
* It can also be used with COUNT, MIN, MAX and AVG functions.

* **General Syntax**

        SELECT expression1, expression2, ... expression_n,   
        aggregate_function (expression)  
        FROM tables  
        [WHERE conditions]  
        GROUP BY expression1, expression2, ... expression_n  
        HAVING condition;  

* **With Sum**

        SELECT emp_name, SUM(working_hours) AS "Total working hours"  
        FROM employees  
        GROUP BY emp_name  
        HAVING SUM(working_hours) > 5;  