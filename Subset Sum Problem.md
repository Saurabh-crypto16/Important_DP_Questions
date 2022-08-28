```java
//Question - Given an array of non-negative integers, and a value sum, determine if there is a subset of the given set with sum equal to given sum. 

class Solution{
    static Boolean isSubsetSum(int N, int arr[], int sum){
        boolean dp[][]=new boolean[arr.length+1][sum+1];
        
        for(int i=0;i<dp.length;i++){
            for(int j=0;j<dp[0].length;j++){
                if(i==0 && j==0){
                    dp[i][j]=true;
                }else if(j==0){
                    dp[i][j]=true;
                }else if(i==0){
                    dp[i][j]=false;
                }else{
                    if(dp[i-1][j]){
                        dp[i][j]=true;
                    }else if(j>=arr[i-1]){
                        dp[i][j]=dp[i-1][j] || dp[i-1][j-arr[i-1]];
                    }
                }
            }
        }
        
        return dp[dp.length-1][dp[0].length-1];
    }
}
```
