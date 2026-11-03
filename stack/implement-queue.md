## problem 
leet-> 232
implement queue using stack 
## explaination 
push()- adds elements from the front side 
so to pop or peek elements in FIFO order we need to reverse them using one more stack 
## code 
```
class MyQueue {
    Stack<Integer> s1=new Stack<>();
    Stack<Integer> s2=new Stack<>();
    public MyQueue() {
        
    }
    public void push(int x) {
         s1.push(x);    
    }
    public int pop() {
        if(s2.isEmpty()){
            while(!s1.isEmpty()){
                s2.push(s1.pop());
            }
        }
        return s2.pop();
    }
    public int peek() {
        if (s2.isEmpty()){
            while(!s1.isEmpty()){
                s2.push(s1.pop());
            }
        }
        return s2.peek();   
    } 
    public boolean empty() {
        return s1.isEmpty() && s2.isEmpty();  
    }
}
```
