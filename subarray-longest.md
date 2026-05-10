## problem
return the length of thr longest subarray with sum k -> gfg
## brute force 
take out all subrarrays and tell teh longest
## approach 
```
class Solution {
    public int longestSubarray(int[] arr, int k) {
        int n=arr.length;
        int sum=0;
        int count=0;
        int maxlen=0;
        HashMap<Integer,Integer> map=new HashMap<>();
        for (int i=0;i<n;i++){
            sum=sum+arr[i];
            if (sum==k){
                maxlen=i+1;
            }
            if (map.containsKey(sum-k)){
                int val=i-map.get(sum-k);
                maxlen=Math.max(maxlen,val);
                
            }
            if (!map.containsKey(sum)){
                map.put(sum,i);
            }
            
        }
        return maxlen;
    }
}

```
## explaination
first make a hashmap
then put the base condition (0,1)-> very imp as sometimes the subarray starts from the start so we need 0 as the sum to take subarray from the start 
prefix = sum till that index 
we use (prefix(i) -prefix(j)=k) where prefix i is current index and prefix j is some previous index 
we reaarange this to (prefix(i)-k=prefix(j)) i.e (sum-k)
and if the sum-k exits in the hashmap then it means that there has been subarray(s) where the subarray sum is k 
for max len 
we just store <sum,index>
and comapre the maxlen each tiem there is a subarray 
we also dont overwrite the earlier indexes -> (!map.containsKey(sum))