
# EX 4D Longest Common SubSequence - Dynamic Programming.
## DATE: 15/05/2026
## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

For example, "ace" is a subsequence of "abcde".
A common subsequence of two strings is a subsequence that is common to both strings.

Input: text1 = "abcde", text2 = "ace" 
Output: 3  
Explanation: The longest common subsequence is "ace" and its length is 3.
Constraints:

1 <= text1.length, text2.length <= 1000
text1 and text2 consist of only lowercase English characters.

## Algorithm
1. Start the program and read the two input strings text1 and text2.
2. Create a 2D dynamic programming array dp of size (n+1) × (m+1) initialized with 0, where n and m are the lengths of the strings.
3. Traverse both strings character by character using nested loops.
4. If the characters at the current positions match, update dp[i][j] = 1 + dp[i-1][j-1]; otherwise, set dp[i][j] as the maximum of dp[i-1][j] and dp[i][j-1].
5. Print the value stored in dp[n][m] as the length of the longest common subsequence and stop the program. 

## Program:
```
Program to implement Reverse a String
Developed by: Pradeep Kumar G
Register Number: 212223230150
```
```java
import java.util.*;

public class Solution {

    public int longestCommonSubsequence(String text1, String text2) 
    {
        int n = text1.length();
        int m = text2.length();
        int[][] dp = new int[n + 1][m + 1];
        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= m; j++) 
            {
                if (text1.charAt(i - 1) == text2.charAt(j - 1)) 
                {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } 
                else 
                {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[n][m];
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");

        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);

        sc.close();
    }
}
```

## Output:

<img width="954" height="230" alt="otuput4" src="https://github.com/user-attachments/assets/6ecc36c7-094c-418f-b625-3b1db6a4d420" />


## Result:
The program successfully implemented and the expected output is verified.
