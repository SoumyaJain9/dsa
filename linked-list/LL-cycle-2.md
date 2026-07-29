## problem 
leet 142
return the index where the tail is connectting to make a cycle else null 
## appraoch 
hashset 
## code 
```

public class Solution {
    public ListNode detectCycle(ListNode head) {
        HashSet<ListNode> set=new HashSet<>();
        while(head!=null){
            if (set.contains(head)){
                return (head);
            }
            set.add(head);
            head=head.next;
        }
        return null;
        
    }
}
```
## optimal appraoch 
The distance from head → cycle start is exactly the same as the distance from meeting point → cycle start (moving around the cycle).
and we have head and meetinf point -> cycle start point is exactly the same distance away from both so wehver htey are equal cycle starts 
## code 
```

public class Solution {
    public ListNode detectCycle(ListNode head) {
        ListNode slow=head;
        ListNode fast=head;
        while (fast!=null&& fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
            if (slow==fast){
                ListNode ptr=head;
                while (ptr!=slow){
                    ptr=ptr.next;
                    slow=slow.next;
                }
                return ptr;
            }      
        }
        return null;    
    }
}
```
