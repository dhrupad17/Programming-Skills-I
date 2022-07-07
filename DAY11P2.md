# Implement Queue using Stacks
---
- ## Question:
> Implement a first in first out (FIFO) queue using only two stacks. The implemented queue should support all the functions of a normal queue (push, peek, pop, and empty)
>
> Implement the MyQueue class:
>- void push(int x) Pushes element x to the back of the queue.
>- int pop() Removes the element from the front of the queue and returns it.
>- int peek() Returns the element at the front of the queue.
>- boolean empty() Returns true if the queue is empty, false otherwise.
>
> Notes:

>- You must use only standard operations of a stack, which means only push to top, peek/pop from top, size, and is empty operations are valid.
>- Depending on your language, the stack may not be supported natively. You may simulate a stack using a list or deque (double-ended queue) as long as you use only a stack's standard operations.
---
- ## Example:
> Input
>["MyQueue", "push", "push", "peek", "pop", "empty"]
>[[], [1], [2], [], [], []]
>
>Output
>[null, null, null, 1, 1, false]
---
- ## Solution:
**Code :**
```java
class MyQueue {

    Stack<Integer> og;
    Stack<Integer> temp;
    int top;
    
    public MyQueue() {
        og = new Stack();
        temp = new Stack();
    }
    
    public void push(int x) {
        if(og.empty())
            top = x;
        og.push(x);
    }
    
    public int pop() {
        while(og.size() != 1)
        {
            temp.push(og.pop());
        }
        int popped = og.pop();
        if(!temp.empty())
            top = temp.peek();
        while(!temp.empty())
        {
            og.push(temp.pop());
        }
        return popped;
    }
    
    public int peek() {
        return top;
    }
    
    public boolean empty() {
        return og.empty();
    }
}
