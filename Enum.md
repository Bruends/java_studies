# Enum
- A Set of constants.
- For convention values are write in CAPSLOCK
- Can have constructor methods and attributes

```java
//Seasons.java
public enum Seasons {  
	FALL("March"),  
	WINTER("June"),  
	SPRING("September"),  
	SUMMER("December");  
	  
	final String startingMonth;  
	  
	Seasons(String startingMonth){  
		this.startingMonth = startingMonth;  
	}  
	  
	public void describe() {  
		System.out.println(this + " starts in: " + this.startingMonth);  
	}  
}

// Main.java
public class Main {  
	public static void main(String[] args) {  
		Seasons season = Seasons.WINTER;  
		season.describe(); // WINTER starts in: June  
	}  
}
