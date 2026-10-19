## problem 
leet-203
## code 
```

class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode temp=head;
        if (head==null){
            return head;
        }
        while(head!=null && head.val==val){
            head=head.next;
        }
        while(temp.next!=null){
            if(temp.next.val==val){
                temp.next=temp.next.next;
            }else{
                temp=temp.next;
            }
        }
        return head; 
    }
}
```
## explaiantion 
to delete a node we need to move temp.next to the desired node 
