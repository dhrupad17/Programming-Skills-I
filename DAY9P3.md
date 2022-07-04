# Verifying an Alien Dictionary
---
- ## Question:
> In an alien language, surprisingly, they also use English lowercase letters, but possibly in a different order. The order of the alphabet is some permutation of lowercase letters.
> 
> Given a sequence of words written in the alien language, and the order of the alphabet, return true if and only if the given words are sorted lexicographically in this alien language.
---
- ## Example:
> Input: words = ["hello","leetcode"], order = "hlabcdefgijkmnopqrstuvwxyz"
> 
> Output: true
> 
> Explanation: As 'h' comes before 'l' in this language, then the sequence is sorted.
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean isAlienSorted(String[] words, String order) {
        
        for(int i=0; i< words.length-1; i++){
            String s1 = words[i];
            String s2 = words[i+1];
            if(!compare(s1, s2, order))
                return false;
        }
        return true;
    }
    private boolean compare(String s1, String s2, String order) {
        if(s1.equals(s2))
            return true;
        
        int min = Math.min(s1.length(), s2.length());
        int j = 0; 
        
        while(j < min && s1.charAt(j) == s2.charAt(j)){
           j++;
        }
        
        if(j==min){
            return (min == s1.length());
        }else{
            char c1 = s1.charAt(j);
            char c2 = s2.charAt(j);
            boolean res = (order.indexOf(c1) < order.indexOf(c2));
            return res;
        }
 }
}
