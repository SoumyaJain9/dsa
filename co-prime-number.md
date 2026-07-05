## problem 
leetcode -> 2748
tell the number of beautiful pairs or co prime numbers 

 ## approach 
 for any two numbers take out the first number of the first number eg - 3 from 31 
 and take out the last from the second number eg - 7 from 67 
 then -> on using euclidean theorem 
 7%3=1
 3%1=0
 yes they are a beautiful pair 

 ## code 
 ```
class Solution {
    public int countBeautifulPairs(int[] nums) {
        int n=nums.length;
        int count=0;
        int last=0;
        for(int i =0;i<n;i++){
            int first=nums[i];
            for (int j=i+1;j<n;j++){
                last=nums[j]%10;
                first=nums[i];
                while(first>=10){
                    first=first/10;
                }
// eucledian theroem
                while(last!=0){
                    int temp=last;
                    last=first%last;
                    first=temp;
                }
                if (first==1){
                    count++;
                }

            }
        }
        return count;
    }
}
```
