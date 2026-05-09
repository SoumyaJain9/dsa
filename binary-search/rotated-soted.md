## problem 
search in rotated sorted array 1 -> leet 33
## appraoch 
if the array is roated at some pivot then one of the half must be sorted 
-> do usual binary search 
-> if the arr[mid] is target then return target
-> if not then first check which side is sorted side (because BS works with sorted arrays)
-> if the left side is sorted and the target lies in the left side shrink the right half else shrink the left side 
-> else if the right side is sorted and the target lies in the right side then shrink the left side else shrink the right side 
-> return -1;
## code 
```
class Solution {
    public int search(int[] nums, int target) {
        int left=0;
        int right=nums.length-1;
        int ans=0;
        while(left<=right){
            int mid=left+(right-left)/2;
            if (nums[mid]==target){
                return mid;
            }
            if (nums[left]<=nums[mid]){
                if (nums[left]<=target && nums[mid]>=target){
                    right=mid-1;
                }else{
                    left=mid+1;
                }
            }
            else if (nums[mid]<=nums[right]){
                if (nums[mid]<=target && nums[right]>=target){
                    left=mid+1;
                }else{
                    right=mid-1;
                }
            }
        }
        return -1;    
    }
}
```
## problem 
search in rotated sorted array 2 -> leet 81 (can contain duplicate values)
## approach 
-> do usual BS
-> if arr[mid] is equal to target return true
-> if arr[left]==arr[mid]==arr[right] do left++ and right-- (for handling duplicates)
-> else if left half is sorted and target is in left then shrink right else shrink left 
-> else if right half is sorted and target is in right then shrink left else shrink right
-> return false 
## code
```
class Solution {
    public boolean search(int[] nums, int target) {
        int left=0;
        int right=nums.length-1;
        int ans=0;
        while(left<=right){
            int mid=left+(right-left)/2;
            if (nums[mid]==target){
                return true;
            }
            if (nums[left]==nums[mid] && nums[mid]==nums[right]){
                left++;
                right--;
            }
            else if(nums[left]<=nums[mid]){
                if (nums[left]<=target && nums[mid]>=target){
                    right=mid-1;
                }else{
                    left=mid+1;
                }
            }
            else if (nums[mid]<=nums[right]){
                if (nums[mid]<=target && nums[right]>=target){
                    left=mid+1;
                }else{
                    right=mid-1;
                }
            }
        }
        return false;    
    }
}
```
## problem 
min in rotated soretd array (leet -> 153)
## approach 
the min will always be in unsorted part of the array 
[7,8,1,3,4]
[4,5,6,7,0,1,2]
-> while condition with left < right ( as left=right can give infinite loop condition)
-> first we find out the mid (1,7)
-> then we shrink the array to whichever side is not sorted 
Note- while shrinking 
in eg 1 we do right = mid (as the mid might be the min itself doing mid-1 will abandon the min)
in eg 2 we do left = mid+1 (as when left < right i.e 4<7 then mid is not the min element therefore no harm in doing mid+1)
-> return nums[left] or nums[right] bcz the while loop breaks when left==right
## code 
```
class Solution {
    public int findMin(int[] nums) {
        int left=0;
        int right=nums.length-1;
        while(left<right){
            int mid=left+(right-left)/2;
            if (nums[mid]<=nums[right]){
                right=mid;
            }
            else {
                left=mid+1;
            }
        }
        return nums[right];    
    }
}
```