```java

//Question - Given a number N. The task is to find the Nth catalan number.
//The first few Catalan numbers for N = 0, 1, 2, 3, … are 1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862, …

class Solution
{
    //Function to find the nth catalan number.
    public static BigInteger findCatalan(int n) {
        BigInteger[] dp = new BigInteger[n+1];
        Arrays.fill(dp, BigInteger.valueOf(0));
        dp[0] = BigInteger.valueOf(1);
        dp[1] = BigInteger.valueOf(1);
        
        for(int i = 2; i <= n; ++i) {
            for(int k = 0; k < i; ++k) 
                dp[i] = dp[i].add(dp[k].multiply(dp[i-k-1]));
        }
        
        return dp[n];
    }
}
```
