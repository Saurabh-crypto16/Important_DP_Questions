```java

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
