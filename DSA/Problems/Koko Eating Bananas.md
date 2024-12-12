 #BinarySearch #Amazon #Atlassian #Microsoft #Uber
 - Solution is very similar to Aggressive Cows problem
```Java
class Solution {
    public int minEatingSpeed(int[] piles, int h) {
        int left = 1;
        int right = 0;
        for(int pile:piles) right = Math.max(right,pile);
        right++;
        int ans = 0;
        while(left <= right) {
            // System.out.println(left+" "+right);
            int mid = left + (right - left)/2;
            if(isPossible(piles,h,mid)) {
                ans = mid;
                right = mid - 1;
            }
            else {
                left = mid + 1;
            }
        }
        return ans;
    }

    public boolean isPossible(int [] piles, int availableHours, int bananasPerHour) {
        long hoursRequired = 0L;
        for(int pile:piles) {
            hoursRequired += (long)pile/bananasPerHour;
            if(pile%bananasPerHour != 0) hoursRequired++;
        }
        // System.out.println("Hours available for "+ bananasPerHour +" is "+hoursRequired);
        return hoursRequired <= (long)availableHours;
    }
}

```