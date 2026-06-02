## problem 
single element in osrted array -> leet 540
## approach 
-> BS used 
-> BS is used by position odd or even 
eg-[1,1,2,2,3,4,4]
a valid pair will have (even,odd) position
## code 
```
class Solution {
    public int singleNonDuplicate(int[] nums) {
        int left=0;
        int right=nums.length-1;
        int ans=0;
        while(left<right){
            int mid=left+(right-left)/2;
            if (mid%2!=0 && nums[mid-1]==nums[mid]){
                left=mid+1; // bcz we have to skip just one number to move past the valid pair [1,1] (e,o)
                
            }
            else if(mid%2==0 && nums[mid+1]==nums[mid]){
                left=mid+2; // bcz we skip the whole pair like [1,1] (e,o)
                
            }
            else if (mid%2!=0 && nums[mid-1]!=nums[mid]){
                right=mid; // we dont skip bcz no valid pair found
            }
            else if (mid%2==0 && nums[mid+1]!=nums[mid]){
                right=mid;  // we dont skip bcz no valid pair found
               
            }
            else if (nums[mid]!=nums[mid-1]&& nums[mid]!=nums[mid+1]){
                return nums[mid];
            }
            
        }
        return nums[left];
        
    }
}
```
## shorter code 
```
class Solution {
    public int singleNonDuplicate(int[] nums) {
        int left=0;
        int right=nums.length-1;
        while(left<right){
            int mid=left+(right-left)/2;
            if (mid%2==1){
                mid--; //mid is even
            }
            if (nums[mid]==nums[mid+1]){
                left=mid+2;
            }
            else{
                right=mid;
            }
        }
        return nums[left];
        
    }
}
```
