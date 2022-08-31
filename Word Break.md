```java
/*
Given a string A and a dictionary of n words B, find out if A can be segmented into a space-separated sequence of dictionary words.
Note: From the dictionary B each word can be taken any number of times and in any order.
*/
class Sol
{
    public static int wordBreak(String A, ArrayList<String> B )
    {
        int size = A.length();
        if (size == 0)  return 1;
        for (int i = 1; i <= size; i++){
            if(B.contains(A.substring(0,i)) && wordBreak(A.substring(i),B)==1)
                    return 1;
        }
        return 0;
    }
}
```
