```java

//Given an infinite supply of each denomination of Indian currency { 1, 2, 5, 10, 20, 50, 100, 200, 500, 2000 } and a target value N.
//Find the minimum number of coins and/or notes needed to make the change for Rs N.
class Solution{
    static List<Integer> minPartition(int target)
    {
        List<Integer> ans=new ArrayList<>();
        int coins[]={2000,500,200,100,50,20,10,5,2,1};
        int i=0,n=coins.length;
        
        while(target>0 && i<n){
            if(target>=coins[i]){
                target-=coins[i];
                ans.add(coins[i]);
            }else{
                i++;
            }
        }
        
        return ans;
    }
}
```
