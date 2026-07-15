## problem 
reverse words in a string 
leet -> 151 
## code 
with java inbuilt functions
```
class Solution {
    public String reverseWords(String s) {
        String[] arr = s.trim().split("\\s+");
        int n=arr.length;
        StringBuilder ss=new StringBuilder();
        for (int i=n-1;i>=0;i--){
            ss.append(arr[i]);
            if (i!=0){
                ss.append(" ");
            }

        }
        return ss.toString();
        
    }
}
```
## code 
with pointer approach 
```
class Solution {
    public String reverseWords(String s) {
        StringBuilder ss= new StringBuilder();
        int n=s.length()-1;
        while(n>=0){
            while(n>=0&&s.charAt(n)==' '){
                n--;
            }
            if (n<0){
                break;
            }
            int j=n;
            while(n>=0&& s.charAt(n)!=' '){
                n--;
            }
            ss.append(s.substring(n+1,j+1));
            while(n>=0&& s.charAt(n)==' '){
                n--;
            }
            if (n>=0){
                ss.append(" ");
            }
        }
        return ss.toString();
    }
}
```
