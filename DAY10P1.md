# Convert Binary Number in a Linked List to Integer
---
- ## Question:
> Given head which is a reference node to a singly-linked list. The value of each node in the linked list is either 0 or 1. The linked list holds the binary representation of a number.
> 
> Return the decimal value of the number in the linked list.
---
- ## Example:
> Input: head = [1,0,1]
> 
> Output: 5
> 
> Explanation: (101) in base 2 = (5) in base 10
---
- ## Solution:
**Code :**
```java
class Solution {
    public int getDecimalValue(ListNode head) {
        int ans=0;
        for(ListNode temp=head;temp!=null;temp=temp.next)
        {
            ans=(ans<<1)+temp.val;
        }
        return ans;
    }
}
