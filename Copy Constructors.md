Return to [[CONSTRUCTORS AND DESTRUCTORS]]

A constructor which copies the data from an initialized object is called as copy constructor.


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

Example :
integer (integer &i)
		{
			m=i.m; n=i.n ;
		}


**A reference variable has been used as an argument to the copy constructor. We cannot pass the argument to a copy constructor.



