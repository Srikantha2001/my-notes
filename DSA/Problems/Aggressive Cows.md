#BinarySearch 

- Variation of Binary Search which involve finding answer by applying Binary search on all possible answers
```Java


// User function Template for Java
class Solution {
    public static int aggressiveCows(int[] stalls, int k) {
        // code here
        
        Arrays.sort(stalls);
        int right = stalls[stalls.length-1] - stalls[0];
        int ans = 0,left = 0;
        while(left <= right) {
            int mid = left + (right - left)/2;
            if(isPossible(stalls,k,mid)) {
                ans = mid;
                left = mid + 1;
            }
            else right = mid -1;
        }
        return ans;
    }
    private static boolean isPossible(int [] stalls, int k, int x) {
        int cur = stalls[0];
        k--;
        for(int i=1;i<stalls.length;i++){
            if((cur+x) <= stalls[i]) {
                k--;
                cur = stalls[i];
            }
        }
        return k<=0;
    }
}
```