```java
/*
Given two strings X and Y of lengths m and n respectively, find the length of the smallest string which has both, X and Y as its sub-sequences.
*/

class Solution
{
    //Function to find length of shortest common supersequence of two strings.
    public static int shortestCommonSupersequence(String text1,String text2,int n,int m)
    {
        int dp[][]=new int[n+1][m+1];
        
        for(int i=0;i<n+1;i++){
            for(int j=0;j<m+1;j++){
                if(i==0 || j==0){
                   dp[i][j]=0;
                }
                else if(text1.charAt(i-1)==text2.charAt(j-1)){
                   dp[i][j]=1+dp[i-1][j-1];
                }
                else{
                   dp[i][j]=Math.max(dp[i-1][j],dp[i][j-1]);
                }   
            }
        }
        
        return (m+n-dp[n][m]);
    }
}

```
