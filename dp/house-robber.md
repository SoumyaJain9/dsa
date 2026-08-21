## problem
leet-> 198 
tell the max robbery that can be done just nto from adjacent houeses or you will be caught 
## code 
```
class Solution {
    public int rob(int[] nums) {
        if (nums.length<=1){
            return nums[0];
        }
        int prev2=nums[0];
        int prev1=Math.max(nums[0],nums[1]);
        for (int i=2;i<nums.length;i++){
            int take=nums[i]+prev2;
            int nottake=prev1;
            int cur=Math.max(take,nottake);
            prev2=prev1;
            prev1=cur;
        }
        return prev1; 
    }
}
```
