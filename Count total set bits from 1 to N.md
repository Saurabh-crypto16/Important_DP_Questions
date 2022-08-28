```java
class Solution{
    
    //Function to return sum of count of set bits in the integers from 1 to n.
    public static int countSetBits(int n){
        if(n==0)    return 0;
        
        //number of set bits from 1 to n is
        //find x largest power of 2 less than n
        //(2^(x-1)*x) + (n-(2^x)+1) + countSetBits(n-2^x)
        
        int x=largestPowerInRange(n);
        int bitsTill2Powx=x*(1<<(x-1));
        int msbFrom2PowxTon=n-(1<<x)+1;
        int rest=n-(1<<x);
        int bitsInRemaining=countSetBits(rest);
        
        int ans=bitsTill2Powx+msbFrom2PowxTon+bitsInRemaining;
        
        return ans;
    }
    public static int largestPowerInRange(int n){
        int x=1;
        
        while((1<<x)<=n){
            x++;
        }
        
        return x-1;
    }
}
```
