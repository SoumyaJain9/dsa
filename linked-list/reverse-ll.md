## problem 
leet-> 206 
reverse single ll 
## code 
```
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode temp=head;
        ListNode newhead=null;
        ListNode prev=null;
        while(temp!=null){
            ListNode tmp=temp.next;
            temp.next=prev;
            prev=temp;
            newhead=temp;
            temp=tmp;
        } 
        return newhead;
    }
}
```
