## problem 
leet - > 496 
find the next greater element of the number in the second array.
## my approach 
```
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        Stack<Integer> s1= new Stack<>();
        for (int i=0;i<nums1.length;i++){
            int num=nums1[i];
            int len2=nums2.length-1;
            int num2=nums2[len2];
            int max=-1;
            while(num2!=num && len2>=0){
                if(num2>num){
                    max=num2;
                }
                len2--;
                num2=nums2[len2];  
            }
            nums1[i]=max;
        }
        return nums1;
    }
}
```
## optimal appraoch 
```
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        Stack<Integer> s1=new Stack<>();
        HashMap<Integer,Integer> map= new HashMap<>();
        for (int i=nums2.length-1;i>=0;i--){
            int num=nums2[i];
            while(!s1.isEmpty() && num>=s1.peek()){
               s1.pop();
            }
            if (s1.isEmpty()){
                map.put(num,-1);
            }else{
                map.put(num,s1.peek());
            } 
            s1.push(num);
        }
        int[] ans = new int[nums1.length];
        for (int i=0;i<nums1.length;i++){
            ans[i]=map.get(nums1[i]);
        }
        return ans;
    }
}
```
we use the monotonic stack approach and hashmap to store the next greater element of each number in nums2 then finally in the ans array we retrive teh numbers from the hashmap which were present in nums1
