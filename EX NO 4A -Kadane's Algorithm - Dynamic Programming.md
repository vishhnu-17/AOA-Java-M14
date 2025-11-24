
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 07-11-2005
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

### Developed by: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103


## Algorithm
1. Initialize a running sum and track the maximum subarray sum found so far.
2. Add each element to the running sum as you iterate through the array.
3. Update the maximum sum whenever the running sum becomes higher than it.
4. Reset the running sum to zero whenever it drops below zero.
5. Return the maximum sum found, or zero if all values were negative.


## Program:
```java
import java.util.*;

public class TraderJoeProfit {
    public static int maxProfit(int[] profits) {
        //Type your code
        int sum = 0;
        int mx = Integer.MIN_VALUE;

        for (int p : profits) {
            sum += p;
            mx = Math.max(mx, sum);
            if (sum < 0) sum = 0;  
        }

        if(mx<0)return 0;
        return mx;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] profits = new int[n];
        for (int i = 0; i < n; i++) {
            profits[i] = sc.nextInt();
        }
        System.out.println(maxProfit(profits));
    }
}

```

## Output:

<img width="462" height="188" alt="image" src="https://github.com/user-attachments/assets/e87a034d-9b9f-4f98-bc3e-2a2483d48ed8" />


## Result:
The program successfully Implemented and the output is verified. 
