# C++ Rampup Lecture 1
### The Memory Model

Created by [Barry Steyn](basteyn@microsoft.com)

~~

# Pointer
## A pointer is really a 64 (or 32) bit integer that holds a memory address

 * The memory address does not have to point to anything real.
 * In fact, the memory address does not even have to exist.

~
# Pointer To Types
## A pointer in C++ (not C) also has type information:

It is declared by using *

```
int *p;
char *c;
SomeObject *someObject
```

~
# Pointer Intialization
## Always initialize pointers. Intialize to NULL if there is no intial value
NULL is a *reserved constant* for the value 0 (zero)

Setting something to null means it points to nothing

```
	int *p1 = NULL,
		*p2;
```
####In the above code snippet, what would `p2` hold?

~

# Pointer Intialization With New
## The new operator reserves memory on the **heap**
```
	int *p1 = NULL,
		*p2 = new int;
```
####Okay, what is in p2 now?

~
# Stack Vs Heap
##Stack is temporary memory used in specific contexts (i.e. functions)
##Heap is permanent (for the duration of your program) memory used in any context
Memory declared on the heap therefore needs to be manually deleted

~

# Removing Things From The Stack
## Use the delete operator

```
	int *p = new int;
	delete p;
```

~

# Memory Leaks
##If something is declared on the heap and you lose the reference to it, you get a memory leak

```
	void memoryLeak() {
		int *p = new int; //
	}

	for (int i=0; i < 1000; i++)
		memoryLeak();
```
Memory leaks are the most common memory mistake to make

~

# Dangling Pointers

```
	int *p = new int,
		*a = &p;

	delete p; // a is now pointing to something it shouldn't
```

~~

# C++'s Conciseness Makes It Confusing
## \* is used to declare a pointer, its also used to dereference it

```
	int *p1 = new int;
	*p1 = 3;

	cout << p1 <<" "<< *p1;
```

~

#Spot The Problem \# 1

```
	int *p;
	cout << *p;
```
~

#Spot The Problem \# 2

```
	int *p = new int; 
	cout << p;
```

~~

# Reference
## A reference is an entity that is an alias for another variable
C++ uses & as the reference operator

```
	int a = 100;
	int &b = a;
```

~

# C++'s Conciseness Makes It Confusing
## The & operator can also be used to *get* a memory location

```
	int a = 100;
	int *p = &a; // 
```

~

#Spot The Problem \# 3

```
	int a = 100;
	int *p = a;
```

~~

# Pass By Reference Vs Pass By Value

 * Modern languages pass complex types *by reference*
 * C++ bucks this trend and everything is passed by value.

~

# Pass By Reference
## Instead of a complex type being copied, a reference to it is passed

 * Its efficient
 * Changes persist <- Watch out for side-effects
<br><br>
###This is what you want most of the time

~
# Example - pass by value

```
class Test {
	int longArray[1000000]; //who cares about initialization :)
}

----

void func1(Test t) {
	//Do nothing
}

Test testVar
func1(tetsVar);

```

~

# Example - pass by reference
## Pointers And References Allow Pass By Reference

```
class Test {
	int longArray[1000000]; //who cares about initialization :)
}

----

void func1(Test &t) {
	//Do nothing
}

Test testVar
func1(tetsVar);

```

~~

# Const
##The const reserved word makes a variable as a constant:

```
const int a = 100; //a cannot change
```

~

# C++'s Conciseness Makes It Confusing

```
void test(int * p);
void test(const int *p);
void test(int * const p);
void test(const int * const p);

```

Much easier for references:
```
void test(const int &r);

```

~~
#RAII Pattern
##RAII = Resource Acquisition Is Initilization
This is just fancy talk for meaning for the following:
  1. Make pointers class variables
  2. Intialize them on the heap in the constructor
  3. Remove them in the destructor

~
# RAII Example

```
class Test {
	int *p;

	public:
		Test() {
			p = new int;
		}

		~Test() {
			delete p;
		}
}
```

~~

#Smart Pointers


~~

#The End
By Barry Steyn
