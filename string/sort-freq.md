## problem 
leet 451
sort the string in decerasing order of frequency 
eg tree -> eert 
## approach
place everything in a hashmap then find the max and keep appending the charcaters 
## code 
```
class Solution {
    public String frequencySort(String s) {
        HashMap<Character,Integer> map=new HashMap<>();
        StringBuilder ss=new StringBuilder();
        for (char c:s.toCharArray()){
            map.put(c,map.getOrDefault(c,0)+1);
        }
        int n=0;
        char ch=' '
        while(!map.isEmpty()){
            int max=Integer.MIN_VALUE;
            for (char c :map.keySet()){
                n=map.get(c);
                if (n>max){
                    ch=c;
                }
            }for (int i=0;i<n;i++){
                ss.append(ch);
            }
            map.remove(n);
        }
        return ss.toString();
    }
}
```
