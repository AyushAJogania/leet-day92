# leet-day92

# Number of Ways to Stay at Index 0

## Problem Description

You are given a pointer at index 0 in an array of size `arrLen`. At each step, you can move one position to the left, one position to the right in the array, or stay in the same place. The pointer should not be placed outside the array at any time. Given two integers `steps` and `arrLen`, your task is to return the number of ways to keep the pointer at index 0 after exactly `steps` steps. 

To avoid large results, return the answer modulo 1,000,000,007.

## Solution

The provided C++ solution uses dynamic programming to calculate the number of ways to stay at index 0 after a given number of steps. The key idea is to keep track of the possibilities at each step. 

The algorithm maintains a 2D array `dp`, where `dp[i][j]` represents the number of ways to reach position `j` after taking `i` steps. The index `i` corresponds to the number of steps, and the index `j` corresponds to the current position in the array.

The solution iterates through the number of steps, updating the `dp` array at each step. To calculate the number of ways to reach position `j` after `i` steps, the algorithm considers three possibilities: moving left, moving right, or staying in the same place.

- The `dp[i - 1][j]` represents staying in the same position.
- The `dp[i - 1][j - 1]` represents moving left.
- The `dp[i - 1][j + 1]` represents moving right.

The algorithm takes into account the boundary conditions to ensure that the pointer does not go outside the array. After processing all steps, the final result is found in `dp[steps][0]`, which represents the number of ways to stay at index 0 after the given number of steps.

The solution uses modulo arithmetic to prevent large results.

## How to Use

To use this solution, you can include the code in your C++ project. The `numWays` function takes two integers, `steps` and `arrLen`, and returns the number of ways to stay at index 0 after the specified number of steps.

Example usage:

```cpp
int steps = 3;
int arrLen = 2;

Solution solution;
int numWays = solution.numWays(steps, arrLen);
cout << "Number of ways: " << numWays << endl;
```

