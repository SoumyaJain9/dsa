## problem 
leet -> 141 
return true if there is a cycle in the LL
## approach 
-> bruteforce using Hashset storing all the new elements whenver repetetion found return true else false 
## code 
```

public class Solution {
    public boolean hasCycle(ListNode head) {
        HashSet<ListNode> set=new HashSet<>();
        while(head!=null){
            if (set.contains(head)){
                return true;
            }
            set.add(head);
            head=head.next;
        }
        return false;       
    }
}
```
## optimal-appraoch 
(uisng floyd way)
using 2 pointers 
slow and fast 
(pointers moving in different speed must meet in a circular track)
## code 
```

public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode slow=head;
        ListNode fast=head;
        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
            if (slow==fast){
                return true;
            }
        }
        return false;
    }
}
```
