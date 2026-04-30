## problem 
return the arraylist with missing and repeating number -> gfg

## code 
using HashMap
```
import java.util.*;

class Solution {
    ArrayList<Integer> findTwoElement(int arr[]) {
        HashMap<Integer,Integer> map = new HashMap<>();
        int n = arr.length;
        int sum = 0;
        int rep = 0;
        int rs = 0;

        for (int i = 0; i < n; i++) {
            sum = sum + arr[i];
            rs = rs + i;

            if (map.containsKey(arr[i])) {
                rep = arr[i];
            } else {
                map.put(arr[i], 1);
            }
        }

        sum = sum - rep;
        rs = rs + n;

        int mis = rs - sum;

        ArrayList<Integer> result = new ArrayList<>();
        result.add(rep);
        result.add(mis);

        return result;
    }
}
```
TC=O(n)
SC=O(n)
## optimal appraoch 
use pure math logic using equations 
x^2-y^2=(x-y)(x+y)
TC=O(n)
SC=O(1)