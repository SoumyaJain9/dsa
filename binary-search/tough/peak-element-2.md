## problem 
leetcode -> 1901
find the peak elemtn in a 2d array or a matrix
## code 
```
class Solution {
    public int[] findPeakGrid(int[][] mat) {
        int col=mat[0].length;
        int row=mat.length;
        int low=0;
        int high=col-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            int maxrow=0;
            for (int i=1;i<row;i++){
                if (mat[i][mid]>mat[maxrow][mid]){
                    maxrow=i;
                }
            }
            int left=(mid>0)?mat[maxrow][mid-1]:-1;
            int right=(mid<col-1)?mat[maxrow][mid+1]:-1;
            if (mat[maxrow][mid]>left && mat[maxrow][mid]>right){
                return new int[] {maxrow,mid};
            }
            else if (left>mat[maxrow][mid]){
                high=mid-1;
            }else{
                low=mid+1;
            }

        }
        return new int[]{-1, -1};

        
    }
}
```
## approach 
we are using binary search for columns to find the mid column 
then we find the max number in that column
then we check the left and right of that number 
if left is greter then we put high = mid+1
if right is gretaer then we put low=mdid-1
else we have the peak element
