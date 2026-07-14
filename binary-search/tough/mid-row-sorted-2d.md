## problem 
gfg
find the mdedian in a row wise sorted matrix
## code 
```
class Solution {
    public int median(int[][] mat) {

        int rows = mat.length;
        int cols = mat[0].length;
        int min = mat[0][0];
        int max = mat[0][cols - 1];

        for (int i = 1; i < rows; i++) {
            if (mat[i][0] < min) {
                min = mat[i][0];
            }

            if (mat[i][cols - 1] > max) {
                max = mat[i][cols - 1];
            }
        }

        while (min < max) {
            int mid = min + (max - min) / 2;
            int count=0;
            for (int i=0;i<rows;i++){
                int low=0;
                int high=cols-1;
                while (low<=high){
                    int m=low+(high-low)/2;
                    if (mat[i][m]<=mid){
                        low=m+1;
                    }else{
                        high=m-1;
                    }
                }
                count=count+low;
            }
            if (count<=(rows*cols)/2){
                min=mid+1;
            }else{
                max=mid;
            }
        }

        return min;
    }
}
```
## approach 
-> first we find the min and max values from the whole matrix i.e the first column and the last column
-> then we binary search across the values of mid eg is min element is 1 and max is 10 then mid is 5
-> then we look for values via binary search which are less than or equal to mid 
-> if the values are less thrn or equal to row*col/2 then yes it is the median 
return the median
