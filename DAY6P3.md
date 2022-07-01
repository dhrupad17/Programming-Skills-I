# Richest Customer Wealth
---
- ## Question:
> You are given an m x n integer grid accounts where accounts[i][j] is the amount of money the i​​​​​​​​​​​th​​​​ customer has in the j​​​​​​​​​​​th​​​​ bank. Return the wealth that the richest customer has.
> 
> A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.
---
- ## Example:
> Input: accounts = [[1,2,3],[3,2,1]]
> 
> Output: 6
---
- ## Solution:
**Code :**
```java
class Solution {
    public int maximumWealth(int[][] accounts) {
        int i,j;
        int ans=-9999;
        for(i=0;i<accounts.length;i++)
        {
            int sum=0;
            for(j=0;j<accounts[i].length;j++)
            {
                sum=sum+accounts[i][j];
            }
            if(sum>ans)
                ans=sum;
        }
        return ans;
    }
}
