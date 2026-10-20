## problem 
leet -> 1290 
convert the given num in linked list from binary to decimal 

## code 
```
class Solution {
    public int getDecimalValue(ListNode head) {
        ListNode temp=head;
        int num=0;
        while(temp!=null){
            num=num*2+temp.val;
            temp=temp.next;
        }
        return num;
        
    }
}
```

## explaiantion 
formula -> num=num*2+temp.val
