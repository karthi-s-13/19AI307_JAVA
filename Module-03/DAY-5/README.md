
# Ex.No:3(E) INNER CLASS

## QUESTION:
Write a Java program to create an inner class and access it from the outer class.

## AIM:
To demonstrate accessing an inner class from an outer class in Java.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	In main(), create an object of the outer class.
4.	Use it to create an object of the inner class.
5.	Call the inner class method.






## PROGRAM:
 ```
/*
Program to implement a InnerClass using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

class OuterClass {
    String name;

    OuterClass(String name) {
        this.name = name;
    }

    void display() {
        InnerClass inner = new InnerClass();
        inner.showMessage();
    }

    class InnerClass {
        void showMessage() {
            System.out.println("Hello, " + name + "! This message is from the Inner Class.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("");
        String input = scanner.next();
        scanner.close();

        OuterClass outer = new OuterClass(input);
        outer.display();
    }
}
```





## OUTPUT:
<img width="1223" height="347" alt="image" src="https://github.com/user-attachments/assets/5daa14f0-598f-44ca-a98a-ba2e4b762976" />



## RESULT:
The program successfully accesses and prints data from the inner class using the outer class.



