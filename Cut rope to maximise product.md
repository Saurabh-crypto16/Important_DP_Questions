```java
//Question - Given a rope of length N meters, 
//cut the rope into several ropes of varying lengths in a way that maximizes product of lengths of all resulting ropes. 
//You must make at least one cut.

class Solution {
    long maxProduct(int n) {
        long[] dp= new long[n+1];
        for(int i=0;i<dp.length;i++){
           dp[i]= -1;
        }
      
        long ans= maxP(n,dp);
        
        return ans;
    }
    static long maxP(int n,long[] dp){
        if(n<=1){
            return 0;
        }
        if(n==2){
            return 1;
        }
        if(n==3){
            return 2;
        }
       
        dp[0]=dp[1]=0;
        dp[2]=1;
       
     
       
        if(dp[n] != -1){
            return dp[n];
        }
       
       
        long max=0; 
         
        for(int i=1;i<n;i++){
            max=Math.max(max, Math.max( i*(n-i), i*maxP((n-i),dp)));
        }
        
        return dp[n]=max;
   }
}

```
