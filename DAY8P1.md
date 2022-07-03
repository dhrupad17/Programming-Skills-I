# Merge Strings Alternately
---
- ## Question:
> You are given two strings word1 and word2. Merge the strings by adding letters in alternating order, starting with word1. If a string is longer than the other, append the additional letters onto the end of the merged string.
> 
> Return the merged string.
---
- ## Example:
> Input: word1 = "abc", word2 = "pqr"
> 
> Output: "apbqcr"
---
- ## Solution:
**Code :**
```java
class Solution {
    public String mergeAlternately(String word1, String word2) {
        int l1=word1.length();
        int l2=word2.length();
        char[] result=new char[l1+l2];
        int p1=0;
        int p2=0;
        int p=0;
        while(p1<l1|| p2<l2)
        {
            if(p1<l1){
                result[p++]=word1.charAt(p1++);
            }
            if(p2<l2)
            {
                result[p++]=word2.charAt(p2++);
            }
                
        }
        return new String(result);
    }
}
