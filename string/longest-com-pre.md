## problem 
leet- 14 
find the longest common prefix 
## code 
(using inbuild functions)
```
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String pre=strs[0];
        for (int i=1;i<strs.length;i++){
            if (!strs.startsWith(pre)){
                pre=pre.substring(0,pre.lenght-1);
            }
        }
        return pre;
    }
}
```
## code 
(using logic)
```
class Solution {
    public String longestCommonPrefix(String[] strs) {
        for (int i=0;i<strs[0].length();i++){
            for (int j=1;j<strs.length;j++){
                if (i==strs[j].length()|| strs[j].charAt(i)!=strs[0].charAt(i)){
                    return strs[0].substring(0,i);
                }
            }
        }
        return strs[0];
    }
}
```
