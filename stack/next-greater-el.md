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
