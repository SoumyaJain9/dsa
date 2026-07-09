## problem 
misunderstood the ques 3765 
## code 
```
class Solution {
    public boolean completePrime(int num) {
        int suff=num%10;
        int pre=num;
        while(pre>=10){
            pre=pre/10;
        }
        if (num < 2 || pre < 2 || suff < 2)
        return false;
        for(int i=2;i*i<=num;i++){
            if(num%i==0){
                return false;
            }
        }
        for (int i=2;i*i<=suff;i++){
            if (suff%i==0){
                return false;
            }
        }
        for (int i=2;i*i<=pre;i++){
            if (pre%i==0){
                return false;
            }
        }
        return true;

        
    }
}
```
 checks if the number its prefix and suffix are prime
