Return to [[1.TABLE OF CONTENTS]]

C++ permits us to add two variables of user defined types with the same syntax that is applied to the basic types. This means that C++ has the ability to provide the operators with a special meaning for a data type . This mechanism of giving such special meanings to an operator is called as operator overloading.


Operator overloading provides a flexible option for the creation for the creation of new definitions for the most of the C++ operators.

We can overload all the C++ operators **except** : 
- class member access operators( dot, star ) 
- sizeof operator
- scope resolution operators( : : )
- conditional / ternary operator (? :)
The reason we cannot overload these operators may be attributed to the fact that these operators take names(example class name) as their operand instead of their values, as is the case with other normal operators.

***NOTE :***
Although the  semantics of an operator can be extende , but its syntax , the grammatical rules that govern the use such as number of operands ,precedence and associativity cannot be changed.

- When an operator is overloaded ,its original meaning is is not lost. 
Example : 
The operator + which has been overloaded to add 2 vectors, can also be used to add two integers.




DEFINING OPERATOR OVERLOADING
To define an additional task to an operator , we must specify what it means in relation to the class to which the operator is applied . This is done with the help of a special function called operator function, which describbes the task.

The general form of the operator function is : 

return type classname : : operator op(arglist)
{
	function body // task defined 
}
where return type is the type of value returned by specified operation and op is the operator being overloaded.

- Operator functions are either member functions( nonstatic ) or friend functions .
- A basic difference between them is that a fried function has only one argument for unary operators and 2 for binary operators *But in case of member functions there are 0 parameters for unary operators and 1 for binary operators.*

REASON- 
**This is because the object used to invoke the member function is passed implicitly and therefore available by the member function.
**However this is not the case with friend function . Arguments may be passed either by value or by reference. Operator functions are defined in calss prototypes as follows :
- vector operator+(vector);
- vector operator- ();
- friend vector operator + ();
- vector oerator + (vector & a);

int operator == ( vector );



vector is a datatype of the class and may represent magnitude and direction.





The process of overloading involves the following steps:
1. Create a class that defines the datatype that is to be used in the overloading operation.
2. Declare the operator function **operator op( )** in the public part of the class. It may be a friend function or a member function.
3. Define the operator function to implement the required operations.


# EXAMPLE OF UNARY OPERATOR OVERLOADING
void space : : operator- ()
{
	x=-x;
	y=-y;
	z=-z;
}

1. ***Remember, A statement "-S" will work but "S2=-S1" will not because the function operator does not return any value; It can work if the function is modified to return a value.
2. ***Also remember that in friend functions it is preferable to pass arguments by references ....because  on passing the arguments by value ,because only a copy of the object is passed. Therefore the changes made by the operator is not reflected by the called object.***
3. ***NOTE : the argument is passed by reference . It will not work if pass by argument because only a copy of the object is passed to Operator.nTherefore the changes made in the operator function will not be changed inside the called object.***

## OVERLOADING BINARY OPERTORS
It is similar to the unary operator.
The same mechanism can be used to overload a binary operator.

Example: 


However the following features are to be noted :
- It receives only one 'complex' type argument explicitly.
- It returns as 'complex' type value.
- It is a member function of 'complex'.

usual call is like C3=C1.operator+C2;

## MANIPULATION OF STRINGS USING OPERATORS

C implements strings using character arrays, pointers and string functions.There are no operators for manipulating strings . One of the main drawbacks of string manipulation in C is that the programmer must determine its length and allocate the required memory size.

In C++ , strings can be defined as class objects which can then be manipulated.
Strings can be defined as class objects which can be then manipulated like the built in types.
Since the strings vary greatly in size , we use new to allocate memory for each string and a pointer variable to point to the string array.

## OVERLOADING THE SUBSCRIPT OPERATOR[]
The subscript operator is used to access and modify a specific element in an array.

## OVERLOADING THE POINTER TO MEMBER ARRAY
The pointer-to-member operator is normally used in conjuction with an object pointer to access any of the objects members .
In a program both the normal and overloaded behaviour -> works fine



# RULES FOR OVERLOADING OPERATORS 


- Only existing operators can be overloaded. New operators cannot be created.
- The overloaded operator must have at least one one operand that is of user defined type.
- Overloaded operators follow the syntax rules of original operators. They cannot be overwritten.
- There are some operators which cannot be overloaded.
- We cannot use friend functions to overload certain operators .However, member functions can be used to overoad them.
- Unary operators, overloaded by means of a member function, take no explicit arguments and return no explicit values but those overloaded by means of a friend function, take one reference argument (the object of the relevant class).
- Binary operators overloaded through a member function take on explicit argument and those which are overloaded through a friend function take two explicit arguments.
- When using binary operators through a member function, the left hand operand must be an object of the relevant class.
- Binary arithmeticoperators such as + , - , * ,and /must explicitly return a value.They must not attempt to change their own argumnts.




# TYPE CONVERSIONS


We know that C applies automatic type conversions to the operands as per certain rules .
Similarly, an assignment operation also causes the automatic type conversion. The type of data on the right is automatically converted to that of the left.

In C++ this also works for user defined datatypes.
What if one object is a an object and other is a built in datatype variabe/object of another class?

Since the user defined datatypes are adesigned by us to suit our requirements, the compiler does not support automatic type conversions for such data types.
We must ,therefore , design the conversion routines by ourselves , if such operations are required.

Three types of situations might arise in the data conversion between uncompatible types:
1. Conversion from basic type to class type 
2. Conversion from class type to basic type
3. Conversion of one class type to another class type

## Basic to class type
Example : 
Conversion of basic type to class type is easy.It may be recalled that the use of constructors was illustrated to initialise objects.
Ex- A constructor can be used to build a vector object from an int type array.
  Or you can convert  a char* variable into string.
NOTE- The constructors used for type conversion take a single argument whose type is to be converted.

## Class to basic type
The constructor functions do not support this operation.
Luckily, c++ offres an overloaded casting operator which can be used to convert a class data type to a basic data type.
The function converts a class type data into *typename*.

The casting operator function should satisfy the following conditions :
- It must be a class member.
- It must not specify a return type.
- It must not have any arguments.
Since it is a member function, it is invoked by the object and therefore the values used for conversion inside the the function belong to the object that invoked the function . This means that the function does not need an argument.


## One class to another class type

let objx be an object of class X and objy be an object of class Y .The class Y type data is converted to class X type data and the converted value is assigned to the objX. Since the conversion takes place from class Y to class X , Y is known as the source class and X is known as the destination class.

Such conversions can be carried out by either a constructor or a conversion function.
Then how do we decide which one to use ? 
It depends upon where we want the type conversion function function to be located in the source class or in the destination class.

MOre DEtails LAter