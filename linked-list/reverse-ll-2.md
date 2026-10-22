## problem 
leet-> 92 
reverse the linked list from given positions from left to right 

## code 
```
class Solution {
    public ListNode reverseBetween(ListNode head, int left, int right) {
        if (head==null||left==right){
            return head;
        }
        ListNode dummy= new ListNode(0);
        dummy.next=head;
        ListNode prev=dummy;
        for (int i=1;i<left;i++){
            prev=prev.next;
        }
        ListNode curr=prev.next;
        for (int i=0;i<right-left;i++){
            ListNode next=curr.next;
            curr.next=next.next;
            next.next=prev.next;
            prev.next=next;
        }
        return dummy.next;
    }
}
```

## explaiantion 
first traverse the linked list before the given left location 
then reverse the linked list normally till the given right position 
do not return head in the last bcz head can change if the node which head iis pointing to is chnaged therefore we need a new node which is dummy.next to return 
