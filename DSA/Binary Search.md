
### Variation 1 : Default

Verify if the element is present in the array or not using binary search

```Java
public boolean contains(int [] arr, int val){
		int left = 0;
		int right = arr.length - 1;
		
		while(left <= right) {
			int mid = left + (right - left)/2;
			
			// equal case , return true
			if(val == arr[mid]) return true;
			
			// value is left of mid, then discard right side
			else if (val < arr[mid] ) right = mid-1;
			
			// value is right of mid, then discard left side
			else left = mid+1;
		}
		
		// value not present
		return false;
	}
```

### Variation 2 : Finding the first Occurrence

- Find the index of first Occurrence of given value

```Java
public int firstOccurance(int [] arr, int val) {
		/*
		 *  	For Finding the first Occurance of an element, we use another variable to store the index when it is exact match and move left
		 */
		 int ans = -1;
		 int left = 0, right = arr.length-1;
		 
		 while(left <= right) {
			 int mid = left + (right - left)/2;
			 
			 if(val < arr[mid]) right = mid - 1;
			 else if (val > arr[mid]) left = mid + 1;
			 else {
				 ans = mid;
				 right = mid - 1;
			 }
		 }
		 return ans;
		 
	}
	
```

### Variation 3 : Find the last Occurrence

```Java
public int lastOccurance(int [] arr, int val){
		/*
		 *  	For Finding the last Occurance of an element, we use another variable to store the index when it is exact match and move right 
		 */ 
		 int ans = -1;
		 int left = 0, right = arr.length-1;
		 
		 while(left <= right) {
			 int mid = left + (right - left)/2;
			 if(val < arr[mid]) right = mid - 1;
			 else if(val > arr[mid]) left = mid + 1;
			 else {
				 ans = mid;
				 left = mid+1;
			 }
		 }
		 return ans;
	}
```

### Variation 4 : Find the Greatest element smaller than given element

```Java
public int greatestElementLesserThanValue(int [] arr, int val) {
	int ans = -1;
	int left = 0, right = arr.length - 1;
	while( left <= right) {
		int mid = left + (right - left)/2;
		if(val > arr[mid]) {
			ans = mid;
			left = mid +1;
		}
		else if (val < arr[mid]) right = mid - 1;
		else right = mid - 1;
	}
	return ans!=-1?arr[ans]:ans;
}
```

### Variation 5: Find the Smallest element greater than given element

```Java
public int leastElementGreaterThanValue(int [] arr, int val) {
		/*
		 * To find the least Element greater than given element, we update the ans whenever we get an element greater than the element and move left
		 */
		 int ans = -1;
		 int left = 0, right = arr.length -1;
		 while(left <= right) {
			 int mid = left + (right - left)/2;
			 if(val > arr[mid]) left = mid+1;
			 else if (val < arr[mid]) {
				 ans = mid;
				 right = mid - 1;
			 }
			 else left = mid + 1;
		 }
		 return ans!=-1?arr[ans]:ans;
	}

```

### Problems

| Problem Name                                                                                                                                  | Solution              |
| :-------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| [Minimum Platforms](https://www.geeksforgeeks.org/problems/minimum-platforms-1587115620/1?page=1&category=Binary%20Search&sortBy=submissions) | [[Minimum Platforms]] |
| [Aggressive Cows](https://www.geeksforgeeks.org/problems/aggressive-cows/1)                                                                   | [[Aggressive Cows]]   |

#### Resources
https://leetcode.com/discuss/interview-question/4203773/Binary-Search-variations/
https://leetcode.com/discuss/interview-question/1322500/5-variations-of-Binary-search-(A-Self-Note)
