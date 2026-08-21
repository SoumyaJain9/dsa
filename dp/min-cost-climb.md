## problem 
leet-> 746 
find the min cost way to reach the top step either starting from 1st index or 2nd index i.r (n-1) and (n-2).
## code 
```
class Solution {
    public int minCostClimbingStairs(int[] cost) {
        int prev2=cost[0];
        int prev1=cost[1];
        for (int i=2;i<cost.length;i++){
            int cur = cost[i]+Math.min(prev1,prev2);
            prev2=prev1;
            prev1=cur;
        }
        return Math.min(prev1,prev2);
    }
}
```
