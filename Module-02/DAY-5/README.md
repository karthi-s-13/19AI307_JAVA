# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:
Create a class Employee with method display(). Inside display(), return the current object using this. Create another method that calls display().printName()

## AIM:
To write a Java program that demonstrates returning the current object using this inside a method. The program should include a method display() that returns the current object and another method that calls display().printName() to show how method chaining works.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.Create a class named Employee.
4. Inside the class, declare an instance variable name.
5. Create a constructor to initialize the employee name.
6. Define a method display() that:</br>
     - Prints a message.</br>
     - Returns the current object using return this;</br>
7. Define a method printName() that prints the employee name.
8. Create another method (e.g., show()) that calls display().printName() to demonstrate method chaining.
9. In the main method:</br>
    - Create an object of Employee.</br>
    - Call the show() method.</br>
10. End the program.		





## PROGRAM:
 ```
/*
Program to implement a Access Modifiers using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.util.*;
class Employee
{
    String name;
    void setName(String name)
    {
        this.name = name;
    }
    Employee display()
    {
        return this;
    }
    void printName()
    {
        System.out.println("Employee Name: " + name);
    }
}
public class Main
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        String empName = sc.nextLine();  
        Employee obj = new Employee();
        obj.setName(empName);
        obj.display().printName();
    }
}
```







## OUTPUT:
<img width="566" height="178" alt="image" src="https://github.com/user-attachments/assets/fe4ccdc6-9dd1-4328-96a2-6644cc01957d" />



## RESULT:
The program successfully demonstrates returning the current object using this inside a method. It also shows how method chaining works by calling display().printName().
