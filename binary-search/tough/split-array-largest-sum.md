## problem 
leetcode -> 410 
similar to allocation of pages 
divide the array into subarrays with the given k and minimize the max subarray sum 
## approach 
similar to allocation of pages 
## code 
```
class Solution {
    public int splitArray(int[] nums, int k) {

        int max = Integer.MIN_VALUE;
        int sum = 0;
        int ans = 0;

        for (int num : nums) {
            if (num > max) {
                max = num;
            }
            sum += num;
        }

        int low = max;
        int high = sum;

        while (low <= high) {

            int mid = low + (high - low) / 2;

            int subarray = 1;
            int sumOfSub = 0;

            for (int i = 0; i < nums.length; i++) {

                if (sumOfSub + nums[i] <= mid) {
                    sumOfSub += nums[i];
                } else {
                    subarray++;
                    sumOfSub = nums[i];
                }
            }

            if (subarray <= k) {
                ans = mid;
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }

        return ans;
    }
}
```
