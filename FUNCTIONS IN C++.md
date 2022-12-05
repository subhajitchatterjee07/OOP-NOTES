

[[1.TABLE OF CONTENTS]]


1. FUNCTION PROTOTYPING  (DECLARATION) :
	The prototype describes the function interface to the compiler by giving giving details such as the number and type of arguments and the type of return values.
***type function name (argument list)

2. CALL BY REFERENCE :
	When we pass arguments by reference the formal arguments in the function become aliases to the actual arguments in the calling function.

   Example-
	void swap(int &a,int &b)
	{
		int t=a;                                                                     //dynamic initialisation
		a=b;
		b=t;
	}
	the function can be called as follows: swap(&x , &y);

3. RETURN BY REFERENCE :
	A function can also return a reference..
	Example-
		int &max (int &x,int &y)
		{
			if(x>y)
			{
				return x;
			}
			else return y;
		}
	Since the return type of the function is int &, the function returns the reference to x or y;



4. INLINE FUNCTIONS :
	An inline function is a function that is expanded in line when it is invoked.That is, the compiler replaces the function call with the corresponding function code.
		Example-
			inline double cube(double a)
			{
				return a  (into)  a  (into)  a;
			}
		*Some of the places Where the inline function does not work are :
		 -> For functions returning values ,if a loop, a switch or a goto exists..
		 -> For functions not returning values, if a return statement exists ..
		 -> If function contains static variables..
		 -> If inline functions are recursive..*




	5.DEFAULT ARGUMENTS: 
			C++ allows a function to call a function without specifying all of its arguments. In such cases, the function assigns a default value to the parameter having no matching argument in the function call.
			*It is important to note that only trailing arguments have default values and therefore we can add 
			values from right to left.*
			->Advantages of default arguments :
			1. We can use default arguments to add new parameters to the existing functions .
			2. Default arguments can be used to combine similar functions into one.



	6. Const ARGUMENTS:
		In C++ an argument to a function can be declared as const 
		int strlen(const char *p)

		The const qualifier tells the computer the function should not modify the argument. The compiler will generate an error when the condition is violated..



	7. RECURSSION :

		A situation when the function calls itself.




	8. FUNCTION OVERLOADING :
		The means by which we can use the same function name to perform a variety of tasks is called as function polymorphism in OOP.
		- The function would perform different tasks depending on the argument list in the function call.
		- The correct function to be invoked is determined by checking the number of type of the arguments but not on the 
                 function type.


	Function overloading involves the following steps :
	1. The compiler first tries to find an exact match in which the types of actual arguments are the same, and use that function.
	2. If an exact match is not found, the compiler uses the integral promotions to the actual arguments, such as (char to int)... to find a match.
	3. When either of them fails, the compiler tries to use the built in conversions (the implicit assignment conversions) to the actual arguments and then uses the function whose match is unique.
	4. A function call such as square(10) is ambiguous because int argument can be converted to both double and long,thereby creating an error.


		USES:
		Overloaded functions are extensively used for handling class objects.
	
	
	9.***STATIC MEMBER OF A FUNCTION : ***
	Static data members are **class members that are declared using static keywords**. A static member has certain special characteristics. These are: Only one copy of that member is created for the entire class and is shared by all the objects of that class, no matter how many objects are created.
	

