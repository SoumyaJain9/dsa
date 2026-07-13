## problem 
leet -> 240 
search target where every row is sorted in ascendinf order 
## code 
```
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int row=0;
        int col=matrix[0].length-1;
        while(row<matrix.length&& col>=0){
            if (matrix[row][col]==target){
                return true;
            }
            else if (matrix[row][col]>target){
                col--;
            }else{
                row++;
            }
        }
        return false;
        
    }
}
```
## appraoch 
in a matrix start comparing target with the last element of the first row 
if greater then reduce the col 
if lesser then increase the row
