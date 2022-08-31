```java
/*
Given an array arr[] of size N, check if it can be partitioned into two parts such that the sum of elements in both parts is the same.
*/

class Solution{
   
    public static int issubset(int arr[], int sum,int N){
        int dp[][] = new int[N+1][sum+1];
        for(int i=0;i<sum+1;i++){
           dp[0][i] = 0;
        }
        for(int i=0;i<N+1;i++){
           dp[i][0] = 1;
        }
       
        for(int i=1;i<N+1;i++){
            for(int j=1;j<sum+1;j++){
                if(arr[i-1]<=j){
                   dp[i][j] = dp[i-1][j-arr[i-1]] | dp[i-1][j];
                }
                else {
                   dp[i][j] = dp[i-1][j];
                }
            }
        }
       
        return dp[N][sum];
    }
    static int equalPartition(int N, int arr[]){
        int sum = 0;
        int ans =0;
        for(int i=0;i<arr.length;i++){
            sum = sum + arr[i];
        }
      
        if(sum%2!=0){
            return 0;
        } else {
            int target =sum/2;
            ans = issubset(arr,target,N);    
        }
      
        return ans;
        }
   }
