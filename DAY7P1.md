# Matrix Diagonal Sum
---
- ## Question:
> Given a square matrix mat, return the sum of the matrix diagonals.
> Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/08/14/sample_1911.png)
> Input: mat = [[1,2,3],
              [4,5,6],
              [7,8,9]]
> Output: 25
---
- ## Solution:
**Code :**
```java
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum=0;
        for(int i=0;i<mat.length;i++)
        {
            for(int j=0;j<mat[0].length;j++)
            {
                if(i==j || (i+j)==mat.length-1)
                    sum=sum+mat[i][j];
            }
        }
        return sum;
    }
}
