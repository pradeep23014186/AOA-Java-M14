# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 12/05/2026
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6
## Algorithm
1. Start the program and read the number of buildings and their net energy values into an array.
2. Use Kadane’s Algorithm to find the maximum subarray sum for the normal (non-circular) case.
3. Simultaneously find the minimum subarray sum and calculate the total sum of the array elements.
4. Compute the circular maximum sum as totalSum - minSum and compare it with the normal maximum sum. If all elements are negative, return the maximum element directly.
5. Print the maximum net energy that can be collected and stop the program.

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy) {
        int totalSum = 0;
        int maxSum = energy[0], currentMax = 0;
        int minSum = energy[0], currentMin = 0;
        int maxElement = energy[0];
        for (int i = 0; i < energy.length; i++) 
        {
            int x = energy[i];
            totalSum += x;
            maxElement = Math.max(maxElement, x);
            currentMax = Math.max(x, currentMax + x);
            maxSum = Math.max(maxSum, currentMax);
            currentMin = Math.min(x, currentMin + x);
            minSum = Math.min(minSum, currentMin);
        }
        if (maxElement < 0) 
        {
            return maxElement;
        }
        return Math.max(maxSum, totalSum - minSum);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }

        System.out.println(maxCircularEnergy(energy));
    }
}
```

## Output:

<img width="442" height="242" alt="output1" src="https://github.com/user-attachments/assets/2d4c75ed-67a5-4a34-8a31-4b22425dadcb" />


## Result:
The program successfully Implemented and the output is verified. 
