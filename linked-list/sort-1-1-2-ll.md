## problem 
gfg -> sort 0s ,1s and 2s in linked list. 
## approach 
```

class Solution {
    public Node segregate(Node head) {
        ArrayList<Integer> arr=new ArrayList<>();
        Node temp=head;
        while(temp!=null){
            arr.add(temp.data);
            temp=temp.next;
        }
        Collections.sort(arr);
        temp=head;
        for (int i=0;i<arr.size();i++){
            temp.data=arr.get(i);
            temp=temp.next;
        }
        return head;
    }
}
```
## optimla approach 
```

class Solution {
    public Node segregate(Node head) {
        Node temp=head;
        int count0=0;
        int count1=0;
        int count2=0;
        while(temp!=null){
            if (temp.data==0){
                count0++;
            }else if (temp.data==1){
                count1++;
            }else{
                count2++;
            }
            temp=temp.next;
            
        }
        temp=head;
        while(count0>0){
            temp.data=0;
            count0--;
            temp=temp.next;
        }
        while(count1>0){
            temp.data=1;
            count1--;
            temp=temp.next;
        }
        while(count2>0){
            temp.data=2;
            count2--;
            temp=temp.next;
        }
        return head;
    }
}
```
