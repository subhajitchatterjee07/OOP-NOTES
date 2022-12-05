Return to [[1.TABLE OF CONTENTS]]



*LIMITATIONS OF C STRUCTURE*
1. the standard C does not allow the struct data type to be treated like built in types.
2. Structures in C do not permit data hiding. In other words, structure members are public data members.


***CLASSES***
- A class is a way to bind the data and its associated functions together. It allows the data (and functions) to be necessary ,from external use.
- A class is an abstract data type which can be treated like any other datatype..



Class specification has 2 parts:
	1. Class declaration
		Class declaration describes the type and scope of its members.
	2. Class function definition
		The class function definitions describe how the class is implemented.




***GENERAL FORM OF CLASS DECLARATION***
class class_name
{
	private:
		variable and/or function declarations;
	public:
		variable and/or function declarations;
}

The variables declared inside the class are known as data members and the functions are known as member functions.
*Only the Member functions can have access to the private data members and data functions.*



***Encapsulation***:
The binding of data and functions together in a single class type variable is called encapsulation.


- An object is an instance of a class.


***Making an outside function inline:***
We can define a member function outside a class and still make it inline by using the qualifier inline  in the header line of the function definition.
- Example :
		class item
		{
			...............................................
			...............................................
			public:
				void getdata(int a,int b);                                                                             ////declaration
		 };
		 inline void item :: getdata(int a,int b)                                                                       ////definition
		 {
			number=a;
			cost=b; 
		 }

***Nesting of member functions***
A member function of a class can be accessed /called only by an object of that class .
But there is an exception to this.Member function can be called by using the name inside another member function of the same class.
This is called as nesting of member functions .


***PRIVATE MEMBER FUNCTIONS***

- Generally, the data are kept private and functions are kept private.
- But some functions need to be kept in private.
- A private member function can only be called by another member function that is a member of the class.
- Even an object cannot invoke a private function that is a member of that class.



***MEMORY ALLOCATION FOR OBJECTS***
- Memory space for objects is allocated when they are declared and not when the class is specified.
- This statement is partly true;actually the member functions are created in the memory space only once when trhey are defined as a part of class specification.
- Since all the objects belonging to the same class use the same member functions, no separate space is allocated to member functions when an object is created.



***STATIC DATA MEMBERS***
The data member of a class can be qualified as static. The properties of a static member are similar to that of static C variable.
The special characteristics are :
- It is initialised to zero when the first object of the class is created.No other initialisation is permitted.
- Only the copy of that member is created for the entire class and is shared by objects of that class, no matter how many objects are created.
- It is visible within the class, but its lifetime is the entire program.

- Static variables are normally used to maintain values common to entire class .
- Ex-Static variable as a counter.



***STATIC MEMBER FUNCTIONS***
Like static member variable, we can also have static member functions. A member function that is declared static has the following properties :
- A static function can have access to only other static (functions or variables) declared in the class.
- A static member function can be called by using the class name(instead of its objects)
		class_name : : function-name;



**Array of Objects** classname obj_name[x];




***FRIEND FUNCTIONS***

We know that a nonmember function cannot have access to private data of a class from outside it.So friend functions are used to have access to private data of more than one class.
- Declaration is in class
- Definition outside the classes..

**A friend function possesses the following characteristics : **
- It is not in the scope of the class to which it has been declared as a friend.
- Since it is not in the scope of the class, it cannot be called using the object of the class.
- It can be invoked like a normal function without the help of any object.
- Unlike the member functions, it cannot access the member names directly and has to use an object name and dot membership operator with with each member name.
- It can be declared in the publiuc or private part of a class without affecting its meaning.
- Usually it has the objects as the arguments.

Example :
class sample
{
	int a;
	int b;
	public:
		void setvalue () {a=25,b=4};
		friend float mean (sample s);
}
float mean (sample s)
{
	return (s.a + s.b)/2;
}

in main()
mean(X)




***CONST MEMBER FUNCTIONS***
If a member function does not alter any data in a class, we may declare it as a const member function as follws:
example:
	void mul(int int) const;
- The qualifier const is appended to the function prototypes (in both declaration and definition) .The compiler will generate an error if such functions try to alter the data values.

***POINTER TO MEMBERS***
class A
{
	int m;
}
We can define a pointer to member m as follows : 
 int A : : *ip =&A : : m;




***LOCAL CLASSES***
It is also possible to define a class inside another class or function or block . Such a class is called local class.
