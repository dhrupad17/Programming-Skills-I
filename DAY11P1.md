# Sort Integers by The Number of 1 Bits
---
- ## Question:
> You are given an integer array arr. Sort the integers in the array in ascending order by the number of 1's in their binary representation and in case of two or more integers have the same number of 1's you have to sort them in ascending order.
> Return the array after sorting it.
---
- ## Example:
> Input: arr = [0,1,2,3,4,5,6,7,8]
> 
> Output: [0,1,2,4,8,3,5,6,7]
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[] sortByBits(int[] arr) {
        int bits[]=new int[arr.length];
        int ans[]=new int[arr.length];
        Arrays.sort(arr);
        for(int i=0;i<arr.length;i++)
        {
            int n=arr[i];
            int count=0;
            while(n>0)
            {
                if((n&1)==1)
                    count++;
            n=n>>1;
            }
            bits[i]=count;
        }
        int l = 0;
        for(int j = 0; j <= 14; j++){
            int length = 0;
            for(int k = 0; k < bits.length; k++){
                if(j == bits[k]){
                    length++;
                    ans[l] = arr[k];
                    l++;
                }
            }
        }
        return ans;
    }
}
