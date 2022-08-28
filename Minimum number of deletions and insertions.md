```java
//Given two strings str1 and str2. The task is to remove or insert the minimum number of characters from/in str1 so as to transform it into str2. 
//It could be possible that the same character needs to be removed/deleted from one point of str1 and inserted to some another point.

class Solution
{
	public int minOperations(String str1, String str2) 
	{ 
        int dp[][]=new int[str1.length()+1][str2.length()+1];
        
        for(int i = 0;i<=str1.length();i++){
	        for(int j = 0;j<=str2.length();j++){
	            if( i == 0 || j == 0){
	                dp[i][j] = 0;
	            }else if(str1.charAt(i-1) == str2.charAt(j-1)){
	                dp[i][j] = dp[i-1][j-1] +1;
	            }else{
	                dp[i][j] = Math.max(dp[i][j-1],dp[i-1][j]);
	            }
	        }
	    }
        
        //System.out.println(dp[str1.length()][str2.length()]);
        
        int deletion=str1.length()-dp[str1.length()][str2.length()];
        int insertion=str2.length()-dp[str1.length()][str2.length()];
        
        return insertion+deletion;
	} 
}
```
