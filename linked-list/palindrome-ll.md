## prob 
leet- 234
## cpde 
 ```
class Solution {
    public boolean isPalindrome(ListNode head) {
        ArrayList<Integer>arr= new ArrayList<>();
        ListNode temp=head;
        while(temp!=null){
            arr.add(temp.val);
            temp=temp.next;
        }
        int j=arr.size()-1;
        for (int i=0;i<arr.size()/2;i++){
            if (!arr.get(i).equals(arr.get(j))){
                return false;
            }
            j--;

        }
        return true;
        
    }
}
```
