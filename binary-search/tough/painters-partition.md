## problem 
painters partition problem 
an array C (each element represents the length of ith board)  is given with A painters available where each takes B time to paint 1 unit of board 
## approach 
define the low = max out of elements in C
high= sum of all elements in C 
then apply BS 
put painters 1 and time 0 
mid is our guessed answer 
then put a for loop and keep adding time and painters
.....
## code 
```
public class Solution {
    public int paint(int A, int B, int[] C) {
        int max=Integer.MIN_VALUE;
        int sum=0;
        int ans=0;
        for (int num:C){
            if (max<num){
                max=num;
            }
            sum=sum+num;
        }
        int low=max;
        int high=sum;
        while(low<=high){
            int mid = low+(high-low)/2;
            int painters=1;
            int time=0;
            for (int i=0;i<C.length;i++){
                if (time+C[i]<=mid){
                    time=time+C[i];
                    
                }else {
                    painters++;
                    time=C[i];
                    
                }
            }
            if (painters <=A){
                ans=mid;
                high=mid-1;
            }else{
                low=mid+1;
            }
        }
        return (int)((long)ans * B % 10000003);
    }
}

```
