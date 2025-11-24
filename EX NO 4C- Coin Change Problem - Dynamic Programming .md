
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE: 07-11-2005
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm

1. Initialize a dp array of size amount+1 with a large sentinel value and set dp[0] = 0.
2. For every value from 1 to amount, iterate over all coins.
3. If the coin value does not exceed the current amount i, update dp[i] = min(dp[i], dp[i - coin] + 1).
4. After filling dp, check if dp[amount] is still larger than amount.
5. If yes return -1 (not possible), otherwise return dp[amount] as the minimum coins required.

### Developed by: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103

## Program:
```java
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        //ADD YOUR CODE HERE
        int[] dp = new int[amount+1];
        Arrays.fill(dp,amount+1);
        dp[0]=0;
        for(int i=1;i<=amount;i++){
            for(int c:coins){
                if(c<=i)dp[i]=Math.min(dp[i],dp[i-c]+1);
            }
        }
        return dp[amount]>amount ? -1:dp[amount];
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

<img width="368" height="247" alt="image" src="https://github.com/user-attachments/assets/1596ef55-48c6-4729-8446-a207397779dd" />


## Result:
The program successfully implemented and the expected output is verified.
