```
int climbStairs(int n) {
    if (n <= 2) {
        return n;
    }
    
    // Initialize an array to store the number of ways to reach each step.
    int dp[n + 1];
    
    // There is one way to reach the first step (1 step at a time).
    dp[1] = 1;
    // There are two ways to reach the second step (2 steps at a time or two 1 steps).
    dp[2] = 2;
    
    // Calculate the number of ways for each step starting from the third step.
    for (int i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    
    return dp[n];
}
```