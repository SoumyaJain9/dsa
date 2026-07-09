## problem 
leet-> 204 find the number of prime numbers till n
## brute force approach 
```
class Solution {
    public int countPrimes(int n) {
        if (n<=1){
            return 0;
        }
        int count=0;
        for (int i=2;i<n;i++){
            boolean prime=true;
            for (int j=2;j*j<=i;j++){
                if (i%j==0){
                    prime=false;
                    break;
                }
            }
            if (prime){
                count++;
            }
        }
        return count;
    }
}
```
  for (int j=2;j*j<=i;j++) -> this condition means that j starts from 2 and shud always be less than root of i
  eg- i=30 then j can be less than or equal to root of 30 which is approax 5 
  ## appraoch 
  for every number starting from 2 till i compare it with j and if i%j==0 thn the number is not prime
  ## optimal appraoch 
  ```
class Solution {
    public int countPrimes(int n) {
        if (n<=1){
            return 0;
        }
        boolean[] prime=new boolean[n];
        for (int i=0;i<n;i++){
            prime[i]=true;
        }
        for (int i=2;i*i<n;i++){
            if (prime[i]){
                for (int j=i*i;j<n;j=j+i){
                    prime[j]=false;
                }
            }
        }
        int count=0;
        for (int i=2;i<n;i++){
            if (prime[i]){
                count++;
            }
        }
        return count;
    }
}
```
## approach 
i*i<n means i < (int)Math.sqrt(n)
first we consider all the elements prime 
then take out 0 1 and 2 -> marking 
then we start from 2 to n -> inside this one more loop 
in this loop we mark the numbers false bcz 
eg - n=30 i< root of 30 which is 5  
then j= root of i (4) and less than n
