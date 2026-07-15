## problem 
leet->1903 
find the largest substring from a given string 
## appraoch 
start looking from the last when u find odd number return 
## code 
```
class Solution {
    public String largestOddNumber(String num) {
        StringBuilder ss= new StringBuilder();
        int n=num.length();
        for (int i=n-1;i>=0;i--){
            if (num.charAt(i)%2!=0){
                return num.substring(0, i + 1);
            }
        }
        return "";
    }
}
```
