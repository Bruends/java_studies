# Binary Search

- locate a specific value in a *sorted collection*.
- scales well with large collections
- as a complexity of "O(log n)"

#### Steps
1. Compare the *middle value* of the collection with the *target value*
2. if (*Middle* == *Target*) -> Success! (end)
3.  If cannot divide the collection in half anymore -> value not found! (end) 
4. Divide the collection in half
5. If (*Middle* > *target*) ->  Continues the lower half of the collection 
	- Continue with upper half otherwise
6. Repeat the step one 
#### Code: 

```java
public class Main {  
	public static void main(String[] args) {  
		int[] collection = {1, 2, 5, 8, 9, 11, 15};  
		int target = 11;  
		  
		System.out.println(binarySearch(collection, target)); // 5  
		System.out.println(binarySearch(collection, -1)); // null  
	}  
	  
	public static Integer binarySearch(int[] collection, int target) {  
		// Search Range  
		int rangeStart = 0;  
		int rangeEnd = collection.length -1;  
		int middleIndex = (rangeStart + rangeEnd) / 2;  
		  
		int middleValue = collection[middleIndex];  
		  
		// loop while search range is not empty  
		while(rangeStart <= rangeEnd) {  
			// success  
			if (middleValue == target) {  
				return middleIndex;  
			}  
			  
			// divide the search range in half  
			if (middleValue > target) {  
				rangeEnd = middleIndex -1;  
			} else {  
				rangeStart = middleIndex + 1;  
			}  
			  
			// get the new middleIndex and middleValue  
			middleIndex = (rangeStart + rangeEnd) / 2;  
			middleValue = collection[middleIndex];  
		}  
		  
		// value not found  
		return null;  
	}  
}
```