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

# 

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

`Book b = new Book();`  object 1

`Book c = new Book();`  object 2

Above we create two reference variables `b` and `d`  and the two new object `b` and `d`  are stored in the heap.

---

`Book d = c;` 

This creates a new reference variable called  `d`  which can be able to control object `c` . its like i have created a new remote to control object `c` using reference variable (remote) `c` and `d` .The `new` keyword is supposed to create a new object when not in use no new object is created as in the case above.

---

`c = b;` 

This changes the object reference variable `c` controls. Previously, `c` controlled object 2 but now it controls #object 1 it’s assigned to reference variable `b` . Now  `c` never controls #object 2.

**Life and death on the heap***

**An Array is Like a Tray of Cups**

When we create an array its like creating an object that stores many values. Here’s how we create them:

`int[] num = new num[5];` 

this creates a reference variable called `num` which references to an array called `num` .

How to insert values inside the array above;

`num[0] = 6;` 

`num[1] = 19;`

`num[2] = 21;`

    :

`num[x] = xx;`

**Array are Objects**

We can still have array of objects as below:

`Dog[] pets = new Dog[6];` 

This declares a new Dog array which has a reference of `pets` that will be used to access each object in the array of objects. To assign new objects into this array we use this snippet:

`pets[0] = new Dog();`  #1

`pets[1] = new Dog();` 

This two parts create new objects that will be inside the array. **#1** will hold the first object in index position 1 in the array.

Exercise : Sharpen your Pencil (pg60)

1. null
2. `pets[3] = pet[1];` 

*How to control objects in an array.*

eg; create an array and try to access methods for each object in the variable.

`Dog[] pet = new Dog[5];`  creates an array of Dogs

`pet[0] = new Dog();`  creates a new object in index position 1.

Now we want to invoke a method for this new Dog. Lets give it a name; 

`pet[0].name = “Fido”;` creates a name Fido for new object by use of the name() method.

Basically we use the reference variable (name) `pet` in this case and the index position of the object `[0]` in order to access it then pass it to an instance variable  `.name` as shown above. For a method we have:

`pet[0].bark();`  makes the dogs in the first index position to bark. Thats calling a method in an array.

**NB: Rules of premitive data types are applied in this case eg you cant have an int inside a byte. there is *spillage* but one can have a byte inside an int since there is no spillage**

puzzle: Heap o’ Trouble

| Index | hq[index] Points to | id |
| --- | --- | --- |
| hq[0] | `null` | — |
| hq[1] | `HeapQuiz` object | 1 |
| hq[2] | `null` | — |
| hq[3] | `HeapQuiz` object | 2 |
| hq[4] | `HeapQuiz` object | 0 |

Five-Minute Mystery

```java
Contact [] contacts = new Contact[10];
while (x < 10 ) {
// make 10 contact objects
contacts[x] = new Contact();
x = x + 1;
}
// do complicated Contact list updating with contacts
```

The code above will work because He has created an array that stores each value in the array thus can be accessed thereafter.

```java
Contact contactRef;
while ( x < 10 ) {
// make 10 contact objects
contactRef = new Contact();
x = x + 1;
}
// do complicated Contact list updating with contactRef
```

The above code is not OK since when we create an object its stored in the contact but when we rerun the loop the old contact is lost since one reference variable is being used `contactRef` .
