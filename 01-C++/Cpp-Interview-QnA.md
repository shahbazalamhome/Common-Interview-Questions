Basic C++ Level Interview Questions
1. What is C++?
C++ is a computer programming language that is a superset of C, with additional features. 

2. Does C++ make use of OOPS? 
Yes, it does. An Object-Oriented Programming System is a paradigm that includes concepts such as data binding, polymorphism, and inheritance, among others.

3. What is a Class?
A class is a user-defined data type that is at the center of OOP. It reflects different entities, attributes, and actions.

4. What is an object?
An object is an instance of the class. An object can have fields, methods, and constructors.

5. What is encapsulation?
Encapsulation is the process of binding together the data and functions in a class. It is applied to prevent direct access to the data for security reasons. The functions of a class are applied for this purpose.

6. What is abstraction?
An abstraction in C++ is hiding the internal implementations and displaying only the required details.

For example, when you send an important message through email, at that time, only writing and clicking the send option is used. This outcome is just the success message that is displayed to confirm that your email has been sent. However, the process followed in transferring the data through email is not displayed because it is of no use to you.

7. What is inheritance?
C++ allows classes to inherit some of the commonly used state and behavior from other classes. This process is known as inheritance.

8. What is the access specifier and what are the types?
An access specifier determines how the class members, i.e., functions and variables, will be accessed outside the class's scope. 



There are three types of access specifiers in C++:

Private: Such class members can’t be accessed outside the class in which they are declared and are only accessible within the same class. Even child classes are disabled to access private members of its parent class.
Protected: In addition to the class in which they are declared, the child classes can access its parent class's protected members.
Public: Class members declared as public can be accessed throughout the program.
9. What is a namespace?
 A namespace is used for resolving the name conflict of the identifier, which is accomplished by placing them under various namespaces.

10. What is a class template?
A class template is a name given to the generic class. The use of the keyword template is made for defining a class template.

11. What is the function of the keyword “Volatile”?
"Volatile" is a function that helps in declaring that the particular variable is volatile and thereby directs the compiler to change the variable externally- this way, the compiler optimization on the variable reference can be avoided.

12. What is a storage class?
A storage class in C++ specifically resembles the scope of symbols, including the variables, functions, etc. Some of the storage class names in C++ include mutable, auto, static, extern, register, etc.

13. What is an Inline Function? Is it possible to ignore inlining?
In order to reduce the function call overhead, C++ offers inline functions. As the name suggests, an inline function is expanded in line when it is called.

As soon as the inline function is called, the whole code of the same gets either inserted or substituted at the particular point of the inline function call. The substitution is completed by the C++ compiler at compile time. Small inline functions might increase program efficiency.

The syntax of a typical inline function is:

Inline return-type function-name(parameters)
{
// Function code goes here
}
As the inlining is a request, not a command, the compiler can ignore it.

14. Can we have a recursive inline function in C++?
Even though it is possible to call an inline function from within itself in C++, the compiler may not generate the inline code. This is so because the compiler won’t determine the depth of the recursion at the compile time.

Nonetheless, a compiler with a good optimizer is able to inline recursive calls until some depth is fixed at compile time and insert non-recursive calls at compile time for the cases when the actual depth exceeds run time.

15. What is the ‘this’ pointer?
The ‘this’ pointer is a constant pointer, and it holds the memory address of the current object. It passes as a hidden argument to all the nonstatic member function calls. It is available as a local variable within the body of all the nonstatic functions.

As static member functions can be called even without any object, i.e., with the class name, the ‘this’ pointer is not available for them.

16. What are the most important differences between C and C++?
C++ supports references while C doesn’t.
Features like friend functions, function overloading, inheritance, templates, and virtual functions are inherent to C++. These are not available in the C programming language.
In C, exception handling is taken care of in the traditional if-else style. On the other hand, C++ offers support for exception handling at the language level.
Mainly used input and output in C are scanf() and printf(), respectively. In C++, cin is the standard input stream while cout serves as the standard output stream.
While C is a procedural programming language, C++ provides support for both procedural and object-oriented programming approaches.
17. Why do we need the Friend class and function?
Sometimes, there is a need for allowing a particular class to access private or protected members of a class. The solution is a friend class, which can access the protected and private members of the class in which it is declared as a friend.

Similar to the friend class, a friend function is able to access private and protected class members. A friend function can either be a global function or a method of some class.

Some important points about friend class and friend function:

Friendship is not inherited.
Friendship isn’t mutual, i.e., if some class called riend is a friend of some other class called NotAFriend, then it doesn’t automatically become a friend of the Friend class.
The total number of friend classes and friend functions should be limited in a program as the overabundance of the same might lead to a depreciation of the concept of encapsulation of separate classes, which is an inherent and desirable quality of object-oriented programming.
18. What is Operator Overloading?
Operating overloading is when operators have different implementations depending on the arguments passed. It is a type of polymorphism.

19. What is Polymorphism?


Polymorphism is the ability of a variable, function, or object to take on multiple forms. 

Intermediate Level Interview Questions
20. Explain vTable and vptr.
vTable is a table containing function pointers. Every class has a vTable. vptr is a pointer to vTable. Each object has a vptr. In order to maintain and use vptr and vTable, the C++ compiler adds additional code at two places:

In every constructor – This code sets vptr:
Of the object being created
To point to vTable of the class
Code with the polymorphic functional call – At every location where a polymorphic call is made, the compiler inserts code in order to first look for vptr using the base class pointer or reference. The vTable of a derived class can be accessed once the vptr is successfully fetched. The address of the derived class function show() is accessed and called using the vTable.
21. How is function overloading different from operator overloading?
Function overloading allows two or more functions with different types and number of parameters to have the same name. On the other hand, operator overloading allows for redefining the way an operator works for user-defined types.

22. Is it possible for a C++ program to be compiled without the main() function?
Yes, it is possible. However, as the main() function is essential for the execution of the program, the program will stop after compiling and will not execute.

23. What is a destructor?
A destructor is the member function of the class. It has the same name as the class name and is also prefixed with a tilde symbol. It can be executed automatically whenever an object loses its scope. A destructor cannot be overloaded, and it has the only form without the parameters.

24. What is the default constructor?
The compiler provides a constructor to every class in case the provider does not offer the same. This is when the programmer provides the constructor with no specific parameters - this is called a default constructor. The code for default constructor can be displayed in the following example.

// Cpp program to illustrate the
// concept of Constructors
#include <iostream>
using namespace std;
class construct {
public:
int a, b;
// Default Constructor
construct()
{
a = 10;
b = 20;
}
};
int main()
{
// Default constructor called automatically
// when the object is created
construct c;
cout << "a: " << c.a << endl
<< "b: " << c.b;
return 1;
} 
25. Can we provide one default constructor for our class?
No, we cannot provide one default constructor for our class. When a variable in the class type is set to null, it means that it was never initialized and the outcomes will be zero.

26. What is the main difference between the keyword struct and class?
The keyword struct is used for resembling public members by default, while the keyword class is used for resembling private members by default.

27. What is the output of the following program?
#include
usingnamespacestd;
intmain()
{
int numbers[5], sum = 0;
cout << "Enter 5 numbers: ";
for (int i = 0; i < 5; ++i)
 {
cin >> numbers[i];
 sum += numbers[i];
 }
cout << "Sum = " << sum << endl;
return0;
}
The program will ask the user to enter 5 numbers and then present with their sum. For instance,

Enter 5 numbers: 22

25

32

46

66

Sum = 191

28. Explain Virtual Functions and Runtime Polymorphism in C++ with an example.
Any function when accompanying the virtual keyword exhibits the behavior of a virtual function. Unlike normal functions that are called in accordance with the type of pointer or reference used, virtual functions are called as per the type of the object pointed or referred.

In simple terms, virtual functions resolve at runtime, not anytime sooner. Use of virtual functions could also be understood as writing a C++ program leveraging the concept of runtime polymorphism. Things essential to writing a virtual function in C++ are:

A base class
A derived class
A function with the same name in both the classes i.e. the base class and the derived class
A pointer or reference of base class type that points or refers, respectively to an object of the derived class
An example demonstrating the use of virtual functions (or runtime polymorphism at play) is:

#include
usingnamespacestd;
classBase {
public:
virtualvoidshow() { cout<<" In Base \n"; }
 };
classDerived: public Base {
public:
voidshow() { cout<<"In Derived \n"; }
 };
intmain(void) {
 Base *bp = new Derived;
 bp->show(); // <- Runtime Polymorphism in Action
return0;
}
In the aforementioned program bp is a pointer of type Base. A call to bp->show() calls show() function of the Derived class. This is because bp points to an object of the Derived class.

29. What differences separate structure from a class in C++?
There are two important distinctions between a class and a structure in C++. These are:

When deriving a structure from a class or some other structure, the default access specifier for the base class or structure is public. On the contrary, the default access specifier is private when deriving a class.
While the members of a structure are public by default, the members of a class are private by default
30. What is a static member?
Denoted by the static keyword, a static member is allocated storage, in the static storage area, only once during the program lifetime. Some important facts pertaining to the static members are:

Any static member function can’t be virtual
Static member functions don’t have ‘this’ pointer
The const, const volatile, and volatile declaration aren’t available for static member functions
31. What is the Reference variable?
The reference variable in C++ is the name given to the existing variables. The variable name and reference variable point share the same memory location in C++, which helps in updating the original variable using the reference variable. The code can be displayed in the following example.

#include<iostream>
using namespace std;
int main()
{
 int x = 10;
 // ref is a reference to x.
 int& ref = x;
 // Value of x is now changed to 20
 ref = 20;
 cout << "x = " << x << endl ;
 // Value of x is now changed to 30
 x = 30;
 cout << "ref = " << ref << endl ;
return 0;
}
Advanced C++ Interview Questions
32. Explain the Copy Constructor.
A member function that initializes an object using another object of the same class is known as a copy constructor in C++. They can also be made private. A call to the copy constructor can happen in any of the following 4 scenarios when:

The compiler generates a temporary object
An object is constructed or based on some another object of the same class
An object of the class is returned by value
An object of the class is passed (i.e., to a function) by value as an argument
The general function prototype for the Copy Constructor is:

ClassName (const ClassName &old_obj);

Point(int x1, int y1) { x=x1; y=y1;}

Point(const Point &p2) { x=p2.x; y=p2.y; }

33. Take a look at the following two code examples for printing a vector. Is there any advantage of using one over the other?
Sample Code 1:
vector vec;
/* ... .. ... */
for (auto itr = vec.begin(); itr != vec.end(); itr++) {
 itr->print();
}
Sample Code 2:
vector vec;
/* ... .. ... */
for (auto itr = vec.begin(); itr != vec.end(); ++itr) {
 itr->print();
}
Though both codes will generate the same output, sample code 2 is a more performant option. This is due to the fact that the post-increment ‘itr++’ operator is more expensive than the pre-increment ‘++itr’ operator.

The post-increment operator generates a copy of the element before proceeding with incrementing the element and returning the copy. Moreover, most compilers will automatically optimize sample code 1 by converting it implicitly into sample code 2.

34. Write a program that stores and displays the GPA (Grade Point Average) of a certain number of students, and you need to store and display it using C++. 
#include
#include
usingnamespacestd;
intmain()
{
int num;
cout << "Enter the total number of students: ";
cin >> num;
float* ptr;
 ptr = newfloat[num];
cout << "Enter the GPA of students." << endl;
for (int i = 0; i < num; ++i)
 {
cout << "Student" << i + 1 << ": ";
cin >> *(ptr + i);
 }
cout << "\nDisplaying GPA of students." << endl;
for (int i = 0; i < num; ++i) {
cout << "Student" << i + 1 << " :" << *(ptr + i) << endl;
 }
delete [] ptr;
return0;
}
35. What is a mutable storage class specifier? How can they be used?
A mutable storage class specifier is applied only to the class's non-static and non-constant member variable. It is used for altering the constant class object's member by declaring it. This can be done by using a storage class specifier.

36. What are the differences between a shallow copy and a deep copy?
The differences between a shallow copy and a deep copy are:

Shallow Copy

Deep Copy

Allows memory dumping on a bit-by-bit basis from one object to another

Allows the copy field, which is done by field from one object to another.

Reflects changes made to the new/copied object in the original object. 

Doesn't reflect changes made to the new/copied object in the original object.

37. What is an Abstract class?
An abstract class in C++ is referred to as the base class, which has at least one pure virtual function. In such a function, a person cannot instantiate an abstract class. This way, a pure virtual function is defined by using a pure specifier which is equal to zero during the declaration of the virtual member function in the class declaration. The code sample can be displayed as follows in example.

// An abstract class
class Test
{
// Data members of class
public:
// Pure Virtual Function
virtual void show() = 0;
/* Other members */
};
38. What are the functions of the scope resolution operator?
The functions of the scope resolution operator include the following.

It helps resolve the scope of various global variables.
It helps associate the function with the class when it is defined outside the class.
The code of the scope resolution operator can be displayed as follows.

#include <iostream>
using namespace std;
int my_var = 0;
int main(void) {
int my_var = 0;
::my_var = 1; // set global my_var to 1
my_var = 2; // setlocal my_var to 2
cout << ::my_var << ", " << my_var;
return 0;
}
39. What is a token?
A token is a name given to the various functions in C++ programs. Examples of tokens include a keyword, symbol, string literal, identifier, constant, etc. The following example explains these:

asm bool catch class
const_cast deletedynamic_cast explicit
export false friend inline
mutable namespace new operator
private protected public reinterpret_cast
static_cast templatethis throw
true try typeid typename
using virtualwchar_t
40. What is the ‘diamond problem’ that occurs with multiple inheritance in C++? 
The diamond problem in C++ represents the inability of the programming language to support hybrid inheritance using multiple and hierarchical inheritance.

Suppose we have a university with some faculty members and some graduate students. A simple inheritance scheme in this scenario might have different types of people in different roles. However, all of them inherit from the same Person class.

The Person class defines an abstract getRole() method that would then be overridden by its subclasses in order to return the correct role type. Things up to this point are simple. However, if we wish to model the role of a TA or Teaching Assistant then things get more complex.

A Teaching Assistant is both a student and a faculty member. The problem generates an inheritance diagram resembling a diamond, hence the name, diamond problem.

Which getRole() implementation should the Teaching Assistant inherit? Graduate Student or the Faculty Member? A potential answer might be to have the Teaching Assistant class override the getRole() method and return a newly-defined role, say TA.

However, such an answer would also be far from complete as it will hide the fact that a teaching assistant is both a faculty member and a graduate student.
