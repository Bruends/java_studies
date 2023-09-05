# Streams

- Process sequences of data like Arrays, Collections..etc
- Streams are **immutable** and return a new sequence of data instead of modifying  the source
- **Middle Functions**: functions that return another stream and can be chained
	- ex: map, sorted, filter
- **Terminal Functions**: end the chain of operations and may return a final value
	- ex: toList, collect, count, forEach

##  example

```java
public class Main {  
	public static void main(String[] args) {  
		List<Integer> values = Arrays.asList(1, 3, 15, 2, 4, 56, 6);  
		
		// Start a Stream 
		Stream<Integer> streamInt = values.stream();  
		  
		List<Integer> intList = streamInt  
			// chain of middle functions  
			.filter(n -> n > 4)  
			.map(n -> n + 1)  
			.sorted()  
			// terminate a stream and return a list  
			.toList();  
			  
		System.out.println(intList); // [7, 16, 57]
	}  
}
```