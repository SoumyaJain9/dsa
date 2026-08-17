## problem 
leet-> 2095 
## approach (code)
```
class Solution {
    public ListNode deleteMiddle(ListNode head) {
        ListNode temp=head;
        int c=0;
        while(temp!=null){
            c++;
            temp=temp.next;
        }
        int mid=c/2;
        if (mid==0){
            return head.next;
        }
        int c2=0;
        ListNode temp2=head;
        while(temp2!=null){
            c2++;
            if (c2==mid){
                temp2.next=temp2.next.next;
            }
            temp2=temp2.next;
        }
        return head;
        
    }
}
```
## optimal appraoch 
```
