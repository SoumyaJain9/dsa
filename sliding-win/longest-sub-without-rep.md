## problem 
leetocode -> 3 
find the longest substring without repeating characters 
## code 
```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashSet<Character> set=new HashSet<>();
        int left=0;
        int maxlen=Integer.MIN_VALUE;
        if (s.length()<=1){
            return s.length();
        }
        for (int right=0;right<s.length();right++){
            char ch=s.charAt(right);
            while (set.contains(ch)){
                set.remove(s.charAt(left));
                left++;
            }
            set.add(s.charAt(right));
            maxlen=Math.max(maxlen,right-left+1);
        }
        return maxlen;
    }
}
```
