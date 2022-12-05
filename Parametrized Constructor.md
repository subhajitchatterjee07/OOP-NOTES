Return to [[CONSTRUCTORS AND DESTRUCTORS]]

The constructor that can take arguments is called as Parametrized Constructor.
When a constructor has been parametrized, the object declaration must have the necessary arguments.
- We must pass the initial values as arguments to the constructor function when an object is declared.
This can be done in 2 ways :
- By calling the constructor explicitly.
- By calling the constructor implicitly.


EXPLICIT CALL :
integer int1 = integer(0,100)

IMPLICIT CALL :
integer int1(0,100)

***NOTE:
- ***The parameters of a constructor can be of any type except that of the class to which it belongs to !!!
- ***However the constructor can accept a reference to its own class as its own parameter.***
Example :
class A
{
	public:
	A(A&);
}
In such cases the constructor is called the copy constructor .





