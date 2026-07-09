## problem 
leetcode -> 7 reverse the integer can be nagative or positive and if the number overflows the integer range then return 0.
## code 
```
class Solution {
    public int reverse(int n) {
        int rev=0;
        int p=0;
        while(n!=0){
            p=n%10;
            if (rev>Integer.MAX_VALUE/10||rev==Integer.MAX_VALUE/10 && p>7){
                return 0;
            }
            if (rev < Integer.MIN_VALUE / 10 ||
               rev == Integer.MIN_VALUE / 10 && p < -8){
                return 0;
            }
            rev=rev*10+p;
            n=n/10;

        }
        return rev;

        
    }
}
```
## appraoch
everything normal just add the condition of over flow that if rev is greater than max value/10 ....etc 
-> we check max value/10 bcz the next operation is rev=rev*10 
note-
Integer.MAX_VALUE = 2147483647
Integer.MIN_VALUE = -2147483648
now the last values we p is the last digit therfore if rev == Integer.MAX.VALUE/10 then if p is greater than 7 then  if we multifly 10 int will overflow
