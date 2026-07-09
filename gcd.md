## problem 
leetcode -> 1979
find gcd of array 
## appraoch 
find the min and max of array then find their gcd 
## code 
```
class Solution {
    public int findGCD(int[] nums) {
        int n=nums.length;
        int min=Integer.MAX_VALUE;
        int max=Integer.MIN_VALUE;
        for (int i=0;i<n;i++){
            if (min>nums[i]){
                min=nums[i];
            }
            if (max<nums[i]){
                max=nums[i];
            }
        }
        int ans=1;
        for (int i=min;i>=1;i--){
            if (max%i==0 && min%i==0){
                ans=i;
                break;
            }
        }
        return ans;
        
    }
}
```
