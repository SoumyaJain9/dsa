## problem 
gfg remove the given integer from the linked list 
## code 
```


class Solution {
    public Node deleteAllOccurOfX(Node head, int x) {
        Node temp=head;
        while(temp!=null){
            if(temp.data==x){
                if(temp==head){
                    head=temp.next;
                }
                Node nextNode=temp.next;
                if (temp.prev!=null){
                    temp.prev.next=temp.next;
                }
                if(temp.next!=null){
                    temp.next.prev=temp.prev;
                }
                temp=nextNode;
            }else{
                temp=temp.next;
            }
        }
        return head;
    }
}
```
