# Ex.No:2(A) CLASS AND OBJECT

## QUESTION:
Define a class Teacher with attributes: name (String), subject (String), and experience (int, years).

## AIM:
To define a Java class named Teacher with attributes name, subject, and experience, and to demonstrate how to create an object of this class and display the details.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Define a class Teacher with the following attributes:name (String),subject (String),experience (int,years)
4.	Create a constructor to initialize these attributes.
5.	Create an object of the Teacher class in the main method.
6.	Display the teacher’s details using print statements.
7.	End the program.






## PROGRAM:
 ```
/*
Program to implement a Class and Objects using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:

```java
import java.util.*;
class Teacher
{
    String name;
    String subject;
    int experience;  
    void print()
    {
        System.out.println("Mr. " + name + " teaches " + subject + " and has " + experience + " years experience.");
    }
}
public class Main
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        Teacher obj = new Teacher();
        obj.name = sc.nextLine();
        obj.subject = sc.nextLine();
        obj.experience = sc.nextInt();
        obj.print();
    }
}
```





## OUTPUT:
<img width="1157" height="296" alt="image" src="https://github.com/user-attachments/assets/78c5c2fc-81bf-434c-b5b9-ff7434685a67" />



## RESULT:
The program successfully defines a Teacher class with attributes for name, subject, and experience, creates an object with the given values, and displays the teacher’s details correctly.

