## problme 
leet-> 1019 
## code 
```

class Solution {
    public int[] nextLargerNodes(ListNode head) {
        ArrayList<Integer> arr= new ArrayList<>();
        ListNode temp=head;
        while(temp!=null){
            ListNode temp2=temp;
            int ans=0;
            while(temp2!=null){
                if (temp.val<temp2.val){
                    ans=temp2.val;
                    break;
                }
                temp2=temp2.next;
            }
            arr.add(ans);
            temp=temp.next;
        }
        int[] result=new int[arr.size()];
        for (int i=0;i<arr.size();i++){
            result[i]=arr.get(i);
        }
        return result;
        
    }
}
```
