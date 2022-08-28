```java
/*
Given two strings s and t. Return the minimum number of operations required to convert s to t.

The possible operations are permitted:
1.Insert a character at any position of the string.
2.Remove any character from the string.
3.Replace any character from the string with any other character.
*/

class Solution {
    public int editDistance(String s, String t) {
        // Code here
        int dp[][]=new int[s.length()+1][t.length()+1];
        
        for(int i=0;i<dp.length;i++){
            for(int j=0;j<dp[0].length;j++){
                if(i==0){
                    dp[i][j]=j;
                }else if(j==0){
                    dp[i][j]=i;
                }else{
                    if(s.charAt(i-1)==t.charAt(j-1)){
                        dp[i][j]=dp[i-1][j-1];
                    }else{
                        int replace=dp[i-1][j-1];
                        int insert=dp[i-1][j];
                        int delete=dp[i][j-1];
                        
                        dp[i][j]=Math.min(replace,Math.min(delete,insert))+1;
                    }
                }
            }
        }
        
        return dp[dp.length-1][dp[0].length-1];
    }
}
```
