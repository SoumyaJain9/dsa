## problem 
leet - > 1249 
remove the min amount of parantehsis to make it valid 
## code 
```
class Solution {
    public String minRemoveToMakeValid(String s) {
        StringBuilder sb= new StringBuilder(s);
        Stack<Integer> s1=new Stack<>();
        List<Integer> remove=new ArrayList<>();
        for (int i=0;i<s.length();i++){
            if (s.charAt(i)=='('){
                s1.push(i);
            }else if(s.charAt(i)==')'){
                if (s1.isEmpty()){
                    remove.add(i);
                }else{
                    s1.pop();
                }
            }
        }
        while(!s1.isEmpty()){
            remove.add(s1.pop());
        }
        Collections.sort(remove,Collections.reverseOrder());
        for (int index:remove){
            sb.deleteCharAt(index);
        }
        return sb.toString();
    }
}
```
## explaination 
bcz a string is immutable we are using string builder 
