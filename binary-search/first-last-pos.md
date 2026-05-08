## problem 
find the first and last position of a given target in a sorted array ( leet -> 34)
## appraoch 
we search for the border element by applying BS two times 
-> in the findFirst BS we always move towards left
-> in the findLast BS we always move towards right 
## code 
```
class Solution {
    public int[] searchRange(int[] nums, int target) {
        int first = findFirst(nums, target);
        int last = findLast(nums, target);
        return new int[]{first, last};
    }

    private int findFirst(int[] nums, int target) {
        int left = 0, right = nums.length - 1;
        int ans = -1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) {
                ans = mid;
                right = mid - 1; // move left
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
    }

    private int findLast(int[] nums, int target) {
        int left = 0, right = nums.length - 1;
        int ans = -1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) {
                ans = mid;
                left = mid + 1; // move right
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
    }
}
```
## problem 
tell the number of occurance of a given target in sorted array (gfg)
## code 
```
class Solution {
    int countFreq(int[] arr, int target) {
        int left=findLeft(arr,target);
        if (left==-1){
            return 0;
        }
        int right =findRight(arr,target);
        return right-left+1;
    }
        private int findLeft(int[] arr,int target){
            int left=0;
            int right=arr.length-1;
            int ans=-1;
            while(left<=right){
                int mid=left+(right-left)/2;
                if (arr[mid]==target){
                    ans=mid;
                    right=mid-1;
                }else if (arr[mid]<target){
                    left=mid+1;
                }else{
                    right=mid-1;
                }
            }
            return ans;
        }
        private int findRight(int[] arr,int target){
            int left=0;
            int right=arr.length-1;
            int ans=-1;
            while(left<=right){
                int mid=left+(right-left)/2;
                if (arr[mid]==target){
                    ans=mid;
                    left=mid+1;
                }else if(arr[mid]<target){
                    left=mid+1;
                }else{
                    right=mid-1;
                }
            }
            return ans;
        }
}
```
