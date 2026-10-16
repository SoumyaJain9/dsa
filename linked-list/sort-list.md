## problem 
leet-> 148 
## code 
```
class Solution {
    public ListNode sortList(ListNode head) {
        if (head==null||head.next==null){
            return head;
        }
        ListNode slow=head;
        ListNode fast=head;
        ListNode prev=null;
        while(fast!=null && fast.next!=null){
            prev=slow;
            slow=slow.next;
            fast=fast.next.next;
        }
        prev.next=null;
        ListNode left=sortList(head);
        ListNode right= sortList(slow);
        return merge(left,right);
        
    }
    private ListNode merge(ListNode left,ListNode right){
        ListNode dummy=new ListNode(0);
        ListNode tail=dummy;
        while(left!=null&& right!=null){
            if(left.val<=right.val){
                tail.next=left;
                left=left.next;
            }else{
                tail.next=right;
                right=right.next;
            }
            tail=tail.next;
        }if (left!=null){
            tail.next=left;
        }else{
            tail.next=right;
        }
        return dummy.next;
    }
}
```
## explaination 
first define a fucntion for always splitting the linked list from the middle 
then sort that recursively using merge sort 
