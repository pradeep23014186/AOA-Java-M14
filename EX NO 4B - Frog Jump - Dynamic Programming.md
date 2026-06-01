
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 12/05/2026
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1. Start the program and read the number of steps n from the user.
2. If n is 1, return 1; if n is 2, return 2 as the base cases.
3. Initialize two variables to store the number of ways to reach the previous two steps.
4. Use a loop from step 3 to n to calculate the current number of ways as the sum of the previous two values.
5. Print the total number of distinct ways to reach the n-th step and stop the program.   

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

    public static int countWays(int n) 
    {
        if (n == 1) return 1;
        if (n == 2) return 2;

        int prev2 = 1; 
        int prev1 = 2; 
        int current = 0;
        for (int i = 3; i <= n; i++) 
        {
            current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        return prev1;
    }
}
```

## Output:

<img width="366" height="204" alt="output2" src="https://github.com/user-attachments/assets/c1889cd7-16ae-45f7-8e3b-f0283964fabe" />


## Result:
The program successfully implemented and the expected output is verified.
