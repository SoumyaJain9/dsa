## problem 
find peak element unsorted -> leet 162
## appraoch 
binary search but with mid and mid+1 because unsorted
## code 
```
class Solution {
    public int findPeakElement(int[] nums) {
        int left=0;
        int right=nums.length-1;
        int max=-1;
        int ans=0;
        while(left<right){
            int mid = left + (right - left) / 2;
            if (nums[mid]<nums[mid+1]){
                left=mid+1;
            }else{
                right=mid-1;
            }
        }  
        return left;      
    }
}
```