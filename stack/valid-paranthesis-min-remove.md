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
then we will make a list called remove in which we add all teh extra unecessary brackets so for that 
we check if its the startng bracket ( -> then just push in stack 
if the closing bracket then we firstly check if the stack is empty -> which means it is extra unecessary then we add it in remove else just pop it 
after traversing the whole thing if we have any brackets left in stack then we add them in remove 
then reverse its order bcz while removing if we remove from the front then the index will be changed for the later things tehreforre we reverse the order of remove and then start deleting by index 
also reverse has index stored in it of the brackets
