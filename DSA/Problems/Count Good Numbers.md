#Recursion 

- As Given in the problem
	- for even indices, we have following choices <mark style="background: #D2B3FFA6;">{0, 2, 4, 6, 8}</mark> => total <mark style="background: #FFF3A3A6;">5</mark> choice
	- For Odd indices, we have following choices <mark style="background: #D2B3FFA6;">{ 2, 3, 5, 7}</mark> => total <mark style="background: #FFF3A3A6;">4</mark> choice

- the number of choices look something like this => (5 * 4 * 5 * 4 * .....) => (20 * 20 * ... )

	 ![[countGoodNumber.png]]

- For finding the power, we use matrix exponentiation method to find the power

```Java
class Solution {
    private static int MOD_VAL = 1000000007;

    public int calculatePower(int a, long b, long base) {
        if(b==0) return 1;
        return ((b & 1) == 1) ? (int)((base* calculatePower(a, b>>1, (base*base)%MOD_VAL))%MOD_VAL) : calculatePower(a, b>>1, (base*base)%MOD_VAL);
    }
    public int countGoodNumbers(long n) {
        long count = n/2;
        int ans = calculatePower(20, count, 20);
        return (n%2==0)? ans: (int)((ans*(long)5)%MOD_VAL);
    }
}
```