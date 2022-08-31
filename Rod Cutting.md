```java
/*
Given a rod of length N inches and an array of prices, price[]. 
price[i] denotes the value of a piece of length i. 
Determine the maximum value obtainable by cutting up the rod and selling the pieces.
*/

class Solution{
    public int cutRod(int price[], int n) {
        int np[]=new int[n+1];
        for(int i=0;i<n;i++){
            np[i+1]=price[i];
        }
        int dp[]=new int[n+1];
        dp[0]=0;
        dp[1]=np[1];
        
        for(int i=2;i<np.length;i++){
            int l=1,r=i-1;
            /*
            cut rod as 1 and n-1,2 and n-2,...and as 0 and n
            find max of all these
            */
            int max=np[i];
            while(l<=r){
                max=Math.max(max,dp[l++]+dp[r--]);
            }
            dp[i]=max;
        }
        
        return Arrays.stream(dp).max().getAsInt();
    }
}

```
