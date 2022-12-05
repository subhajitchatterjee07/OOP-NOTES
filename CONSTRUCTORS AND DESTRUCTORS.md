Return to [[1.TABLE OF CONTENTS]]

A constructor is a special member function whose task is to initialize the object of its class.

The special characteristics of the constructor functions are:
- They should always be declared in the public section.
- They are invoked automatically when the objects are created.
- They do not have return values,not even void and therefore , they cannot return values.
- They cannot  be inherited, although a derived class can call the base class constructor.
- Like other C++ functions, they can have default arguments.
- Constructors cannot be ***virtual***.
- We cannot refer to their addresses.
- An object with a constructor or destructor cannot be used as a member of a union.
- They make implicit calls to operators 'new' and 'delete' when memory allocation is required.


***LIMITATIONS OF CONSTRUCTORS***
- constructors do not have any return type.
- Constructors can neither be inherited nor can be virtual.
- Constructors can be declared in public scope only.
- Constructor's memory address cannot be fetched.



They are of 3 types of constructors:
- [[Default Constructors]]
- [[Parametrized Constructor]]
- [[Copy Constructors]]

  
  ***MULTIPLE CONSTRUCTORS IN A CLASS: ( OPERATOR OVERLOADING )***
C++ allows multiple constructors within a class to exist provided no ambiguity is present.
Example:
class integer:
{
	int m,n;
	public:
		integer( ) { m=0; n=0}
		integer( int a, int b)
		{
			m=a;  n=b;
		}
		integer (integer &i)
		{
			m=i.m; n=i.n ;
		}
}


***CONSTRUCTORS WITH DEFAULT ARGUMENTS
It is possible to define constructors with default arguments.***
- It is imposrtant to distinguish between the default constructor A : : A() and default argument constructor A : : A ( int = 0 )
- When both these forms are used to in a class , it causes ambiguity and hence error.
- Example- If we use OB A; compiler can't understand if OB::A() or OB::A(int=0) is being called.


***DYNAMIC INITIALIZATION OF OBJECTS
It is possible to assign class objects dynamically, that is, the initial value of an object may be provided during runtime.One advantage of dynamic initialization is that we can provide class various initialization formats using overloaded conbstructors.***



***DYNAMIC CONSTRUCTORS***
*Constructors can also be used to allocate memory while creating objects. This will enable to allocate right amount of memory for each object when objects are not of same size.,thus saving memory.
Memory is allocated with the help of **new** operator.*


***CONSTRUCTING 2 DIMENSIONAL ARRAYS***


***const OBJECTS ***

We may create and use constant objects using const keyword before object declaration.For example :   const matrix X (m,n);

***DESTRUCTORS***
As the name implies, a destructor is used to destroy the objects that have been created by a constructor.
A destructor is a special member function that has same name as the class name as that of the class but with a tilde ~ mark before it.
- A destructor never takes any value nor does it return any value.
- It will be invoked implicitly by the compiler upon exit from the program(or block or function) to clean up storage that is no longer accessible.
- We use **delete** to free the memory.
- The primary use of destructors is to free up the memory reserved by the object before it is destroyed.
NOTE :
A class constructor is called everytime an object is created . Similarly, as the program control leaves the current block , the objects start getting destroyed in the reverse order of their creation. Finally , when the main block is exited, the destructors are called corresponding to the remaining objects inside the main.