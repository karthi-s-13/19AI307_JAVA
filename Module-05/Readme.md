# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a program to demonstrate chaining of streams (BufferedReader on top of InputStreamReader on top of System.in)

## AIM:
To Write a program to demonstrate chaining of streams (BufferedReader on top of InputStreamReader on top of System.in)

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a BufferedReader object chained with InputStreamReader to read input from the keyboard.
4.	Read the user’s name as a string using readLine().
5.	Read the age as a string, then convert it to an integer using Integer.parseInt().
6.	Display the user details (name and age) on the screen.
7.	Close the BufferedReader and handle any possible IOException.	






## PROGRAM:
 ```
/*
Program to implement a InputStreamReader using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ChainingStreamsExample {
    public static void main(String[] args) {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        try {
            String name = br.readLine(); 

            String ageInput = br.readLine(); 
            int age = Integer.parseInt(ageInput); 

            System.out.println("--- User Details ---");
            System.out.println("Name: " + name);
            System.out.println("Age: " + age);

            br.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```






## OUTPUT:
<img width="701" height="402" alt="image" src="https://github.com/user-attachments/assets/234259fe-b2de-4385-b85f-cb8c70a525f5" />



## RESULT:
Thus, the program to demonstrate chaining of streams is executed successfully.




# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList) into a file.

## AIM:
To Write a Java program to serialize a collection of objects (like ArrayList) into a file.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Start by reading the number of students and their details (id, name, marks) from the user and store each entry as a Student object in a list.
4.	Serialize (save) the list of Student objects into a file using ObjectOutputStream.
5.	Deserialize (load) the list back from the file using ObjectInputStream.
6.	Retrieve the list of Student objects from the file and print each student's details.
7.	Handle exceptions such as IOException and ClassNotFoundException to avoid runtime errors.





## PROGRAM:
 ```
/*
Program to implement a Serialization and Deserialization using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:

```java
import java.io.*;
import java.util.*;

class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class StudentSerializationUserInput {

    public static void serializeStudents(List<Student> students, String fileName) {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) {
            oos.writeObject(students);
            System.out.println("Students serialized successfully into: " + fileName);
        } catch (IOException e) {
            System.out.println("Error during serialization: " + e.getMessage());
        }
    }

    @SuppressWarnings("unchecked")
    public static List<Student> deserializeStudents(String fileName) {
        List<Student> students = null;
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) {
            students = (List<Student>) ois.readObject();
            System.out.println("Students deserialized successfully from: " + fileName);
        } catch (IOException | ClassNotFoundException e) {
            System.out.println("Error during deserialization: " + e.getMessage());
        }
        return students;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        List<Student> students = new ArrayList<>();

        int n = scanner.nextInt();
        scanner.nextLine(); 
        for (int i = 0; i < n; i++) {
            int id = Integer.parseInt(scanner.nextLine());
            String name = scanner.nextLine();
            double marks = Double.parseDouble(scanner.nextLine());
            students.add(new Student(id, name, marks));
        }

        String fileName = "students.dat";

        serializeStudents(students, fileName);

        List<Student> deserializedStudents = deserializeStudents(fileName);

        if (deserializedStudents != null) {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) {
                System.out.println(s);
            }
        }

        scanner.close();
    }
}
```





## OUTPUT:
<img width="1217" height="390" alt="image" src="https://github.com/user-attachments/assets/b503c48d-034d-4cc3-8723-e601c571813f" />



## RESULT:
Thus, the program to serialize a collection of objects (like ArrayList) into a file executed successfully.




# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to count the number of words in a file.

## AIM:
To Write a program to count the number of words in a file.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read a full line of text from the user and write it into a file using BufferedWriter.
4.	Open the same file using BufferedReader to read its contents line by line.
5.	For each line, trim it and split it into words using whitespace as the delimiter.
6.	Count all valid words and accumulate the total word count.
7.	Print the total number of words and close all streams properly.






## PROGRAM:
 ```
/*
Program to implement a File Handling using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.io.*;
import java.util.Scanner;

public class WordCountFile {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String fileName = "input.txt";

        try {
            String input = sc.nextLine();

            BufferedWriter writer = new BufferedWriter(new FileWriter(fileName));
            writer.write(input);
            writer.close();

            BufferedReader reader = new BufferedReader(new FileReader(fileName));
            int wordCount = 0;
            String line;
            while ((line = reader.readLine()) != null) {
                String[] words = line.trim().split("\\s+"); 
                if (!line.trim().isEmpty()) {
                    wordCount += words.length;
                }
            }
            reader.close();

            System.out.println("Number of words in the file: " + wordCount);

        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            sc.close();
        }
    }
}
```






## OUTPUT:
<img width="1137" height="250" alt="image" src="https://github.com/user-attachments/assets/464a8ea0-58a3-4297-a4a1-57645ed42f12" />


## RESULT:
Thus, the program to count the number of words in a file executed successfully.




# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for determine the priority and name of the current thread.

Note : Read the threadname from the User

## AIM:
To Write a java program for determine the priority and name of the current thread.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read a thread name from the user using Scanner.
4.	Get the reference of the current running thread using Thread.currentThread().
5.	Change the name of the current thread to the user-provided name.
6.	Retrieve the current thread’s priority using getPriority().
7.	Print the thread’s priority, updated name, and full thread information.






## PROGRAM:
 ```
/*
Program to implement a Thread Priority Concept using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

public class CurrentThreadInfo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String threadName = sc.nextLine();

        Thread currentThread = Thread.currentThread();

        currentThread.setName(threadName);

        int priority = currentThread.getPriority();

        System.out.println("Priority of Thread: " + priority);
        System.out.println("Name of Thread: " + currentThread.getName());
        System.out.println(currentThread);

        sc.close();
    }
}
```






## OUTPUT:
<img width="810" height="216" alt="image" src="https://github.com/user-attachments/assets/b2db9cf1-77ce-4451-bc07-0b07bbc50590" />



## RESULT:
Thus, the program to determine the priority and name of the current thread is executed successfully.





# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Read N numbers from user, use a fixed thread pool (size 3) to compute the sum of each number multiplied by 2. Return results in order.

## AIM:
To Read N numbers from user, use a fixed thread pool (size 3) to compute the sum of each number multiplied by 2. Return results in order.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read T and then read T numbers from the user and store them in a list.
4.	Create a fixed thread pool with 3 threads using Executors.newFixedThreadPool(3).
5.	For each number, submit a task to the executor that returns the number multiplied by 2.
6.	Store all submitted tasks as Future objects and later retrieve their results using future.get().
7.	Print each processed result and finally shut down the executor service.





## PROGRAM:
 ```
/*
Program to implement a Synchronization concept using Java
Developed by: KARTHIKEYAN S
RegisterNumber:  212224230116
*/
```

## SOURCE CODE:
```java
import java.util.*;
import java.util.concurrent.*;

public class FixedThreadPoolExample {
    public static void main(String[] args) throws InterruptedException, ExecutionException {
        Scanner sc = new Scanner(System.in);

        int T = Integer.parseInt(sc.nextLine());
        List<Integer> numbers = new ArrayList<>();

        for (int i = 0; i < T; i++) {
            numbers.add(Integer.parseInt(sc.nextLine()));
        }

        ExecutorService executor = Executors.newFixedThreadPool(3);

        List<Future<Integer>> futures = new ArrayList<>();

        for (int num : numbers) {
            Future<Integer> future = executor.submit(() -> num * 2);
            futures.add(future);
        }

        for (Future<Integer> future : futures) {
            System.out.println("Result: " + future.get());
        }

        executor.shutdown();
        sc.close();
    }
}
```






## OUTPUT:
<img width="436" height="450" alt="image" src="https://github.com/user-attachments/assets/8e9741e9-ddb5-40e6-9723-7ef79525545b" />



## RESULT:
Thus, the program to Read N numbers from user, use a fixed thread pool (size 3) to compute the sum of each number multiplied by 2 executed successfully.
