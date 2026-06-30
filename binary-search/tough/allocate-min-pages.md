## problem 
gfg -> allocate min pages 
an array is given and each element represents the number of pages in ith book and we need to divide the books among the given number of students so that the max number of pages is minimized

## approach 
-> we use BS for the ans range 
low is the max element in the array 
high is the sum of all the elements i.e all the books were assigned to a single student 
if no of students is greater than no of books we return -1
-> mid is only a guess to the range of the ans and not the actual ans 
we take a guess mid and count the students among which the books are distributes
then we minimize our mid for optimized answer

## code 
```
class Solution {
    public int findPages(int[] arr, int k) {
        int max=Integer.MIN_VALUE;
        int sum=0;
        int ans=0;
        if (k>arr.length){
            return -1;
        }
        for (int num:arr){
            if (num>max){
                max=num;
            }
            sum=sum+num;
        }
        int low=max;
        int high=sum;
        while(low<=high){
            int mid=low+(high-low)/2;
            int students=1;
            int pages=0;
            for (int i=0;i<arr.length;i++){
                if (pages+arr[i]<=mid){
                    pages=pages+arr[i];
                }else{
                    students++;
                    pages=arr[i];
                    
                }
                
            }
            if (students<=k){
                    high=mid-1;
                    ans=mid;
                }else{
                    low=mid+1;
                }
            
        }
        return ans;
    }
}
```
