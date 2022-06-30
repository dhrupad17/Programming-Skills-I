# Next Greater Element I
---
- ## Question:
> The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.
> 
> You are given two distinct 0-indexed integer arrays nums1 and nums2, where nums1 is a subset of nums2.
> 
> For each 0 <= i < nums1.length, find the index j such that nums1[i] == nums2[j] and determine the next greater element of nums2[j] in nums2. If there is no next greater element, then the answer for this query is -1.
> 
> Return an array ans of length nums1.length such that ans[i] is the next greater element as described above.
---
- ## Example:
> Input: nums1 = [4,1,2], nums2 = [1,3,4,2]
> 
> Output: [-1,3,-1]
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        int[] result=new int[nums1.length];
        int flag=0;
        int max;
        for(int i=0;i<nums1.length;i++)
        {
            max=0;
            flag=0;
            for(int j=0;j<nums2.length;j++)
            {
                if(nums1[i]==nums2[j])
                    flag=1;
                else if(flag==1 && nums2[j]>nums1[i])
                {
                    max=nums2[j];
                    break;
                }
            }
            if(max!=0)
                result[i]=max;
            else
                result[i]=-1;
        }
        return result;
    }
}
