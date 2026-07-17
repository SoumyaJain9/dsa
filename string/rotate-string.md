## problme 
leetcode ->796
## code 
```
class Solution {
    public boolean rotateString(String s, String goal) {
        if (s.length() != goal.length()) {
            return false;
        }

        return (s + s).contains(goal);
    }
}
```
