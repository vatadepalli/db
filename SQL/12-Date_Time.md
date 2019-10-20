# Date & Time

| Example              | Format                |
|----------------------|-----------------------|
| '2018-10-18'         | 'YYYY-MM-DD'          |
| '20181018'           | 'YYYYMMDD'            |
| 20181018             | YYYYMMDD              |
| '18-10-18'           | 'YY-MM-DD'            |
| 181018               | YYMMDD                |
| '2018-10-18 5:25:20' | 'YYYY-MM-DD HH:MM:SS' |
| '2018101852520'      | 'YYYYMMDDHHMMSS'      |
| 2018101852520        | YYYYMMDDHHMMSS        |
| '18-10-18 5:25:20'   | 'YY-MM-DD HH:MM:SS'   |
| '18101852520'        | 'YYMMDDHHMMSS'        |
| 18101852520          | YYMMDDHHMMSS          |

## Examples
* **Example 1**

        select id, name, salary, date_format(sal_date,'%d-%m-%y') as new_date_format 
        from staff;  

* **Example 2**

        select id, name, salary, date_format(sal_date,'%d%m%y') as new_date_format 
        from staff;  
