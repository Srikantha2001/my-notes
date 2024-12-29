#Recursion 

```Java
class Solution {
    int getValue(int n, int k){
        if(n==1){
            return 0;
        }
        if(n==2) {
            return k-1;
        }
        if(k>(Math.pow(2,n-2))){
            int temp = k-(int)Math.pow(2,n-2);
            return 1-getValue(n-1,temp);
        }
        return getValue(n-1,k);
    }

    public int kthGrammar(int n, int k) {
        return getValue(n,k);
    }
}

```
