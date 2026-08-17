## prob 
leet-> 19
## code 
```
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode temp=head;
        int c=0;
        while(temp!=null){
            c++;
            temp=temp.next;
        }
        int node=c-n;
        if (node==0){
            return head.next;
        }
        int c2=0;
        ListNode temp2=head;
        while(temp2!=null){
            c2++;
            if (c2==node){
                temp2.next=temp2.next.next;
            }
            temp2=temp2.next;
        }
        return head;
    }
}
```
