# Assignment: Activity – 7.1 Exceptions

## My Lab Objective

The goal of this lab is to write an application in Java that uses *Exception notion* to convert the amount of steps into miles. The conversion rate is 2,000 steps = 1 mile, meaning the software defines the method name *stepsToMiles()*, which allows steps convert to miles. When the user enters a negative number to the amount of steps. The application will raise an exception displaying a message of, "Exception: Negative step count entered." My objective in this lab is to learn how Java exception handling works, and how to employ that into try-catch blocks to carefully handle any user input errors to avoid program crashes. Then returning results formatted to two decimal places.

## This is my Assignment 7.1 Code

```
import java.util.Scanner;

public class StepCounter {
    
    public static double stepsToMiles(int steps) throws Exception {
        if (steps < 0) {
            throw new Exception("Exception: Negative step count entered.");
        }
        return steps / 2000.0; // 2000 steps = 1 mile
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int steps = sc.nextInt();

        try {
            double miles = stepsToMiles(steps);
            System.out.printf("%.2f\n", miles);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

## My Flowchart:


## Challenges Faced
The challenges I faced were understanding how to throw and catch exceptions in Java. Compile-time had technical problems at first was caused by failure, and resolved by throwing an exception in the method header. Third was examining how exceptions can spread between different procedures I dealt with, which was easily able to fix. Fourth was making sure the output was formatted correctly into two decimal places for another problem, I used *System.out.printf("%.2f", value)* in my code to fix this. At last was ensuring that users entering negative numbers didn't cause any problems with the software to fail. In my program it was easier to use error management made it easier to observe any problems, and use the try-catch block.

## Assignment Video
