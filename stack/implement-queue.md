## problme 
leet -> 225 
implement stack using queue 
## explaination 
in a queue the functions are 
poll() to delete elements -> like pop()
offer() to add elements from the rear end (right side) -> like add()
peek() to return the top element -> like top()
now as we want to impement a stack i.e. LIFO 
for that we need to have the latest element on the front side
therefore 
## code 
```
class MyStack {
    Queue<Integer> q1=new LinkedList<>();
    Queue<Integer> q2=new LinkedList<>();
    public MyStack() {     
    } 
    public void push(int x) {
        q2.offer(x);
        while(!q1.isEmpty()){
            q2.offer(q1.poll());
        }
        Queue<Integer> temp=q1;
        q1=q2;
        q2=temp;   
    }
    public int pop() {
        return q1.poll();
        
    }
    public int top() {
        return q1.peek();
        
    }
    public boolean empty() {
        return q1.isEmpty();   
    }
}

```
