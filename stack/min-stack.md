## problem 
leet-> 155 
find the min element in the stack with O(1) time complexity.
## code 
in this time limit was exceeded but the sol is right 
```
class MinStack {
    Stack<Integer> s1= new Stack<>();
    Stack<Integer> s2= new Stack<>();
    public MinStack() {   
    }
    public void push(int value) {
        s2.push(value);
    }
    public void pop() {
        s2.pop();    
    }
    public int top() {
        return s2.peek();   
    }
    public int getMin() {
        int min=Integer.MAX_VALUE;
        for (int i=0;i<s2.size();i++){
            if (s2.get(i)<min){
                min=s2.get(i);
            }
        }
        return min;       
    }
}
```
## proper code with no time limit exceeded error
```
class MinStack {
    Stack<Integer> s1= new Stack<>();
    Stack<Integer> s2= new Stack<>();
    public MinStack() {   
    }
    public void push(int value) {
        s2.push(value);
        if (s1.isEmpty()||s1.peek()>=value){
            s1.push(value);
        }
    }
    public void pop() {
        int x=s2.pop(); 
        if (s1.peek()==x){
            s1.pop();
        }   
    }
    public int top() {
        return s2.peek();   
    }
    public int getMin() {
        return s1.peek();     
    }
}
```
