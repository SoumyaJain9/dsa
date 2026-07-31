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
## code - dl
```
class Solution {
    Node reverseDLL(Node head) {
        if (head == null || head.next == null) {
            return head;
        }
        Node curr = head;
        Node temp = null;
        while (curr != null) {
            temp = curr.prev;
            curr.prev = curr.next;
            curr.next = temp;
            curr = curr.prev;
        }
        if (temp != null) {
            head = temp.prev;
        }
        return head;
    }
}
```
