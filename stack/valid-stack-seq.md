## problem 
leet-> validate stack sequence 
## code 
```
class Solution {
    public boolean validateStackSequences(int[] pushed, int[] popped) {
        Stack<Integer> s1=new Stack<>();
        int j=0;
        for (int i=0;i<pushed.length;i++){
            s1.push(pushed[i]);
            while(!s1.isEmpty() && s1.peek()==popped[j]){
                s1.pop();
                j++;
            }
        }
        return s1.isEmpty();
    }
}
```
