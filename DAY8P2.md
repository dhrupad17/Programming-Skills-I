# Goal Parser Interpretation
---
- ## Question:
> You own a Goal Parser that can interpret a string command. The command consists of an alphabet of "G", "()" and/or "(al)" in some order. The Goal Parser will interpret "G" as the string "G", "()" as the string "o", and "(al)" as the string "al". The interpreted strings are then concatenated in the original order.
> 
> Given the string command, return the Goal Parser's interpretation of command.
---
- ## Example:
> Input: command = "G()(al)"
> 
> Output: "Goal"
---
- ## Solution:
**Code :**
```java
class Solution {
   public String interpret(String command) {
        StringBuilder ans = new StringBuilder();
        int i=0 , n = command.length();
        while(i<n){
            if(command.charAt(i)=='(' && command.charAt(i+1)!=')'){
                ans.append("al");
                i+=3;
            }
             else if(command.charAt(i)=='(' && command.charAt(i+1)==')'){
                ans.append("o");
                i+=1;
            }else{
                 ans.append("G");
             }
            i++;
            if(i==n-1){
                ans.append("G");
                break;
            }
        }
        return ans.toString();
    }
}
