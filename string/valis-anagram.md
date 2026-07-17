## problem 
leet -> 242
if two strings are of same lwngth same letters but in any order 

## appraoch 
make a hashmap add occuance then keep deducting the occurance for the second string 
finally u will have an empty hashmap 

## code 
```
class Solution {
    public boolean isAnagram(String s, String t) {
        HashMap<Character,Integer> map=new HashMap<>();
        if (s.length() != t.length()) {
            return false;
        }
        for (int i=0;i<s.length();i++){
            map.put(s.charAt(i),map.getOrDefault(s.charAt(i),0)+1);
            
        }
        for (char c :t.toCharArray()){
            if (!map.containsKey(c)){
                return false;
            }
            map.put(c,map.get(c)-1);
            if (map.get(c)==0){
                map.remove(c);
            }
        }
        return map.isEmpty();

        
    }
}
```
