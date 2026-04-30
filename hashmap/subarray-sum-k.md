## problem
return the num of subarrays with sum k -> 560
## brute force 
two nestes loops
adding on elements with the beginning position fixed then moving to the next element (next to beginning)
Time: O(n²)
Space: O(1)

## explaination 
first make a hashmap
then put the base condition (0,1)-> very imp as sometimes the subarray starts from the start so we need 0 as the sum to take subarray from the start 
prefix = sum till that index 
we use (prefix(i) -prefix(j)=k) where prefix i is current index and prefix j is some previous index 
we reaarange this to (prefix(i)-k=prefix(j)) i.e (sum-k)
and if the sum-k exits in the hashmap then it means that there has been subarray(s) where the subarray sum is k 

## edge case 
if array has only one elemnt 
if all elements are zero 
negative numbers

## code
```
class Solution {
    public int subarraySum(int[] nums, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int sum=0;
        int count=0;
        map.put(0,1);
        for (int num:nums){
            sum=sum+num;
            if (map.containsKey(sum-k)){
                count=count+map.get(sum-k);
            }
            map.put(sum,map.getOrDefault(sum,0)+1);
        }
        return count;   
    }
}
```
TC & SC = O(n)
