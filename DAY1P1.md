# Count Odd Numbers in an Interval Range
---
- ## Question:
> Given two non-negative integers low and high. Return the count of odd numbers between low and high (inclusive).
---
- ## Example:
> **Input :** low = 3, high = 7
> 
> **Output:** 3
> 
> **Explanation:** The odd numbers between 3 and 7 are [3,5,7].
---
- ## Solution:
**Code :**
```java
class Solution {
    public int countOdds(int low, int high) {
       if(high%2!=0 || low%2!=0)
       {
           int diff=high-low;
           return (diff/2)+1;
       }
        else
        {
            int diff=high-low;
            return diff/2;
        }
    }
}
