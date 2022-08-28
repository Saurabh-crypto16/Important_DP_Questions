```java
/*
Given a NxN matrix of positive integers. There are only three possible moves from a cell Matrix[r][c].

1.Matrix [r+1] [c]
2.Matrix [r+1] [c-1]
3.Matrix [r+1] [c+1]
Starting from any column in row 0 return the largest sum of any of the paths up to row N-1.
*/

class Solution{
    static int maximumPath(int N, int mat[][])
    {
        for(int i=N-2;i>=0;i--){
            for(int j=0;j<N;j++){
                if(j==0){
                    mat[i][j]+=Math.max(mat[i+1][j],mat[i+1][j+1]);
                }else if(j==N-1){
                    mat[i][j]+=Math.max(mat[i+1][j],mat[i+1][j-1]);
                }else{
                    mat[i][j]+=Math.max(mat[i+1][j],
                        Math.max(mat[i+1][j-1],mat[i+1][j+1]));
                }
            }
        }
        
        int ans=Integer.MIN_VALUE;
        for(int val: mat[0]){
            ans=Math.max(ans,val);
        }
        
        return ans;
    }
}

```
