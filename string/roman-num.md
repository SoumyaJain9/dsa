## problem 
leet -> 13 
tell the roman from the string 

## code 
```
class Solution {
    public int romanToInt(String s) {
        HashMap<Character,Integer> map=new HashMap<>();
        map.put('I',1);
        map.put('V',5);
        map.put('X',10);
        map.put('L',50);
        map.put('C',100);
        map.put('D',500);
        map.put('M',1000);
        int ans=map.get(s.charAt(s.length()-1));
        if (s.length()==1){
            return map.get(s.charAt(0));
        }
        for (int i=s.length()-2;i>0;i--){

            if (map.containsKey(s.charAt(i))){
                if (map.get(s.charAt(i))>=map.get(s.charAt(i+1))){
                    ans=ans+map.get(s.charAt(i));
                }
                else{
                    ans=ans-map.get(s.charAt(i));
                }
            }
        }
        if (map.get(s.charAt(0)) >= map.get(s.charAt(1))) {
            ans=ans+map.get(s.charAt(0));
        }
        else{
            ans=ans-map.get(s.charAt(0));
        }
        
        return ans;
        
    }
}
```
