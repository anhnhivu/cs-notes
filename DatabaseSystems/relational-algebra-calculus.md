# Relational Algebra
- relation: table
- record or tuple: row
- field or attribute: column

### Overview
- is the basic set of operations -> queries
- result is a new relation -> "closed"

### Unary

SELECT `sigma_DNO=4 (EMPLOYEE)` -> rows

PROJECT `pi_Lname,Fname,Salary (EMPLOYEE)` -> columns (removes duplicate)

RENAME `rho_(First_name, Last_name, Salary) (EMPLOYEE)` or `rho_employess_company (EMPLOYEE)`

### Binary

JOIN
- combine related tuples
- join condition: `r[A_i] = s[B_j]`
- normal = THETA JOIN
- EQUIJOIN: only use `=`
- NATURAL JOIN: denote by `*`, same as EQUIJOIN but both relations have the same attribute names

DIVISION: retrieve the names of employees who work on **all** the projects that 'John Smith' works on
`SSNS(SSN) <- SSN_PNOS / SMITH_PNOS)

### Set theory 
- union compatible: same degree `n` and `dom(A_i) = dom(B_i)`
- UNION and INTERSECTION are commutative, associative


UNION: includes all tuples in S and R, no duplicate

INTERSECTION: in both S and R

DIFFERENCE: `R-S` in R but not in S

CARTESIAN PRODUCT
- create tuples with combined attributes of two relations
- does not have to be "type compatible"
- result has `n + m` attributes, `nR * nS` tuples

Complete set `{sigma, pi, rho, minus, cartesian product}`


### Additional

OUTER JOIN: RIGHT OUTER JOIN, LEFT OUTER JOIN, FULL OUTER JOIN

OUTER UNION: take union of tuples that have some common attributes, but are not union compatible

AGGREGATE FUNCTIONS: SUM, AVERAGE, MAXIMUM, MINIMUM, COUNT

`<grouping attributes> F <function list> (R)` 
`Dno F count ssn, average salary (EMPLOYEE)`

# Relational Calculus
- non procedural or declarative query language
- tuple DRC vs domain DRC
- what result to obtain
- no order
- domain dependent

### TUPLE 
- `{ t | COND(t) }`
- safe expression: finite result

### DOMAIN
- query-by-example
- [TRC/DRC](https://www.geeksforgeeks.org/difference-between-tuple-relational-calculus-trc-and-domain-relational-calculus-drc/)



