# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
A jewelry store tracks gold rates for different types of customers. The base class is Customer with attributes like customerId, name, and purchaseWeight (in grams). There are two types of customers: RegularCustomer and PremiumCustomer. RegularCustomer gets a fixed discount of 2% on the gold rate per gram. PremiumCustomer gets a 5% discount plus a special cashback. The base gold rate per gram is input at runtime. For each customer, calculate the final price they pay:

finalPrice = purchaseWeight * (goldRatePerGram - discount)

For PremiumCustomer, additionally show cashback amount (which is 1% of the final price).

## AIM:
To write a Java program using inheritance to calculate the final gold price for different types of customers (Regular and Premium) based on discounts and cashback.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3. Define PremiumCustomer subclass with a 5% discount and 1% cashback on the final price.
4.	Input the base gold rate per gram at runtime.
5.	For each customer, calculate and display the final price (and cashback for premium). 	





## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;
import java.text.DecimalFormat;

class Customer {
    String customerId, name;
    double purchaseWeight, goldRatePerGram;

    Customer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        this.customerId = customerId;
        this.name = name;
        this.purchaseWeight = purchaseWeight;
        this.goldRatePerGram = goldRatePerGram;
    }

    double getDiscountRate() {
        return 0; // Default: no discount
    }

    double calculateFinalPrice() {
        double discountAmount = goldRatePerGram * getDiscountRate() / 100;
        double effectiveRate = goldRatePerGram - discountAmount;
        return purchaseWeight * effectiveRate;
    }

    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: General");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class RegularCustomer extends Customer {
    RegularCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 2.0;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Regular");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class PremiumCustomer extends Customer {
    PremiumCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 5.0;
    }

    double getCashback() {
        return calculateFinalPrice() * 0.01;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Premium");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        System.out.println("Cashback: " + df.format(getCashback()));
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (sc.hasNext()) {
            String type = sc.next();
            String customerId = sc.next();
            String name = sc.next();
            double weight = sc.nextDouble();
            double goldRate = sc.nextDouble();

            Customer c;
            if (type.equalsIgnoreCase("Regular")) {
                c = new RegularCustomer(customerId, name, weight, goldRate);
            } else if (type.equalsIgnoreCase("Premium")) {
                c = new PremiumCustomer(customerId, name, weight, goldRate);
            } else {
                c = new Customer(customerId, name, weight, goldRate);
            }

            c.display();
            System.out.println();
        }

        sc.close();
    }
}
```






## OUTPUT:


<img width="1290" height="746" alt="image" src="https://github.com/user-attachments/assets/5a74858f-886a-4573-98a5-b9cefef91af2" />


## RESULT:
The program successfully calculates and displays the final payable price for both Regular and Premium customers with applicable discounts and cashback.


# Ex.No:3(b) POLYMORPHISM

Write a Java program demonstrating method overriding. Create a class Animal with a method sound(). Subclass it as Dog, Cat, Cow, each overriding the sound() method.## QUESTION:


## AIM:
To write a Java program that demonstrates method overriding using inheritance and polymorphism.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Override the sound() method in each subclass to print specific sounds.
4.	In main(), use an Animal reference to point to each subclass object.
5.	Call the sound() method to demonstrate runtime polymorphism.






## SOURCE CODE:
```java
import java.util.Scanner;

class Animal {
    void sound() {
        System.out.println("Unknown animal");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

class Cow extends Animal {
    @Override
    void sound() {
        System.out.println("Cow moos");
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNextLine()) {
            String input = sc.nextLine().trim();
            if (input.isEmpty()) continue;

            Animal a;
            switch(input.toLowerCase()) {
                case "dog": a = new Dog(); break;
                case "cat": a = new Cat(); break;
                case "cow": a = new Cow(); break;
                default: a = new Animal();
            }
            a.sound();
        }
        sc.close();
    }
}
```






## OUTPUT:
<img width="1215" height="500" alt="image" src="https://github.com/user-attachments/assets/b8a9e748-162e-4206-8746-d2a053094f1e" />



## RESULT:
The program successfully demonstrates method overriding, showing different behaviors of the sound() method for different animal subclasses.



# Ex.No:3(C) ABSTRACTION

## QUESTION:
Description: Create abstract class GameScore with method finalScore(). Subclasses:

ArcadeGame: score = baseScore + (level × 100)

PuzzleGame: score = (attempts ≤ 3) ? 1000 - (attempts × 100) : 500

Input Format:

First line: 1 or 2 Second line: base, level (or attempts)

Output Format:

Final score (int)

## AIM:
To write a Java program using an abstract class GameScore with subclasses ArcadeGame and PuzzleGame, each implementing its own finalScore() method.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Define subclass PuzzleGame where
4.	If attempts ≤ 3, score = 1000 - (attempts × 100)
5.	Else score = 500.
6.	Take user input for game type and relevant values.
7.	Display the final score based on game type.





## SOURCE CODE:
```java
import java.util.*;

abstract class GameScore {
    abstract int finalScore();
}

class ArcadeGame extends GameScore {
    int base, level;
    ArcadeGame(int base, int level) {
        this.base = base;
        this.level = level;
    }
    int finalScore() {
        return base + (level * 100);
    }
}

class PuzzleGame extends GameScore {
    int attempts;
    PuzzleGame(int attempts) {
        this.attempts = attempts;
    }
    int finalScore() {
        if (attempts <= 3)
            return 1000 - (attempts * 100);
        else
            return 500;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int type = sc.nextInt();
        if (type == 1) {
            int base = sc.nextInt();
            int level = sc.nextInt();
            ArcadeGame game = new ArcadeGame(base, level);
            System.out.println(game.finalScore());
        } else if (type == 2) {
            int attempts = sc.nextInt();
            PuzzleGame game = new PuzzleGame(attempts);
            System.out.println(game.finalScore());
        }
    }
}
```






## OUTPUT:
<img width="1147" height="386" alt="image" src="https://github.com/user-attachments/assets/bd53fa2c-3a84-4505-a71b-a5d98040f5ba" />



## RESULT:
The program successfully demonstrates abstraction and inheritance by computing the final score for different game types using subclass-specific logic.



# Ex.No:3(D)    INTERFACE 

## QUESTION:
You are programming bots that analyze weather data. Each bot must implement a common interface and give a prediction.

Bot Types:

SunBot: Predicts "HOT" if temperature > 30, else "MODERATE".

RainBot: Predicts "COLD" if temperature < 20, else "WARM".

Input:

temperature botType (1 for SunBot, 2 for RainBot)Output: Prediction as a string.

## AIM:
To implement weather prediction using interfaces with two bots — SunBot and RainBot.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Take temperature and botType as input.
4.	Use the chosen bot to call predict().
5.	Display the prediction.






## PROGRAM:

## SOURCE CODE:
```java
import java.util.Scanner;

interface WeatherBot {
    String predict(int temperature);
}

class SunBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature > 30) {
            return "HOT";
        } else {
            return "MODERATE";
        }
    }
}

class RainBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature < 20) {
            return "COLD";
        } else {
            return "WARM";
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int temperature = sc.nextInt();
        int botType = sc.nextInt();
        WeatherBot bot;

        if (botType == 1) {
            bot = new SunBot();
        } else {
            bot = new RainBot();
        }

        System.out.println(bot.predict(temperature));
        sc.close();
    }
}
```







## OUTPUT:
<img width="1148" height="334" alt="image" src="https://github.com/user-attachments/assets/ba1e4fa3-84c0-4da6-8ce9-183fc9094552" />



## RESULT:
The program predicts weather conditions using interface implementation and method overriding.



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


