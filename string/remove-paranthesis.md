## problem
leet 1021 
remove the outermost paranthesis of primitive elements 
## code 
```
class Solution {
    public String removeOuterParentheses(String s) {
        StringBuilder ss=new StringBuilder();
        int n=s.length();
        int count=0;
        for (int i=0;i<n;i++){
            if (s.charAt(i)=='('){
                if (count>0){
                    ss.append(s.charAt(i));
                }
                count++;
            }else{
                count--;
                if (count>0){
                    ss.append(s.charAt(i));
                }
            }
        }
        return ss.toString();
    }
}
```
## approach 
introduce a counter and skip if 0 and and add if not 0 
'(' adds counter 
')' decreases counter