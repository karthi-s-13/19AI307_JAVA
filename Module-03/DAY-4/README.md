
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
 ```
/*
Program to implement a Interface using Java
Developed by: KARTHIKEYAN S
RegisterNumber: 212224230116 
*/
```

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


