# problem 
You have a row of flowers, where each flower blooms after a specific day. The array arr[] represents the blooming schedule: arr[i] is the day the flower at position i will bloom. To create a bouquet, you need to collect k adjacent bloomed flowers. Each flower can only be used in one bouquet.

Your goal is to find the minimum number of days required to make exactly m bouquets. If it is not possible to make m bouquets with the given arrangement, return -1. -> gfg 
# approach 
if flower*bouquet > arr.length return -1 
first find out the search space min and max numbers in array 
then count the number of bouquets by updating flowers 
then use binary search for exact number of bouquets asked 
# code 
``` 
class Solution {
    public int minDaysBloom(int[] arr, int k, int m) {
        if ((long)m * k > arr.length)
            return -1;
        int low = Integer.MAX_VALUE;
        int high = Integer.MIN_VALUE;

        for (int day : arr) {
            low = Math.min(low, day);
            high = Math.max(high, day);
        }
        int ans=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            int bouquets = 0;
            int flowers = 0;
            for (int day:arr){
                if (day<=mid){
                    flowers++;
                    if (flowers==k){
                        bouquets++;
                        flowers=0;
                    }
                }else{
                    flowers=0;
                }
            }
            if (bouquets>=m){
                high=mid-1;
                ans=mid;
            }
            else{
                low=mid+1;
            }
        }
        return ans;
        
    }
}
```