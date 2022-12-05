Return to [[1.TABLE OF CONTENTS]]

C++ strongly supports the concept of reusability . The C++ classes can be reused in several ways . Once a class that has already been written and tested , it can be adapted by other programmers to suit the requirements.
This is basically done by creating new classes , reusing the properties of the existing old classes 

**This mechanism of deriving a new class from an existing one is called inheritance .**
The old class is called as the base class and the new one is called as derived class or subclass.


## Types of inheritance

- Single inheritance - 
	![](singleinheritance.jpg)

A derived class with only one base is called as single inheritance .

- Multiple inheritance- 
	![](multipleinheritance.jpg)

A derived class with more than one base class is called as a multiple inheritance.


- Hierarchical Inheritance - 
	![](hierarchicalinheritance.jpg)
	When traits of one class are inherited by more than one classes , then the process is called as hierarchical inheritance.

- Multilevel inheritance : 
	![](multilevelinheritance.jpg)
	The mechanism of deriving a class from another derived class is 'multilevel inheritance'.


- Hybrid / Diamond inheritance problem- 
	all types of inheritance....


When a base class is privtely inherited by a derived class , 'public' members of the base class appear as private members of the derived class.They are inaccessible to the objects of the derived class.
- Remember, a public member of a class can be accessed by its own objects using the dot operator.The result is that no member of the base class is accessible to the base class.

On the other hand, if the class is publicly inherited, 'public members' of the base class become public members of the derived class.

Suppose a derived class define a function of the same name. What will happen when a derived class object invokes the function ?  In such cases, the derived class function supersedes the base class definition. However, if the derived class function does not redefine the function, then the base class function will be called. 

## MAKING A PRIVATE MEMBER INHERITABLE

What do we do if private data needs to be accessed by a derived class ?
C++ provides a visibility modifier , **protected** , which serve a limited purpose in inheritance.
- A member declared as protected is accessible by the member functions within its class and any class can be immediately derived from it. It cannot be accessed by the functions outside the 2 classes.
- When a protected member is inherited in public mode, it becomes protected in the derived class too and therefore is accessible by the derived class . It is also ready for the further inheritance. A member declared as protected , inherited in private mode becomes private in derived class , it is available for further inheritance. Since private members cannot be inherited.



## AMBIGUITY RESOLUTION IN INHERITANCE

Occasionally, we may face a problem in using the multiple inheritance, when a function using the same name appears in more than one base class. 
Ex- let there be **display()** function inherited by two classes .
We can solve this problem by using the class resolution operator with the function.


## VIRTUAL BASE CLASSES
Consider a situation where all the 3 kinds of inheritance , namely multilevel, multiple and hierarchical inheritance are involved .
![](diamondinheritance.png)


The child (class c) has 2 direct 'base classes' class1 and class2 ,which themselves have a common base class 'superclass' The child inherits the traits of the grandparent via two separate paths . The grandparent is sometimes referred to as the indirect base class.

- However this may pose some problems as the public and protected members of the grandparent are inherited twice via parent1 and parent2 . 

The duplication of inherited members due to these multiple paths will lead to ambiguity.

The duplication of inherited members due to these multiple paths can be avoided by making the common base class (ancestor class) as virtual base class. 

- When a class is made a virtual base class , C++ makes sure to see that only one copy of that copy of that class is inherited , regardless of how many inheritance paths exist between the virtual class and a derived class. 


## ABSTRACT CLASSES

An abstract class is one that is not used to create objects. An abstract class is designed only to act as a base class (to be inheried by other classes).It is a design concept in program development and provides a base upon which other classes may be built may be built.

- However one must never forget the fact that that by definition, a class can be considered as an abstract class if it has at least one pure virtual function.  


## CONSTRUCTORS IN DERIVED CLASSES 

- One important important thing to note that as long as no base class constructors takes any argu,ments , the derived class does not take any constructor function.
- However, if any base class contains a constructor with one or more arguments, then it is mandatory for the derived class to have a constructor and pass the arguments to the base class constructors.
- When both derived and base class have constructors then the base constructor is executed first and then the derived class constructor is executed.
- In case of multiple inheritance, , the base classes are constructed *in the order* in which they appear in the declaration of the derived class.Similarly, in a multilevel inheritance the base constructor is executed first and then the constructor in the derived class is executed.


pg 210 important........


- C++ supports another method of initialising the class objects. This method uses what is known as initialisation list in the constructor function. This takes the following form :

	constructor (arglist) : initialization-section
	{
		assignment-section
	}

Ex- 
class xyz
{
	int a;
	int b;
	public :
		xyz(int i,int j) : a(i),b(2*j)
}
