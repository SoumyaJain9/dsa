## problem 
leet-> 148
sort the linked list 
## appraoch 
make an arraylist and copy ll into it sort it and then copy it to the linked list back 
## code 
```
class Solution {
    public ListNode sortList(ListNode head) {
        ListNode temp=head;
        ArrayList<Integer> arr =new ArrayList<>();
        while(temp!=null){
            arr.add(temp.val);
            temp=temp.next;
        }
        Collections.sort(arr);
        temp = head;
        for (int i = 0; i < arr.size(); i++) {
            temp.val = arr.get(i);
            temp = temp.next;
        }
        return head;
    }
}
```
## optimal approach 
