```java
//Question - Given two sequences, find the length of longest subsequence present in both of them. Both the strings are of uppercase.


class Solution
{
    //Function to find the length of longest common subsequence in two strings.
    static int lcs(int x, int y, String s1, String s2)
    {
        int dp[][]=new int[x+1][y+1];
        
        for(int i=1;i<=x;i++){
            for(int j=1;j<=y;j++){
                char c1=s1.charAt(i-1);
                char c2=s2.charAt(j-1);
                
                if(c1==c2){
                    dp[i][j]=1+dp[i-1][j-1];
                }else {
                    dp[i][j]=Math.max(dp[i-1][j],dp[i][j-1]);
                }
            }
        }
        
        return dp[dp.length-1][dp[0].length-1];
    }
    
}
```
