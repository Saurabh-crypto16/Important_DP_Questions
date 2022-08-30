```java
/*
Question 1 - You are given an array A of size N. The array contains integers and is of even length. 
The elements of the array represent N coin of values V1, V2, ....Vn. You play against an opponent in an alternating way.

In each turn, a player selects either the first or last coin from the row, removes it from the row permanently, and receives the value of the coin.

You need to determine the maximum possible amount of money you can win if you go first.
Note: Both the players are playing optimally.
*/

class solve
{
    //Function to find the maximum possible amount of money we can win.
    static long countMaximum(int arr[], int n)
    {
        long dp[][]=new long[n][n];
        
        for(int g=0;g<n;g++){
            for(int i=0,j=g;j<n;i++,j++){
                if(g==0){
                    dp[i][j]=arr[i]; 
                }else if(g==1){
                    dp[i][j]=Math.max(arr[i],arr[j]);
                }else{
                    //if user 1 takes i he gets min of i+2,j and i+1,j-1
                    //else gets min of i,j-2 and i+1,j-1
                    long val1=arr[i]+Math.min(dp[i+2][j],dp[i+1][j-1]);
                    long val2=arr[j]+Math.min(dp[i][j-2],dp[i+1][j-1]);
                    dp[i][j]=Math.max(val1,val2);
                }
            }
        }
        
        return dp[0][n-1];
    }
}
```
