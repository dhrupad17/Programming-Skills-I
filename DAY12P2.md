# Range Sum Query - Immutable
---
- ## Question:
> Given an integer array nums, handle multiple queries of the following type:
> 
>Calculate the sum of the elements of nums between indices left and right inclusive where left <= right.
>Implement the NumArray class:
>
>- NumArray(int[] nums) Initializes the object with the integer array nums.
>- int sumRange(int left, int right) Returns the sum of the elements of nums between indices left and right inclusive (i.e. nums[left] + nums[left + 1] + ... + nums[right]).
---
- ## Example:
> Input
>["NumArray", "sumRange", "sumRange", "sumRange"]
>[[[-2, 0, 3, -5, 2, -1]], [0, 2], [2, 5], [0, 5]]
>
>Output
>[null, 1, -1, -3]
---
- ## Solution:
**Code :**
```java
class NumArray {

    int[] nums;

public NumArray(int[] nums) {
    for(int i = 1; i < nums.length; i++)
        nums[i] += nums[i - 1];
    
    this.nums = nums;
}

public int sumRange(int i, int j) {
    if(i == 0)
        return nums[j];
    
    return nums[j] - nums[i - 1];
}
}
