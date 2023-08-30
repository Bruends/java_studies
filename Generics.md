# Generics

- Allows a class/method to be more flexible and work with more than one type.
-  doesn't work with primitive types ( int, char, etc... ).
	-  but works with the Object counterparts ( Integer, Character, etc... ).
-  Supports inheritance and interfaces.

#### Generics in Classes:
```java
// Printer.java
// the 'T' is a Convention and can be anything
public class Printer <T>{  
	T toPrint; 
	  
	public (T toPrint) {  
		this.toPrint = toPrint;  
	}
}

// Main.java
public class Main {  
	public static void main(String[] args) {  
		Printer<String> printer = new Printer<>("Attribute");
	}
} 

```

#### Inheritance & Interfaces
```java
// generics also suports inheritance and interfaces 
// for interfaces also use the keyword 'extends'
public class GenericsExample <T extends MotherClass>{  
	T genericAttribute;  
	  
	public GenericsExample(T genericAttribute) {  
		this.genericAttribute = genericAttribute;  
	}
}

// main.java
public class Main {  
	public static void main(String[] args) {   
		Type obj = new Type();
		GenericsExample<Type> ge = new GenericsExample<>(obj);  
	}
}  

// using inheritance and interfaces at the same time
// the extended class always come before the interface
public class GenericsExample <T extends MotherClass & Interface> 

```

#### Generics in methods
```java
public class ClassName
{
	public <T, V> V methodName(T attribute, V returnValue){
		System.out.println(attribute);
		return returnValue;
	}
}
```