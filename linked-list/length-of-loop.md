## problem 
gfg -> count the number of nodes in cycle

## code 
```

class Solution {
    public int lengthOfLoop(Node head) {
        HashSet<Node> set=new HashSet<>();
        Node tmp=null;
        while(head!=null){
            if (set.contains(head)){
                tmp=head;
                break;
            }
            set.add(head);
            head=head.next;
            if (head==null){
                return 0;
            }
        }
        int c=0;
        Node curr=head.next;
        while(curr!=head){
            curr=curr.next;
            c++;
        }
        c++;
        return c;
        
    }
}
```
