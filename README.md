# Exp-6-Dynamic Programming


## **📌 Dynamic Programming (DP)**
Dynamic Programming (DP) is a powerful algorithmic technique used for solving optimization problems by breaking them down into smaller overlapping subproblems and solving each subproblem only once, storing the results for future reference.

---

## **🔹 Key Concepts**
### **1. Optimal Substructure**
A problem exhibits **optimal substructure** if its solution can be constructed from the solutions of its subproblems.  
Example: The shortest path in a graph can be broken into smaller shortest path subproblems.

### **2. Overlapping Subproblems**
A problem has **overlapping subproblems** when it solves the same subproblems multiple times.  
Example: Fibonacci sequence, where `fib(n) = fib(n-1) + fib(n-2)`, repeatedly calculates the same Fibonacci numbers.

### **3. Memoization (Top-Down Approach)**
- Uses **recursion** with a **cache (array or hashmap)** to store previously computed results.
- Avoids redundant calculations.
- Example:
  ```java
  import java.util.*;

  class Fibonacci {
      static Map<Integer, Integer> memo = new HashMap<>();
      public static int fib(int n) {
          if (n <= 1) return n;
          if (memo.containsKey(n)) return memo.get(n);
          int result = fib(n - 1) + fib(n - 2);
          memo.put(n, result);
          return result;
      }

      public static void main(String[] args) {
          System.out.println(fib(10)); // Output: 55
      }
  }
  ```
### **4. Tabulation (Bottom-Up Approach)**
- Uses **iteration** and builds up solutions from smaller subproblems.
- Typically more space-efficient.
- Example:
  ```java
  class Fibonacci {
      public static int fib(int n) {
          if (n <= 1) return n;
          int[] dp = new int[n + 1];
          dp[0] = 0;
          dp[1] = 1;
          for (int i = 2; i <= n; i++) {
              dp[i] = dp[i - 1] + dp[i - 2];
          }
          return dp[n];
      }

      public static void main(String[] args) {
          System.out.println(fib(10)); // Output: 55
      }
  }
  ```

---

## **🚀 Common DP Problems**
| Problem Type | Examples |
|-------------|----------|
| **1D DP** | Fibonacci, Climbing Stairs, House Robber |
| **2D DP** | Longest Common Subsequence, Knapsack Problem |
| **DP on Strings** | Edit Distance, Longest Palindromic Subsequence |
| **DP on Trees** | Diameter of Binary Tree, House Robber III |
| **DP on Graphs** | Shortest Path Algorithms (Floyd-Warshall, Bellman-Ford) |

---

## **📖 Famous DP Problems & Solutions**
### **1. Climbing Stairs (Fibonacci Variation)**
#### **Problem Statement**  
You can climb `n` stairs taking `1` or `2` steps at a time. Find the number of ways to reach the top.

#### **Solution (Bottom-Up DP)**
```java
class Solution {
    public int climbStairs(int n) {
        if (n <= 2) return n;
        int[] dp = new int[n + 1];
        dp[1] = 1;
        dp[2] = 2;
        for (int i = 3; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
}
```
**Time Complexity:** O(n)  
**Space Complexity:** O(n) (Can be optimized to O(1) using variables)

---
These are the problem which are releated to Dynamic Programming are solved in the given expirement 🚀🚀🚀: -
>> 1. Climbing Stairs - https://leetcode.com/problems/climbing-stairs/
>> 2. Jump Game - https://leetcode.com/problems/jump-game/



