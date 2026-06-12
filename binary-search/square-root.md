# problme 
find square root of the number in log n -gfg
# approach 
BS 
# code 
```
class Solution {
    int floorSqrt(int n) {
        int left=0;
        int right=n;
        int ans=0;
        while(left<=right){
            int mid=left+(right-left)/2;
            if (mid*mid<=n){
                left=mid+1;
                ans=mid;
            }else{
                right=mid-1;
            }
        }
        return ans;
        
    }
}
```