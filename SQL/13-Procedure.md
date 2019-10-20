# Procedure

## Creating a Procedure

    CREATE PROCEDURE procedure_name
    [ (parameter datatype [, parameter datatype]) ]  
    BEGIN  
        Declaration_section  
        Executable_section  
    END;  

* **Example**

        DELIMITER $$ 

        CREATE PROCEDURE get_student()  
        BEGIN  
            SELECT * FROM table1;  
        END$$  

        DELIMITER ;