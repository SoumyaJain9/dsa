## problme 
tuf platform 
implement stack using array
## code 
```
class ArrayStack {
    int[] arr;
    int l;
    public ArrayStack() {
        arr=new int[10000];
        l=0;
    }

    public void push(int x) {
        arr[l]=x;
        l++;
    }

    public int pop() {
        l--;
        return arr[l];
    }
    public int top() {
        return arr[l-1];
        
    }

    public boolean isEmpty() {
        if (l==0){
            return true;
        }else{
            return false;
        }
    }
}

```
