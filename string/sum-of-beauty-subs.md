## problem 
leet-> 1781
find their sum of beauty of all the possible substrings 
## appraoch 
using 3 nested loops for every string we find the max and min freq of every element 
and max - min= sum of beauty 
## code 
```
class Solution {
    public int beautySum(String s) {
        int ans=0;
        for (int i=0;i<s.length();i++){
            int [] arr= new int[26];
            for (int j=i;j<s.length();j++){
                arr[s.charAt(j)-'a']++;
                int max=0;
                int min=Integer.MAX_VALUE;
                for (int k=0;k<26;k++){
                    if (arr[k]>0){
                        max=Math.max(max,arr[k]);
                        min=Math.min(min,arr[k]);
                    }
                }
                ans=ans+(max-min);
            }
        }
        return ans;
        
    }
}
```
