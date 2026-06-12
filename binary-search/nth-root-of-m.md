# problem 
find the nth root of m -> gfg
# code 
```
class Solution {
    public int nthRoot(int n, int m) {
        int left=0;
        int right =m;
        while (left<=right){
            int mid=left+(right-left)/2;
            long val=1;
            for (int i=0;i<n;i++){
                val=val*mid;
                if (val>m) break;
            }if (val==m){
                return mid;
            }else if (val<m){
                left=mid+1;
            }else{
                right=mid-1;
            }
        }
        return -1;
    }
}
```