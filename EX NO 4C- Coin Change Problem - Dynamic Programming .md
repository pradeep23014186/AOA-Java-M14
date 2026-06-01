
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE: 14/05/2026
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1. Start the program and read the coin denominations and target amount from the user.
2. Create a dynamic programming array dp of size amount + 1 and initialize all values with a large number except dp[0] = 0.
3. Traverse all amounts from 1 to amount and for each amount, check every coin denomination.
4. If the current coin can contribute to the amount, update dp[i] with the minimum value between the current value and dp[i - coin] + 1.
5. After filling the array, print -1 if the amount cannot be formed; otherwise, print the minimum number of coins required and stop the program.   

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.*;

public class Solution 
{
    public int coinChange(int[] coins, int amount) 
    {
        int[] dp = new int[amount + 1];
        Arrays.fill(dp, amount + 1);
        dp[0] = 0;
        for (int i = 1; i <= amount; i++) 
        {
            for (int coin : coins) 
            {
                if (i - coin >= 0) 
                {
                    dp[i] = Math.min(dp[i], dp[i - coin] + 1);
                }
            }
        }
        return dp[amount] > amount ? -1 : dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        Solution solution = new Solution();

        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();

        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");

        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }

        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));

        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}
```

## Output:

<img width="388" height="237" alt="output3" src="https://github.com/user-attachments/assets/ab180556-1ccf-44e7-8038-5d7a69c79602" />


## Result:
The program successfully implemented and the expected output is verified.
