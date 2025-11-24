
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 07-11-2005
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

### Developed by: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103

## Algorithm
1. If n is 1 or 2, directly return n as the number of ways.
2. Initialize two variables a = 1 and b = 2 to store previous computed ways.
3. Iterate from 3 up to n to compute ways for each step.
4. Update c = a + b (current ways), then shift a = b and b = c.
5. Return the final computed value c as the total number of ways to reach step n.
 

## Program:
```java
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       //Type your code here
       if(n==1)return 1;
       if(n==2)return 2;
       int a=1;
       int b=2;
       int c=0;
       for(int i=3;i<=n;i++){
           c=a+b;
           a=b;
           b=c;
       }
       return c;
    }
}

```

## Output:

<img width="336" height="207" alt="image" src="https://github.com/user-attachments/assets/c5df0757-4b16-4456-a324-8dbeb95a8526" />


## Result:
The program successfully implemented and the expected output is verified.
