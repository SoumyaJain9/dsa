## problem 
leet-> 5 find the longest palindromic substring in a given string 
 ## approach 
 (without using dp)
 ## code 
 ```
class Solution {
    public String longestPalindrome(String s) {
        int start=0;
        int end=0;
        for (int i=0;i<s.length();i++){
            int len1=expandcentre(s,i,i);
            int len2=expandcentre(s,i,i+1);
            int maxlen=Math.max(len1,len2);
            if (maxlen> end-start+1){
                start=i-(maxlen-1)/2;
                end=i+maxlen/2;
            }
        } 
        return s.substring(start,end+1);     
    }
    private int expandcentre(String s, int left, int right){
        while(left>=0&& right<s.length()&& s.charAt(left)==s.charAt(right)){
            left--;
            right++;
        }
        return (right-left-1);
    }
}
```
