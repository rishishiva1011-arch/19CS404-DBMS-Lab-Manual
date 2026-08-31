# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

## Program
```
DECLARE
    a NUMBER := 45;
    b NUMBER := 80;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || a);
    ELSIF b > a THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Both numbers are equal: ' || a);
    END IF;
END;
/
```

## Output
<br>
<img width="1485" height="267" alt="image" src="https://github.com/user-attachments/assets/ea242e75-17c7-4a5b-9897-52a708184052" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

## Program
```
DECLARE
    n NUMBER := 10;
    i NUMBER := 1;
    total NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        total := total + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || total);
END;
/
```

## Output

<img width="1491" height="306" alt="image" src="https://github.com/user-attachments/assets/892acaba-0476-4866-87df-0362a5930a0c" />
---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

## Program
```
DECLARE
    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER;
    fib_series VARCHAR2(200);
BEGIN
    fib_series := a || ', ' || b;

    FOR i IN 3..n LOOP
        c := a + b;
        fib_series := fib_series || ', ' || c;
        a := b;
        b := c;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || fib_series);
END;
/
```

## Output

<img width="1488" height="282" alt="image" src="https://github.com/user-attachments/assets/afb9d7c5-c1b3-4455-993b-d996adfca155" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

## Program
```
DECLARE
    n NUMBER := 1535;
    temp NUMBER;
    rem NUMBER;
    reverse_num NUMBER := 0;
BEGIN
    temp := n;

    WHILE temp > 0 LOOP
        rem := MOD(temp, 10);
        reverse_num := (reverse_num * 10) + rem;
        temp := TRUNC(temp / 10);
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reverse_num);
END;
/
```
## Output
<img width="1488" height="294" alt="image" src="https://github.com/user-attachments/assets/e6b382ae-dfe6-4175-b783-45aefd9ef083" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## Program
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a >= b THEN
        IF a >= c THEN
            largest := a;
        ELSE
            largest := c;
        END IF;
    ELSE
        IF b >= c THEN
            largest := b;
        ELSE
            largest := c;
        END IF;
    END IF;

    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
```

## Output

<img width="1485" height="312" alt="image" src="https://github.com/user-attachments/assets/2f9f87d4-450c-469f-b21a-73de7f797192" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
