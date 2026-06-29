## problem 
leetcode -> 1283 find the smallest diviser given the threshold
## approach 
->we find the smallest diviser so that when that diviser divides the array and give a ceil answer the sum is less than or equal to the given threshold.
->we use BS method across the range of possible divisers and not the array i.e min=1 , max=max(array)
->ceil means round up 
## code 
```
class Solution {
    public int smallestDivisor(int[] nums, int threshold) {
        int low=1;
        int max = Integer.MIN_VALUE;
        for (int num : nums) {
            if (num > max) {
                max = num;
            }
        }
        int high =max;
        int ans=0;
        while(low<=high){
            int mid=low+(high-low)/2;
            int sum=0;
            for (int num:nums){
                sum=sum+(num+mid-1)/mid;
            }
            if (sum<=threshold){
                ans=mid;
                high=mid-1; 
            }else {
                low=mid+1;
            }
        }
        return ans;
        
    }
}
``` 