## problem 
leet-> 1456
find the max num of vowels in a substring of given length k 
## approach 
sliding window 
## code 
```
class Solution {
    public int maxVowels(String s, int k) {
        int c=0;
        for (int i=0;i<k;i++){
            char ch=s.charAt(i);
            if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'){
                c++;
            }
        }
        int cmax=c;
        for (int i=k;i<s.length();i++){
            char ph=s.charAt(i);
            char gh=s.charAt(i-k);
            if (ph=='a'||ph=='e'||ph=='i'||ph=='o'||ph=='u'){
                c++;
            }
            if (gh=='a'||gh=='e'||gh=='i'||gh=='o'||gh=='u'){
                c--;
            }
            cmax=Math.max(c,cmax);
        }
        return cmax;
        
    }
}
```
