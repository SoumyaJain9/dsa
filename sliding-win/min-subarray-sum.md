## problem
leet-> 209
find the minimal length of the subarray whos sum is greater than or equal to the given target.
## approach 
sliding window 
## code 
```
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int left=0;
        int minlen=Integer.MAX_VALUE;
        int sum=0;
        for (int right=0;right<nums.length;right++){
            sum=sum+nums[right];
            while(sum>=target && left<nums.length){
                minlen=Math.min(minlen,right-left+1);
                sum=sum-nums[left];
                left++;
            }
        }
        if (minlen == Integer.MAX_VALUE) {
            return 0;
        }
        return minlen;
        
    }
}
```
