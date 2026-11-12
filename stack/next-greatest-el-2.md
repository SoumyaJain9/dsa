## problem 
leet -> 503
find the next greatest elemtn of each num in the given circular array so teh last element points to the first element 
## code 
```
class Solution {
    public int[] nextGreaterElements(int[] nums) {
        Stack<Integer> s1= new Stack<>();
        int[] ans=new int[nums.length];
        for (int i=2*nums.length-1;i>=0;i--){
            int num=nums[i%nums.length];
            while(!s1.isEmpty() && s1.peek()<=num){
                s1.pop();
            }
            if (i<nums.length){
                if (s1.isEmpty()){
                    ans[i]=-1;
                }else{
                    ans[i]=s1.peek();
                }
            }
            s1.push(num);
        }
        return ans;  
    }
}
```
## explaiation
we dont ue hashmap in this but instead work with indexes bcz this is a circular array nums and if the array consists duplicate elelments it will give wrong answers.
