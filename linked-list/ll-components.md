## problem 
leet -> 817
find the number of connections in temp that are also in nums 

## code 
```
class Solution {
    public int numComponents(ListNode head, int[] nums) {
        HashSet<Integer> set=new HashSet<>();
        boolean previ=false;
        for (int num:nums){
            set.add(num);
        }
        int count=0;
        ListNode temp=head;
        while(temp!=null){
            boolean curi=set.contains(temp.val);
            if (set.contains(temp.val) && !previ){
                count++;
            }
            temp=temp.next;
            previ=curi;
        }
        return count;  
    }
}
```
## explaination
increase the countter wehenever temp.val is in nums AND the previous value was not in nums (i.e. new connection)
