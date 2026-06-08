# Ex.No:1(A) INTRODUCTION TO JAVA PROGRAMMING, DATA TYPES, VARIABLES AND OPERATORS

## QUESTION:
Lovely has mastered printing in Java, and now she wants to learn how arithmetic operators work. She’s curious about how Java can add, subtract, multiply, divide, and find remainders of two numbers.

Write a Java program that:

Accepts two integer numbers from the user.

Demonstrates all 5 arithmetic operations:

Addition (+)

Subtraction (-)

Multiplication (*)

Division (/)

Modulus (%)

Displays the result of each operation in a separate line with a clear message.

Input Format
First line: Integer → first number

Second line: Integer → second number

Output Format
Each line shows the result of an arithmetic operation in this format:


Sum = <value>
Difference = <value>
Product = <value>
Quotient = <value>
Remainder = <value>
Ensure integer division and modulus are correctly handled. Assume the second number will not be 0.

## AIM:
To write a Java program that performs arithmetic operations such as addition, subtraction, multiplication, division, and modulus on two integers.

## ALGORITHM :
1.Start the program.

2.Import the Scanner class to read input from the user.

3.Declare two integer variables to store the numbers.

4.Read the two integer values from the user.

5.Perform arithmetic operations: addition, subtraction, multiplication, division, and modulus.

6.Display the results of each operation.

7.Stop the program.



## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## Sourcecode.java:
```py
import java.util.Scanner;
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int a=sc.nextInt();
        int b=sc.nextInt();
        int sum=a+b;
        int diff=a-b;
        int prod=a*b;
        int quo=a/b;
        int rem=a%b;
        System.out.println("Sum = " + sum);
        System.out.println("Difference = " + diff);
        System.out.println("Product = " + prod);
        System.out.println("Quotient = " + quo);
        System.out.println("Remainder = " + rem);

        sc.close();
    }
}
```




## OUTPUT:
<img width="1252" height="354" alt="image" src="https://github.com/user-attachments/assets/b42fd06e-6ade-4df2-a3a3-8d25a65b9d7e" />


## RESULT:
Thus the Java program to perform arithmetic operations using variables and operators was implemented and executed successfully.
