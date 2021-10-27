## Create views in MySQL

```sql
CREATE VIEW employee_project AS  
   SELECT SSN, FNAME, MINIT, LNAME, PNUMBER, PNAME, HOURS 
		FROM EMPLOYEE E 
		JOIN WORKS_ON W ON E.SSN = W.ESSN
		JOIN PROJECT P ON W.PNO = P.PNUMBER
		WHERE P.PLOCATION = 'Houston'; 

SELECT * FROM employee_project;  
```

```sql
CREATE VIEW e_dependent AS  
	SELECT E.SSN, E.FNAME, E.MINIT, E.LNAME,
		COUNT(D.DEPENDENT_NAME) AS NUMBER_OF_DEPENDENTS
		FROM EMPLOYEE E 
		JOIN DEPENDENT D ON E.SSN = D.ESSN
		GROUP BY D.ESSN
		HAVING NUMBER_OF_DEPENDENTS > 2; 

SELECT * FROM e_dependent; 
```

```sql
CREATE 
	  -- DEFINER = CURRENT_USER -- read-only
    -- SQL SECURITY DEFINER
VIEW july_bdate AS 
	SELECT E.LNAME, E.BDATE, E.SEX
    FROM EMPLOYEE E
		WHERE MONTH(BDATE) = 07;

SELECT * FROM july_bdate; 
```

## Create a trigger
```sql
delimiter //
DROP TRIGGER IF EXISTS age//
CREATE TRIGGER age 
  BEFORE INSERT
  ON EMPLOYEE
  FOR EACH ROW
  IF (YEAR(CURRENT_DATE) - YEAR(NEW.BDATE) <= 18) THEN
	  SIGNAL SQLSTATE '50001' 
	  SET MESSAGE_TEXT = 'Employee must be older than 18.';
  END IF; //
delimiter ;

INSERT INTO EMPLOYEE (`SSN`, `BDATE`) VALUES (123721232, '2008-12-08');
```

## Create a stored function
```sql
DELIMITER //
DROP FUNCTION IF EXISTS number_of_projects //

CREATE FUNCTION number_of_projects (ssn NUMERIC) 
RETURNS INT 
DETERMINISTIC
	BEGIN
		DECLARE NUM INT;
		SELECT COUNT(*) INTO NUM
		FROM WORKS_ON
		GROUP BY ESSN
		HAVING ESSN = ssn;
		RETURN NUM;
	END; //
DELIMITER ;  

SELECT number_of_projects(123456789);
```

## Create a stored procedure 
```sql
DELIMITER //
drop procedure if exists employee_detail //

CREATE PROCEDURE employee_detail()
   BEGIN    
      SELECT ssn, CONCAT(fname, ' ', minit, ' ', lname) AS fullname, dname, salary
      FROM EMPLOYEE E
      JOIN DEPARTMENT D ON E.DNO = E.DNO;
   END;  //
   
DELIMITER ;


call employee_detail();  
```
