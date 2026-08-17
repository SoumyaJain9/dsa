## prob 
leet-> 328 sort the the linked list by odd even indices 
## approach 
two pointer appraoch 
## code 
```
class Solution {
    public ListNode oddEvenList(ListNode head) {
        if (head==null||head.next==null){
            return head;
        }
        ListNode point1=head;
        ListNode point2=head.next;
        ListNode even=head.next;
        
        while(point1.next!=null&& point2.next!=null){
            point1.next=point2.next;
            point1=point1.next;
            point2.next=point1.next;
            point2=point2.next;
        }
        point1.next=even;
        return head; 
    }
}
```
