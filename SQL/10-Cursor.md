# Cursor

* Steps for creating a cursor.
    1. Declare Cursor
    2. Open Cursor
    3. Fetch Cursor
    4. Close Cursor

## Declare Cursor
* A cursor is a select statement, defined in the declaration section of MySQL.

        DECLARE cursor_name CURSOR FOR  
        SELECT statement;  

## Open Cursor

    Open cursor_name;  


## Fetch Cursor

* Used to fetch the row or the column.
* Variables, comma separated, etc. is stored in a cursor for the result set

        FETCH [ NEXT [ FROM ] ] cursor_name 
        INTO variable_list;  


## Close Cursor

    Close cursor_name;  

## Examples

* **Cursor Using Procedure**

        DELIMITER $$

        CREATE PROCEDURE list_name(INOUT name_list VARCHAR(4000))
        BEGIN
            DECLARE is_done INTEGER DEFAULT 0;
            DECLARE s_name VARCHAR(100) DEFAULT "";
            
            DECLARE stud_cursor CURSOR FOR
            SELECT name FROM table1;

            DECLARE CONTINUE HANDLER FOR NOT FOUND is_done = 1;

            OPEN stud_cursor;
            get_list: Loop
                FETCH stud_cursor INTO s_name;
                IF is_done = 1 THEN
                    LEAVE get_list;
                END IF;
            
                SET name_list = CONCAT(s_name, ";", name_list);
            END LOOP get_list;

            CLOSE stud_cursor;
        END$$

        DELIMITER ;



        SET @name_list = "";
        CALL list_name(@name_list);
        SELECT @name_list;