## problem 
floor in sorted arrray -> gfg 
return the largest number less than or equal to the target given (from a sorted array)
## code 
```
class Solution {
    public int findFloor(int[] arr, int x) {
        int n=arr.length;
        int left=0;
        int right=n-1;
        int ans =-1;
        while(left<=right){
            int mid=left+ (right-left)/2;
            if (arr[mid]>x){
                right=mid-1;
            }
            if (arr[mid]<=x){
                ans=mid;
                left=mid+1;
            }
        }
        return ans;
    }
}
```
## problem 
floor and ceil in unsorted array -> gfg
## code 
```
class Solution {
    public int[] getFloorAndCeil(int x, int[] arr) {
        int n=arr.length;
        int floor=-1;
        int ceil=-1;
        for (int i=0;i<n;i++){
            if (arr[i]<=x){
                floor=Math.max(arr[i],floor);
            }if (arr[i]>=x){
                if (ceil==-1|| arr[i]<ceil){
                    ceil=arr[i];
                }
                
            }
        }
        return new int[]{floor,ceil};    }
}
```
## peoblem 
ceil in osrted array -> gfg 
## code 
```
class Solution {
    public int findCeil(int[] arr, int x) {
        int left=0;
        int right=arr.length-1;
        int ans =-1;
        while (left<=right){
            int mid =left +(right-left)/2;
            if (arr[mid]<x){
                left=mid+1;
            }
            else{
                ans=mid;
                right=mid-1;
            }
        }
        return ans;
    }
}
```