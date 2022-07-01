# Sum of All Odd Length Subarrays
---
- ## Question:
> Given an array of positive integers arr, return the sum of all possible odd-length subarrays of arr.
> A subarray is a contiguous subsequence of the array.
 ---
- ## Example:
> Input: arr = [1,4,2,5,3]
> 
> Output: 58
---
- ## Solution:
**Code :**
```java
class Solution {
    public int sumOddLengthSubarrays(int[] arr) {
        int sum=0;
        for(int i=0;i<arr.length;i++)
        {
            sum=sum+((arr[i])*((((i+1)*(arr.length-i))+1)/2));
        }
        return sum;
    }
}
