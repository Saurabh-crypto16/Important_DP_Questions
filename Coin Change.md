```java
/*
Given an integer  array coins[ ] of size N representing different denominations of currency and an integer sum, 
find the number of ways you can make sum by using different combinations from coins[ ].  
Note: Assume that you have an infinite supply of each type of coin. 
*/

class Solution {
    public long count(int coins[], int N, int sum) {
        long[] dp = new long[sum+1];
        dp[0] = 1;
       
        for(int i = 0 ; i < coins.length;i++){
            for(int j = coins[i]; j<=sum;j++){
                dp[j] = dp[j] + dp[j-coins[i]];
            }
        }
       
        return  dp[sum];       
    }
}

```
