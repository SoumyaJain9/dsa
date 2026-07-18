## problem 
leet -> 1614
## code 
```
class Solution {
    public int maxDepth(String s) {
        int n=s.length();
        int maxi=Integer.MIN_VALUE;
        int j=0;
        for (int i=0;i<n;i++){
            if( s.charAt(i)=='('){
                j++;
            }
            maxi=Math.max(maxi,j);
            if(s.charAt(i)==')'){
                j--;
            }
        }
        return maxi;  
    }
}
```
