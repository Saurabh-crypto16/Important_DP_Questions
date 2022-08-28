```java
//Question - A frog jumps either 1, 2, or 3 steps to go to the top. In how many ways can it reach the top. 
//As the answer will be large find the answer modulo 1000000007.

class Solution
{
    //Function to count the number of ways in which frog can reach the top.
    static long countWays(int n)
    {
        long dp[]=new long[n+1];
        long mod=(long)1e9+7;
        dp[0]=1;
        
        for(int i=1;i<=n;i++){
            if(i==1){
                dp[i]=dp[i-1];
            }else if(i==2){
                dp[i]=(dp[i-1]+dp[i-2])%mod;
            }else{
                dp[i]=((dp[i-1]+dp[i-2])%mod+dp[i-3])%mod;
            }
        }
        
        return dp[n];
    }
    
}

```
