```java
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
