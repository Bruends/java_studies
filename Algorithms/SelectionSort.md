# Selection Sort

### Code
```Java
public class SelectionSort {  
	public static void main(String[] args){  
		int[] arrayToSort = {1,8,6,23,11};  
		  
		sort(arrayToSort);  
		  
		for (int value : arrayToSort) {  
		System.out.println(value);  
		}  
	}  
	  
	public static void sort(int[] arrayToSort){  
		int arrayLength = arrayToSort.length;  
		  
		// run through the array  
		for (int i=0; i <= arrayLength -1; i++) {   
			int minIndex = i;  
			boolean foundMinimalValue = false;  
			  
			// search in the unsorted part of the array  
			// for the next minimal value  
			for (int j=i+1; j < arrayLength; j++) {  
				if (arrayToSort[minIndex] > arrayToSort[j]){  
					minIndex = j;  
					foundMinimalValue = true;  
				}  
			}  
		  
			if (foundMinimalValue) {  
				// swap the minimal value with the old one  
				int swapHelper = arrayToSort[minIndex];  
				arrayToSort[minIndex] = arrayToSort[i];  
				arrayToSort[i] = swapHelper;  
			} 
		} 
	}  
}
```