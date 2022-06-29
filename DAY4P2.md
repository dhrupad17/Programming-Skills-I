# Can Make Arithmetic Progression From Sequence
---
- ## Question:
> A sequence of numbers is called an arithmetic progression if the difference between any two consecutive elements is the same.
> 
> Given an array of numbers arr, return true if the array can be rearranged to form an arithmetic progression. Otherwise, return false.
---
- ## Example:
> Input: arr = [3,5,1]
> 
> Output: true
> 
> Explanation: We can reorder the elements as [1,3,5] or [5,3,1] with differences 2 and -2 respectively, between each consecutive elements.
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean canMakeArithmeticProgression(int[] arr) {
        Arrays.sort(arr);
        int diff=arr[1]-arr[0];
        for(int i=2;i<arr.length;i++)
        {
            if(arr[i]-arr[i-1]!=diff)
                return false;
        }
        return true;
    }
}
