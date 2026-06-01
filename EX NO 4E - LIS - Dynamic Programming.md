
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 15/05/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1. Start the program and read the size of the array and its elements from the user.
2. Create a dynamic programming array dp and initialize all values to 1, since each element itself forms an increasing subsequence of length 1.
3. Traverse the array using two nested loops and compare each element with all previous elements.
4. If nums[j] < nums[i], update dp[i] as the maximum of its current value and dp[j] + 1. 5. Keep track of the maximum subsequence length found.
5. Print the length of the longest increasing subsequence and stop the program. 

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) 
    {
        int n = nums.length;
        int[] dp = new int[n];
        Arrays.fill(dp, 1);

        int maxLen = 1;
        for (int i = 0; i < n; i++) 
        {
            for (int j = 0; j < i; j++) 
            {
                if (nums[j] < nums[i]) 
                {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
            maxLen = Math.max(maxLen, dp[i]);
        }
        return maxLen;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        int result = lengthOfLIS(nums);

        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}
```

## Output:

<img width="1122" height="243" alt="output5" src="https://github.com/user-attachments/assets/357dd9d9-d509-44f4-a94d-f2b7b2ef86be" />


## Result:
The program successfully implemented and the expected output is verified.
