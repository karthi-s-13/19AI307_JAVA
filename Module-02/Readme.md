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


# Ex.No:2(B) METHODS

## QUESTION:
Write a method int cube(int x) that calls a method int square(int x) internally to calculate the cube as x * square(x).

## AIM:
To write a Java program that defines a method cube(int x) which internally calls another method square(int x) to compute the cube of a number using the formula: cube = x * square(x).

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a method square(int x) that returns the value of x * x.
4. Create another method cube(int x) that:</BR>
     - Calls square(x)</BR>
     - Multiplies the result by x</BR>
     - Returns the final cube value.</BR>
5. In the main method:</BR>
     - Read or assign a value for x</BR>
     - Call the cube(x) method</BR>
6. Display the cube.
7. End the program.




## PROGRAM:

## SOURCE CODE:
```java
import java.util.*;
public class Main
{
    static int square(int x)
    {
        return x*x;
    }
    static int cube(int x)
    {
        return x*square(x);
    }
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.println(cube(n));
    }
}
```






## OUTPUT:
<img width="282" height="90" alt="image" src="https://github.com/user-attachments/assets/0c98b161-ebf9-4ee6-92cc-084d1e4c1829" />



## RESULT:
The program successfully calculates the cube of a given number by calling the square() method from within the cube() method, demonstrating method calling and reuse in Java.


# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:
Write a Java program to create a class called Person with private instance variables name, age. and country. Provide public getter and setter methods to access and modify these variables.

## AIM:
To write a Java program that defines a class Person with private instance variables name, age, and country, and to provide public getter and setter methods to access and modify these variables.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class named Person.
4. Declare private instance variables:</br>
     - name (String)</br>
     - age (int)</br>
     - country (String)</br>
5. Define public setter methods to assign values to each variable.
6. Define public getter methods to retrieve the values of each variable.
7. In the main method:</br>
     - Create an object of the Person class.</br>
     - Use setter methods to set name, age, and country.</br>
     - Use getter methods to display the values.</br>
8. End the program.




## PROGRAM:


## SOURCE CODE:
```java
import java.util.*;
class Person
{
    private String name;
    private int age;
    private String country;  
    public String getName()
    {
        return name;
    }
    public void setName(String name)
    {
        this.name = name;
    }
    public int getAge()
    {
        return age;
    }
    public void setAge(int age)
    {
        this.age = age;
    }
    public String getCountry()
    {
        return country;
    }
    public void setCountry(String country)
    {
        this.country = country;
    }
}
public class prog
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        Person obj = new Person();
        obj.setName(sc.nextLine());
        obj.setAge(sc.nextInt());
        obj.setCountry(sc.nextLine());
        System.out.println("Person 1");
        System.out.println("Name: " + obj.getName());
        System.out.println("Age: " + obj.getAge());
        System.out.println("Country: " + obj.getCountry());
    }
}
```






## OUTPUT:
<img width="648" height="365" alt="image" src="https://github.com/user-attachments/assets/f3c1492f-5d1b-46b1-9d1d-726b7822232e" />



## RESULT:
The program successfully creates a Person class with private variables and accesses them using getter and setter methods, demonstrating encapsulation in Java.


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
