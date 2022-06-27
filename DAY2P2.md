# Subtract the Product and Sum of Digits of an Integer
---
- ## Question:
> Given an integer number n, return the difference between the product of its digits and the sum of its digits.
---
- ## Example:
> Input: n = 234
> 
> Output: 15 
> 
> Explanation: 
> 
> Product of digits = 2 * 3 * 4 = 24 
> 
> Sum of digits = 2 + 3 + 4 = 9 
> 
> Result = 24 - 9 = 15
---
- ## Solution:
**Code :**
```java
class Solution {
    public int subtractProductAndSum(int n) {
        int d;
        int res=0;
        int prod=1;
        int sum=0;
        while(n!=0)
        {
           d=n%10;
           prod=prod*d;
           sum=sum+d;
           n=n/10;
        }
        res=prod-sum;
        return res;
        
    }
}
