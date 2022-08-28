```java
//Question - Given an array of integers, find the length of the longest (strictly) increasing subsequence from the given array.


class Solution 
{
    //Function to find length of longest increasing subsequence.
    static int longestSubsequence(int size, int a[])
    {
        int dp[]=new int[a.length];
        Arrays.fill(dp,1);
        int ans=1;
        
        for(int i=1;i<size;i++){
            int max=1;
            for(int j=0;j<i;j++){
                if(a[i]>a[j])
                    max=Math.max(max,dp[j]+1);
            }
            dp[i]=max;
            ans=Math.max(ans,dp[i]);
        }
        
        return ans;
    }
} 
```
