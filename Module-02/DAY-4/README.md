
# Ex.No:2(D) VARIABLE SCOPE AND CONSTRUCTOR

## QUESTION:
Write a java code to implement a parameterised constructor that will initialize the id,name,age,gender,doj,dob of the student and print the details using user defined function.

## AIM:
To write a Java program that implements a parameterized constructor to initialize the details of a student such as ID, name, age, gender, date of joining (doj), and date of birth (dob), and to print these details using a user-defined function.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class named Student.
4. Declare instance variables:</br>
     - id (int)</br>
     - name (String)</br>
     - age (int)</br>
     - gender (String)</br>
     - doj (date of joining) (String)</br>
     - dob (date of birth) (String)</br>
5. Create a parameterized constructor to initialize all the variables.
6. Create a user-defined function (e.g., displayDetails()) to print the student's information.
7. In the main method:</br>
     - Read the student details from the user.</br>
     - Create an object of Student using the parameterized constructor.</br>
     - Call the display function to show the student details.</br>
8. End the program. 





## PROGRAM:
 ```
/*
Program to implement a Variable scope and Constructor using Java
Developed by: KARTHIKEYAN S
RegisterNumber: 212224230116
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;
class Student
{
    int id, age;
    String name, gender, doj, dob;
    Student(int id, String name, int age, String gender, String doj, String dob)
    {
        this.id = id;
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.doj = doj;
        this.dob = dob;
    }

    void display()
    {
        System.out.println("--- Student Details ---");
        System.out.println("ID: " + id);
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Gender: " + gender);
        System.out.println("Date of Joining: " + doj);
        System.out.println("Date of Birth: " + dob);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        int id = sc.nextInt();
        String name = sc.next();
        int age = sc.nextInt();
        String gender = sc.next();
        String doj = sc.next();
        String dob = sc.next();
        Student obj = new Student(id, name, age, gender, doj, dob);
        obj.display();
    }
}
```






## OUTPUT:
<img width="632" height="563" alt="image" src="https://github.com/user-attachments/assets/ac9ec43b-4ddc-4ac7-a78e-b0544dc16d5e" />



## RESULT:
The program successfully initializes student details using a parameterized constructor and prints them using a user-defined function.
