## problem 
leet-> 2 
add two numbers given in linked list form in reversed order 
return the ans in reversed order too
## appraoch 
just add every signle digit in reverse order 
## code 
```
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode temp1=l1;
        ListNode temp2=l2;
        int carry=0;
        ListNode newNode=new ListNode(0);
        ListNode tail=newNode;
        while(temp1!=null || temp2!=null){
            int x=0;
            int y=0;
            if (temp1!=null){
                x=temp1.val;
                temp1=temp1.next;
            }
            if (temp2!=null){
                y=temp2.val;
                temp2=temp2.next;
            }
            int sum=x+y+carry;
            int digit=sum%10;
            carry=sum/10;
            tail.next=new ListNode(digit);
            tail=tail.next;
        }
        if (carry!=0){
            tail.next=new ListNode(carry);
        }
        return newNode.next;
        
    }
}
```
