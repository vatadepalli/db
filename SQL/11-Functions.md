# Functions

## Create a  Function

* **General Syntax**

        CREATE FUNCTION function_name 
        [ (parameter datatype [, parameter datatype]) ]   
        RETURNS return_datatype  
        BEGIN  
            Declaration_section  
            Executable_section  
        END;  

* **Example**

        DELIMITER $$

        CREATE FUNCTION get_designation_name
        (d_id INT)
        RETURNS VARCHAR(20)
        BEGIN
            DECLARE de_name VARCHAR(20) DEFAULT "";
            SELECT name 
            INTO de_name
            FROM designation
            WHERE id = d_id;
            RETURN de_name;
        END $$

        DELIMITER ;

## Execute a Function

    SELECT id, get_designation1(`d_id`) as DESIGNATION, name 
    FROM 'staff';

## Drop a Function

    DROP FUNCTION [ IF EXISTS ] function_name;  

