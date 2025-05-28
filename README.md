# javaNotes
# JAVA Notes

**CHAPTER 2:A Trip to Objectville**

**Overview: We will see how ot create objects and classes OO principles.**

WHY OO IS PREFERED.

When creating programs we want to maintain reduce redudancy. Example a program that has shapes and needs to make the shapes rotate can be made easier using classes and methods. We can have classes for each shape and for the main class that works on the functionality. The shapes will inherit the methods inside our superclass that manages the shape movements.

---

DESIGNING A CLASS

When designing a class, think about the objects that will be created from that class type. Think about:

- Things the object KNOWS
- Things the object DOES

Example;

| ShoppingCart |  |
| --- | --- |
| **`cartContents`** | **KNOWS** |
| `addToCart()   removeFromCart() checkOut()`                                      | DOES |

Things an object knows about itself are called ***instance variables***

Things an object can do are called ***methods***

**Exercise: (pg 34)**

| Television |
| --- |
| brand  powerState        pixelCount |
| setPower()         setChannel()       playSound()       |

### What is the difference between a class and an object?

A `*class`* is a ***blueprint*** for an object.

This can be anologised this way : A contact list contains many contacts, each contact in the list have the same identification basis like name, phone number, email, photo and etc. The actual contacts like Timothy, 0741481434, [timothywilliams.003@icloud.com](mailto:timothywilliams.003@icloud.com) and my photo make up a contact or an `object` ***.*** Therefore the paremeters of identity are the blueprint for creating a contact (object). these identifications are called the *instance state*  while the actions like getName(), setName(), changeName() are the *methods* for these contacts  or an object

### Making your first object

To create and use an object, we need 2 classes. 

class 1: type of object you want to use eg Bungee 

class 2: a class to test if the object (class) works eg bungeeTestDrive

### Step 1: Write your class.

```java
class Dog {
//instance variables(knows)
	int size;
	String breed;
	String name;
	
	void bark() {
	//methods(does)
		System.out.println("Ruff! Ruff!");
	}
}
```

### Step 2: Write a tester class.

```java
class DogTestDrive{
	public static void main (String[] args) {
		// Dog test code goes here
	}
}
```

### Step 3: In your tester , make an object and access the object’s variables and methods.

```java
class DogTestDrive {
	public static void main (String[] args) {
		Dog d = new Dog();
		d.size = 40;
		d.bark();
	}
}
```

| public | Everyone can use it | “Open to everyone” |
| --- | --- | --- |

| static | No object needed to use it | “Use it directly!” |
| --- | --- | --- |

| void | Doesn’t return anything | “I’ll do something but give nothing back”  |
| --- | --- | --- |

### Explanation of Step 3;

The test class willl be in the same file with the actual class ( Dog).

	`Dog d = new Dog();`

In the above snippet;

Dog = name of the class we want to access

d = name of our dog

new Dog() = creates a new dog ( new is a JAVA keyword)

---

Exercise (pg 37)

object 1 : title = Gone with the Stock

          genre = Tragic

    rating = -2

object 2 : title = Lost in cubicle space

          genre = Comedy

    rating = 5

object 3 : title = Byte club

          genre = Tragic but ultimately uplifting

    rating = 127

---

**objects should talk to each other**

Two uses of `main` :

- to *test* your real class
- to *launch/start*  your java application

---

Bullet Points

- Object-oriented programming lets you extend a program without having to touch previously tested code.
- All Java code is defined in a ***class.***
- A class decribes how to make an object of that class type making a class a ***blueprint of an object.***
- An object ***knows*** things and ***does*** things
- What an object knows are called ***instance variables***
- What an object does are known as ***methods***
- When creating a class we create a separate class with `main()` that will create objects from the class *blueprint (class type).*
- A class can ***inherit***  instance variables and methods from a ***superclass***

---

exercise: Be the Compiler

CODE A:

```java
class StreamingSong {
	String title;
	String artist;
	int duration;
	
	void play() {
		System.out.println("Playing song");
		
	void printDetails() {
		System.out.println("This is " + title + " by " + artist);
	}
}

class StreamingSongTestDrive {
	public static void main (String[] args) {
		StreamingSong song = new StreamingSong();// this was the missing piece,  we were supposed to create an objectfor the code to run
		song.artist = "The Beatles";
		song.title = "Come Together";
		song.play();
		song.printDetails();
	}
}
```

Output:

| Terminal |
| --- |
| $ Playing song                                            $ This is Come Together by The beatles |

CODE B:

Output:

| Terminal |
| --- |
| $ Skipping intro…                                            $  |

Exercise : CODE MAGNETS

```java
class DrumKit {
	boolean topHat = true;
	boolean snare = true;

	void playTopHat() {
		System.out.println("ding ding da-ding");
	}
	void playSnare() {
		System.out.println("bang bbang ba-bang");
	}
}

class DrumKitTestDrive {
	public static void main (String [] args) {
		DrumKit d = new DrumKit();

		if (d.snare == true) {
		d.playSnare();
		}

		d.playTopHat();
	}
}
```

POOL PUZZLE 

```java
class Echo {
	//instance variable
	int count = 0;
	// Methods 
	void hello(){
		System.out.println("helloooo..");
	}
}

//
public class EchoTestDrive {
	public static void main (String[] args ) {
		Echo e1 = new Echo(); //create new object
		Echo e2 = new Echo();
		int x = 0;
		while (x < 4) {
			e1.hello();
			e1.count = e1.count + 1;
			
			if ( x == 4) {
				e2.count = e2.count + 1;
			}
			if ( x < 4) {
				e2.count = e2.count + e1.count;
			}
		x = x + 1;
		}
	System.out.println(e2.count);
	}
}

```

WHO AM I?

I am compiled from a **.java** file - class

My instance variable values can be different from my buddy’s values - object

I behave like a template - class 

I like to do stuff - method, object

I can have many methods - class , objects

i represent “state” - instance variables

i have behaviours - class, objects 

I am am located in objects - methods, instance variables

I live on the heap - objects

I am used to create object instances - class

My state can change - objects, instance variable

I declare methods - class

i can change at runtime - object, instance variable

## Chapter 3 : Know Your Variables

**Declaring variables**

We have 2 ways of declaring variables:

- *primitive* ( they hold simple bit patterns eg integers, booleans and etc )
- *object reference* ( they hold *references* to objects )

1. ***Primitive Variables***

Example of format ;

---

# `int count;`

---

NB : `int` = type, `count` = name of variable

**Categories of numeric variables :**

| `int` | `floating point` |
| --- | --- |
| byte (8 bit) | float (32 bits) |
| short (16 bits) | double (64 bits) |
| int (32 bits) |  |
| long (64 bits) |  |

Examples : 

`int x;
x = 234;
byte b = 89;
boolean isFun = true;
double d = 3456.98;
char c = ‘f’;
int z = x;
boolean isPunkRock;
isPunkRock = false;
boolean powerOn;
powerOn = isFun;
long big = 3456789L;
float f = 32.5f;`

A mnemonic to remember primitive data types:

**B**e **C**areful **B**ears **S**houldnt **I**ngest **L**arge **F**urry **D**ogs

Boolean Char Byte Short Int Long Float Double

Example in a piece of code: 

```java
public class primitiveTypes {
	public static void main ( String[] args){
		// showing all datatypes namely boolean, char, byte, short, int, long, float, double.
		boolean noFood = true;
		char firstAlphabet = 'A';
		byte boxes = 13;
		short dataBalance = 1024;
		int population = 45000000;
		long noOfCells = 1000000000;
		float pie = 3.14267f;
		double K = 1000.638712981;
		// display all this values
		System.out.println( "Is there food " + noFood );
		System.out.println( "The first alphabet " + firstAlphabet);
		System.out.println( "Number of boxes " + boxes );
		System.out.println( "Data balance? " + dataBalance);
		System.out.println( "Kenya's population " + population);
		System.out.println("Number of cells : " + noOfCells);
		System.out.println("Value of pie : " + pie);
		System.out.println("Value of constant K = " + K);
	}
}
```

---

***b. Object References***

**THE 3 STEPS OF OBJECT DECLARATION, CREATION AND ASSIGNMENT :**

**Step 1: Declare a reference**

`Dog myDog = new Dog();` 

`Dog myDog` ~ This creates a new object reference called `myDog` . The reference variable is, forever, of type `Dog` . This is also the object name.

**Step 2: Create an object**

`Dog myDog = new Dog();`

`new Dog();`  ~ The JVM is told to create a new object space in the ***heap*** to store the object.

**Step 3: LInk the object and the variable**

`Dog myDog =new Dog();` 

`=` ~ it assigns the new `Dog()` to the reference variable `myDog` 

***Life On The Garbage-collectible Heap.***

How this works:

`Book b = new Book();`

`Book d = new Book();`

Above we create two reference variables `b` and `d`  and the two new object `b` and `d`  are stored in the heap.
