# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36

## Program
```
CREATE OR REPLACE PROCEDURE find_square (
    p_num IN NUMBER
)
IS
    v_square NUMBER;
BEGIN
    v_square := p_num * p_num;
    DBMS_OUTPUT.PUT_LINE('Square of ' || p_num || ' is ' || v_square);
END find_square;
/
BEGIN
    find_square(6);
END;
/
```
## Output

<img width="1875" height="417" alt="image" src="https://github.com/user-attachments/assets/ae3428e9-e1e8-4d53-baf3-318fa828abb2" />


---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120

## Program
```
CREATE OR REPLACE FUNCTION get_factorial (
    p_num IN NUMBER
) RETURN NUMBER
IS
    v_fact NUMBER := 1;
BEGIN
    FOR i IN 1..p_num LOOP
        v_fact := v_fact * i;
    END LOOP;
    RETURN v_fact;
END get_factorial;
/
DECLARE
    v_result NUMBER;
BEGIN
    v_result := get_factorial(5);
    DBMS_OUTPUT.PUT_LINE('Factorial of 5 is ' || v_result);
END;
/
```
## Output

<img width="1872" height="411" alt="image" src="https://github.com/user-attachments/assets/59af0cf0-0bdf-4ccb-993e-d69914a03672" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even

## Program
```
CREATE OR REPLACE PROCEDURE check_even_odd (
    p_num IN NUMBER
)
IS
BEGIN
    IF MOD(p_num, 2) = 0 THEN
        DBMS_OUTPUT.PUT_LINE(p_num || ' is Even');
    ELSE
        DBMS_OUTPUT.PUT_LINE(p_num || ' is Odd');
    END IF;
END check_even_odd;
/
BEGIN
    check_even_odd(12);
END;
/
```

## Output
<img width="1875" height="423" alt="image" src="https://github.com/user-attachments/assets/cdfd06ef-6f85-40b1-abcc-3453e7307fb7" />

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321

## Program
```
CREATE OR REPLACE FUNCTION reverse_number (
    p_num IN NUMBER
) RETURN NUMBER
IS
    v_temp NUMBER := p_num;
    v_rem  NUMBER;
    v_rev  NUMBER := 0;
BEGIN
    WHILE v_temp > 0 LOOP
        v_rem := MOD(v_temp, 10);
        v_rev := (v_rev * 10) + v_rem;
        v_temp := TRUNC(v_temp / 10);
    END LOOP;
    RETURN v_rev;
END reverse_number;
/
DECLARE
    v_result NUMBER;
BEGIN
    v_result := reverse_number(1234);
    DBMS_OUTPUT.PUT_LINE('Reversed number of 1234 is ' || v_result);
END;
/
```
## Output

<img width="1875" height="414" alt="image" src="https://github.com/user-attachments/assets/a48481be-d26d-4f42-aa3c-8b862d94b03d" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

## Program
```
CREATE OR REPLACE PROCEDURE print_table (
    p_num IN NUMBER
)
IS
BEGIN
    DBMS_OUTPUT.PUT_LINE('Multiplication table of ' || p_num || ':');
    FOR i IN 1..10 LOOP
        DBMS_OUTPUT.PUT_LINE(p_num || ' x ' || i || ' = ' || (p_num * i));
    END LOOP;
END print_table;
/
BEGIN
    print_table(5);
END;
/

```

## Output

<img width="1872" height="816" alt="image" src="https://github.com/user-attachments/assets/ef6e8896-1161-480a-a4e6-9eb65c43233a" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
