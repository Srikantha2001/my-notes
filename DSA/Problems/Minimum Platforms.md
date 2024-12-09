#BinarySearch
#Amazon #Microsoft #Paytm #DEShaw #Walmart #Google #Adobe #Atlassian


### Using Binary Search

```Java


// User function Template for Java
class Pair {
    public int x;
    public int y;
    
    Pair(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
class Solution {
    // Function to find the minimum number of platforms required at the
    // railway station such that no train waits.
    static int findPlatform(int arr[], int dep[]) {
        // add your code here
        
        List<Pair> timeDuration = new ArrayList<>();
        for(int i=0;i<arr.length;i++) {
            timeDuration.add(new Pair(arr[i], dep[i]));
        }
        Collections.sort(timeDuration, (p1,p2) -> (p1.x - p2.x));
        int [] depArray = timeDuration.stream().mapToInt(p -> p.y).sorted().toArray();
        int ans = 1;
        for(int i=1;i<arr.length;i++) {
            int idx = leastElementGreaterThanValue(depArray, timeDuration.get(i).x, i-1);
            ans = Math.max(i-idx+1, ans);
        }
        return ans;
        
    }
    
    static int leastElementGreaterThanValue(int [] arr, int val, int right) {
		 int ans = right+1;
		 int left = 0;
		 while(left <= right) {
			 int mid = left + (right - left)/2;
			 if(val > arr[mid]) left = mid+1;
			 else {
				 ans = mid;
				 right = mid - 1;
			 }
		}
		 return ans;
	}

}
```

### Alternate Approach

- sort both the arrays and use two pointers
```Java


// User function Template for Java
class Pair {
    public int x;
    public int y;
    
    Pair(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
class Solution {
    // Function to find the minimum number of platforms required at the
    // railway station such that no train waits.
    static int findPlatform(int arr[], int dep[]) {
        // add your code here
        Arrays.sort(arr);
        Arrays.sort(dep);
        int ai = 0, di =0;
        int ans = 0,finalAns = 0;
        while(ai<arr.length) {
            if(arr[ai] <= dep[di]) {
                ans++;
                ai++;
            }
            else {
                ans--;
                di++;
            }
            finalAns = Math.max(finalAns,ans);
        }
        return finalAns;
        
    }
    
    

}
```