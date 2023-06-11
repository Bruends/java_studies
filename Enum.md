## Enum
conjunto de constantes.
ex:  

```java
// Seasons.java
public enum Seasons {  
	//obs: por convensão escrevemos os valores em "capslock"
	FALL,  
	WINTER,  
	SPRING,  
	SUMMER;  
}

// Main.java
public class Main {  
	public static void main(String[] args) {  
		Seasons season =  Seasons.FALL;  
		  
		System.out.println(season); //FALL 
	}  
}


```

enums podem ter atributos.
ex:

```java
// podemos incluir o mês inicial de cada estação.
public enum Seasons {  
	FALL("March"),  
	WINTER("June"),  
	SPRING("September"),  
	SUMMER("December");  

	// por convenção os atributos dos enums devem ser imútaveis
	final String startingMonth;  
	  
	Seasons(String startingMonth){  
		this.startingMonth = startingMonth;  
	}  
  
}

// Main.java
public class Main {  
	public static void main(String[] args) {  
		Seasons season =  Seasons.FALL;  
		  
		System.out.println(season.FALL.startingMonth); //March 
	}  
}
