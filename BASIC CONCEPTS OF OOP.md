Return to [[1.TABLE OF CONTENTS]]

- Objects
- Classes
- Data abstraction and encapsulation
- Inheritance
- Polymorphism
- Dynamic Binding
- Message passing



- OBJECTS
An object is a basic runtime entity in an object oriented system. They may represent a person, a place, a bank account, a table of data or any item that a program has to handle.
They may also represent user defined data. 


- CLASSES
A class is a collection of objects of similar datatype. The entire set of data and code of an object can be made user defined data type with the help of a class.


- DATA ABSTRACTION AND ENCAPSULATION
    - The wrapping up of data and functions into a single unit called class is called **encapsulation**.
	    Data is not accessible to the outside world and those functions which are wrapped in the class can access it. The function provides the interface between the object's data and the program.
    - The insulation of data from direct access by the program is called as data hiding or information hiding
    - Abstraction refers to the act of representing essential features without including the background details and explanations. Classes use the concept of abstraction and are defined as list of abstract attributes such as size, weight and cost , and functions to operate on these attributes.
    - The attributes are sometimes called as data members because they hold information. The functios that operate on them are called as methods or functions.



- INHERITANCE
	Inheritance is the process by which objects of one class acquire the properties of objects of another class.
	It supports the concept of heirarchical classification.
	- In OOP, polymorphism provides the concept of reusability. That means we can add additional features to an existing class without modifying it. This is possible by deriving a class from the base class.
	- The new class will have the combined features of both the classes.
	- Note that , each subclass defines only those unique features which are unique to it. Without the use of classification we would have to explicitly include all of its features.


- POLYMORPHISM
	Polymorphism is another OOP concept, meaning the ability to take more than one form.
	- Polymorphism plays an important role in allowing objects having different internal structure to have same external interface. 
	- Polymorphism is widely used in implementing inheritance. 

- DYNAMIC BINDING
	- Binding refers to the linking of a procedure call to the code to be executed in response to the call .
	- Dynamic binding ( also known as late binding ) means that the code associated with a given procedure call is not known until the call at run time.
	- It is associated with polymorphism and inheritance . A function call associated with a polymorphic reference depends on the dynamic type of that reference .

- NAMESPACE 
    -   Namespace provide the space where we can define or declare identifier i.e. variable,  method, classes.
    -   Using namespace, you can define the space or context in which identifiers are defined i.e. variable, method, classes. In essence, a namespace defines a scope.

ADVANTAGES OF USING NAMESPACE :
Namespaces are used to organize code into logical groups and to prevent name collisions that can occur especially when the code base includes multiple libraries.

