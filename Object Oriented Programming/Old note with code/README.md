
- [Object-Oriented-Programming](#object-oriented-programming)
    - [What is OOP?](#what-is-oop)
  - [Core Concepts](#core-concepts)
    - [Classes and Objects](#classes-and-objects)
    - [Encapsulation](#encapsulation)
    - [Inheritance](#inheritance)
    - [Polymorphism](#polymorphism)
    - [Abstraction](#abstraction)
- [Classes and Object](#classes-and-object)
  - [Class Related](#class-related)
    - [Structures and Classes Are Related](#structures-and-classes-are-related)
    - [Unions and Classes Are Related](#unions-and-classes-are-related)
  - [Friend Fucntions](#friend-fucntions)
  - [Friend Classes](#friend-classes)
  - [Inline](#inline)
    - [Inline Function](#inline-function)
    - [Inline Functions Within a Class](#inline-functions-within-a-class)
  - [Parameterized Constructors](#parameterized-constructors)
  - [Static Class Members](#static-class-members)
    - [Static Data Members](#static-data-members)
    - [Static Functions Member](#static-functions-member)
  - [When Constructors and Destructors Are Executed](#when-constructors-and-destructors-are-executed)
  - [The Scope Resolution Operator](#the-scope-resolution-operator)
    - [Nested Classes](#nested-classes)
    - [Local Classes or define class with in function](#local-classes-or-define-class-with-in-function)
- [Arrays of Objects and Pointer](#arrays-of-objects-and-pointer)
  - [Arrays of Objects](#arrays-of-objects)
    - [Pointers to Objects](#pointers-to-objects)
  - [The this Pointer](#the-this-pointer)
  - [Pointers to Derived Types](#pointers-to-derived-types)
  - [References](#references)
    - [Reference Parameters](#reference-parameters)
    - [Passing References to Objects](#passing-references-to-objects)
  - [C++'s Dynamic Allocation Operators](#cs-dynamic-allocation-operators)
    - [Allocating Arrays](#allocating-arrays)
    - [Allocating Objects](#allocating-objects)
- [Function Overloading Copy Constructors, and Default Arguments](#function-overloading-copy-constructors-and-default-arguments)
  - [Function Overloading](#function-overloading)
  - [constuctors overloading](#constuctors-overloading)
    - [Initialized and Uninitialized Objects](#initialized-and-uninitialized-objects)
  - [Copy Constructors](#copy-constructors)
  - [Default Function Arguments](#default-function-arguments)
- [Operator Overloading](#operator-overloading)
  - [Operator Overloading](#operator-overloading-1)
    - [perfix and postfix increment and decrement operator](#perfix-and-postfix-increment-and-decrement-operator)
    - [Overloading the Shorthand Operators( +=, –=,)](#overloading-the-shorthand-operators--)
    - [Operator Overloading Using a Friend Function](#operator-overloading-using-a-friend-function)
    - [Overloading new and delete](#overloading-new-and-delete)
  - [Overloading Some Special Operators](#overloading-some-special-operators)
- [Inheritance](#inheritance-1)
  - [Base-Class Access Control](#base-class-access-control)
    - [public](#public)
    - [Private](#private)
    - [protected](#protected)
  - [Inheriting Multiple Base Classes](#inheriting-multiple-base-classes)
  - [Constructors, Destructors, and Inheritance](#constructors-destructors-and-inheritance)
  - [Constructors and Destructors](#constructors-and-destructors)
    - [Constructors](#constructors)
    - [Destructors](#destructors)
    - [When Constructors and Destructors Are Execute](#when-constructors-and-destructors-are-execute)
  - [Passing Parameters to Base-Class Constructors](#passing-parameters-to-base-class-constructors)
  - [Granting Access](#granting-access)
  - [Virtual Base Classes](#virtual-base-classes)
- [Virtual Functions and Polymorphism](#virtual-functions-and-polymorphism)
  - [Virtual Functions or virtual methods](#virtual-functions-or-virtual-methods)
    - [Calling a Virtual Function Through a Base Class Reference](#calling-a-virtual-function-through-a-base-class-reference)
    - [The Virtual Attribute Is Inherited](#the-virtual-attribute-is-inherited)
    - [Virtual Functions Are Hierarchical](#virtual-functions-are-hierarchical)
  - [Pure Virtual Functions and Abstract Classes](#pure-virtual-functions-and-abstract-classes)
    - [abstract class](#abstract-class)
- [Collect resource](#collect-resource)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# Object-Oriented-Programming

### What is OOP?

Object-Oriented Programming is a programming paradigm(দৃষ্টান্ত) that organizes code into self-contained objects.\
Each object combines data and the methods that operate on that data, resulting in more modular, flexible, and reusable code.

## Core Concepts

### Classes and Objects

A class serves as a **blueprint** for creating objects, defining their attributes and methods.\
An object represents an instance of a class. It contains both data (attributes of the class) and the methods designed to manipulate that data.

### Encapsulation

Encapsulation is the mechanism that binds together code and the data it manipulates,and keeps both safe from outside interference and misuse.\
**Private** code is accessible only by another part of the same object. **Public** other parts of your program.

### Inheritance

**Do not repeat the code**⛔.Inheritance has the code reuse-ability.
The class being inherited from is the base class or superclass, while the class inheriting is the derived class or subclass.\
Animal(eat,sleep)<---------Dog(Black)\
base/super class <--Inherite--derived/sub class\
**Visual Representation**
![](inheritance.jpg )
If any language does not support the inheritance then its not calle the Object oriented programming language its called the **Object-Based-Language.**

### Polymorphism

**Polymorphis** means having many forms with same name.
Polymorphism allows objects of derived classes (subclasses) to be treated as objects of their base class (the superclass) but still maintain their unique behaviors.

- Compile_Time Polymorphism(static): Determined before the code runs, typically using method overloading.
- Run_Time Polymorphism(dynamic): Determined while the code is running, typically through method overriding.

### Abstraction

Abstraction means displaying only essential information and hiding the details.Like stack push pop function.

# Classes and Object

## Class Related

 A class is a logical abstraction, but an object has physical existence.In other words, an object is an instance of a class.\
 Access-specifier is one of these three C++ keywords:

 1. public
 2. private
 3. protected

Some point of class

1. By default, functions and data declared within a class are private.
2. private member may be accessed only by other members of the class.
3. The public access specifier allows functions or data to be accessible to other parts of your program
4. The protected access specifier is needed only when inheritance is involved

Functions that are declared within a class are called member functions. Variables that are elements of a class are called (member variables,data members,instance variable).No member can be declared as auto, extern, or register in class.

### Structures and Classes Are Related

 The only difference between a class and a struct is that by default all members are public in a struct and private in a class. In all other respects, structures and classes are equivalent.
<details>
  <summary> Code </summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

struct mystr
{
    void buildstr(char *s); // public
    void showstr();

  private:
    char str[255];
};

void mystr::buildstr(char *s)
{
    if (!*s)
        *str = '\0'; // initialize string
    else
        strcat(str, s);
}
void mystr::showstr()
{
    cout << str << "\n";
}
int main()
{
    mystr s;
    s.buildstr(""); // init
    s.buildstr("Hello ");
    s.buildstr("there!");
    s.showstr();
    return 0;
}
```

</details>

### Unions and Classes Are Related

Memory space can be used by one member variable at one point in time, which means if we assign value to one member variable, it will automatically deallocate the other member variable stored in the memory which will lead to loss of data.

- Access at a time at most one member

<details>
  <summary> Code </summary>

```cpp
#include <iostream> 
using namespace std; 
// Creating a union 
union geek { 
 // Defining data members 
 int age; //default public
 char grade; 
 float GPA; 
}; 

int main() 
{
 // Defining a union variable 
 union geek student1; 
 student1.age = 25; 
 cout << "Age : " << student1.age << endl; 

 student1.grade = 'B'; 
 cout << "Grade : " << student1.grade << endl; 

 student1.GPA = 4.5; 
 cout << "Age : " << student1.age << endl; 
 cout << "Grade : " << student1.grade << endl; 
 cout << "GPA : " << student1.GPA << endl; 

 return 0; 
}

```

</details>

```cpp
Age : 25
Grade : B
Age : 1083179008
Grade : 
GPA : 4.5
```

Look at the output where age and grade give us garbage value becouse all three member use same memory. When last initialize GPA then othe 2 member values deleted that's why we got garbage in age and grade.

## Friend Fucntions

 A friend function has access to all private and protected members of the class for which it is a friend.

<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

class myclass
{
    int a, b;
public:
    friend int sum(myclass x);//Friend declared
    void set_ab(int i, int j);
};

void myclass::set_ab(int i, int j) {
    a = i;
    b = j;
}

int sum(myclass x) {

    return x.a + x.b;
}
int main() {
    myclass n;
    n.set_ab(2, 3);
    cout << sum(n);
    return 0;
}
```

</details>

Without  declared frined in class the sum function can't access private and protected member.

Lets see another example, It's easy so don't be skip.
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

const int Idle = 0;
const int InUse = 1;

class C2;
//forward declaration or forward reference becouse c1 use c2 in friend function

class  C1
{
    int status;
public:
    friend int idle(C1 a, C2 b);
    void set_status(int status);
};
class  C2
{
    int status;
public:
    friend int idle(C1 a, C2 b);
    void set_status(int status);
};
// set method
void C1::set_status(int statu) {
    status = statu;
}

void C2::set_status(int statu) {
    status = statu;
}
//end set method

int idle(C1 a, C2 b)
{
    if (a.status or b.status)
        return 0;
    else return 1;
}

int main() {

    C1 x;
    C2 y;
    x.set_status(Idle);
    y.set_status(Idle);

    if (idle(x, y)) cout << "Screen can be used.\n";
    else cout << "In use.\n";
    x.set_status(InUse);

    if (idle(x, y)) cout << "Screen can be used.\n";
    else cout << "In use.\n";
    return 0;
}
// Output
Screen can be used.
In use.
```

</details>

- A friend of one class may be a member of another

Let's see an example same as above one.
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

const int Idle = 0;
const int InUse = 1;

class C2;
//forward declaration or forward reference becouse c1 use c2 in friend function

class  C1
{
    int status;
public:
    int idle(C2 b);
    void set_status(int status);

};

class  C2
{
    int status;
public:
    friend int C1::idle(C2 b);
    void set_status(int status);
};
// set method
void C1::set_status(int statu) {
    status = statu;
}

void C2::set_status(int statu) {
    status = statu;
}
//end set method

int C1::idle(C2 b)
{
    if (status or b.status)
        return 0;
    else return 1;
}

int main() {

    C1 x;
    C2 y;
    x.set_status(Idle);
    y.set_status(Idle);

    if (x.idle(y)) cout << "Screen can be used.\n";
    else cout << "In use.\n";
    x.set_status(InUse);

    if (x.idle(y)) cout << "Screen can be used.\n";
    else cout << "In use.\n";
    return 0;
}

//Output
Screen can be used.
In use.
```

</details>

## Friend Classes

It is possible for one class to be a friend of another class. The friend class and all of its member functions have access to the private members defined within the other class.

Let's see an easy example of Friend class.
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;
class TwoValues {
	int a;
	int b;
public:

	TwoValues(int i, int j) {
		a = i, b = j;
	}
	friend class Min;
};

class Min {
public:
	int min(TwoValues x) {
		return x.a < x.b ? x.a : x.b;
	}
};

int main() {

	TwoValues ob(10, 20);
	Min m;
	cout << m.min(ob);
	return 0;
}
// //output
// 10
```

</details>

## Inline

### Inline Function

Inline function substitution is performed by the C++ compiler at compile time. An inline function may increase efficiency if it is small.

When we use inline function

- Very small function.
- The functions are called several times in a program.

The code we write
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

inline int max(int a,int b)
{
    return a>b?a:b;
}
int main() {

    cout<<max(10,20);
    cout<<" "<<max(40,30);
    return 0;

}
```

</details>

The code transfrom after compilation.

```cpp
#include <iostream>
using namespace std;
int main()
{
    cout << (10 > 20 ? 10 : 20);
    cout << " " << (99 > 88 ? 99 : 88);
    return 0;
}
```

Inline is actually just a request, not a command, to the compiler. The compiler can choose to ignore it.

- Inline function can be use in class. Let's see an example

<details>
  <summary> Code </summary>

```cpp
  #include <iostream>

using namespace std;
class myclass {
    int a, b;
public:
    void init(int i, int j);
    void show();
};
// Create an inline function.
inline void myclass::init(int i, int j)
{
    a = i;
    b = j;
}
// Create another inline function.
inline void myclass::show()
{
    cout << a << " " << b << "\n";
}
int main()
{
    myclass x;
    x.init(10, 20);
    x.show();
    return 0;
}
```

</details>

### Inline Functions Within a Class

When a function is defined inside a class declaration, it is automatically made into an inline function (if possible).
<details>
  <summary> Code </summary>

```cpp
#include <iostream>
using namespace std;
class myclass {
    int a, b;
public:
// automatic inline
    void init(int i, int j) { a = i; b = j; }
    void show() { cout << a << " " << b << "\n"; }
};
int main()
{
    myclass x;
    x.init(10, 20);
    x.show();
    return 0;
}
```

</details>

## Parameterized Constructors

It is possible to pass arguments to constructors. Typically, these arguments help initialize an object when it is created.
<details>
  <summary> Code </summary>
  
```cpp
# include <iostream>
using namespace std;
class myclass {
    int a, b;
public:
    myclass(int i, int j) {a = i; b = j;}
    void show() {cout << a << " " << b;}
};
int main()
{
    myclass ob(3, 5);
    ob.show();
    return 0;
    C++
}
```

</details>

We can define object with perameter two method.

- myclass ob(3, 4);
- myclass ob = myclass(3, 4);
There have some defarent. We will learn it leter.

<details>
<summary>Code ->Another example</summary>

```cpp
#include <iostream>
#include <cstring>
using namespace std;
const int IN = 1;
const int CHECKED_OUT = 0;
class book {
    char author[40];
    char title[40];
    int status;
public:
    book(char *n, char *t, int s);
    int get_status() {return status;}
    void set_status(int s) {status = s;}
    void show();
};
book::book(char *n, char *t, int s)
{
    strcpy(author, n);
    strcpy(title, t);
    status = s;
}
void book::show()
{
    cout << title << " by " << author;
    cout << " is ";
    if (status == IN) cout << "in.\n";
    else cout << "out.\n";
}
int main()
{
    book b1("Twain", "Tom Sawyer", IN);
    book b2("Melville", "Moby Dick", CHECKED_OUT);
    b1.show();
    b2.show();
    return 0;
}
```

</details>
> Output:Tom Sawyer by Twain is in.\ Moby Dick by Melville is out.

If a constructor only has one parameter, there is a third way to pass an initial value to that constructor.
> X ob = 99;

## Static Class Members

### Static Data Members

 **Only one copy** of that variable will exist and that all objects of the classwill share that variable.No matter how many objects of a class
 are created, **only one copy** of a static data member exists. All static variables are initialized to zero before the first object
 is created.\
 Static varible must provide a global definition for it elsewhere, outside the class.When you declare a static data member within a class, you are not defining it. A static member variable exists before any object of its class is created.

Let's see and proper example
<details>
  <summary> Code </summary>
  
```cpp
# include<bits/stdc++.h>
using namespace std;
class employee
{
    int id;
    static int count;
public:
    void setData(int i)
    {
        id = i;
        count++;
    }
    void getData(void)
    {
        cout << "ID: " << id << ", Number of employee: " << count << endl;
    }

};
int employee::count;//global added. without globaly it's not initialize.

int main() {

    employee a, b, c;
    a.setData(3);//count=1
    b.setData(4);//count=2
    c.setData(1);//count=3

    b.getData();
    return 0;
}

```

</details>

>Output->  ID: 4, Number of employee: 3

Here count is static which allocat one memory location for 3 object, means if I change in object(a) it will also change in object(b).

<details>
<summary>You can see another example</summary>

```cpp
#include <iostream>
using namespace std;
class cl {
    static int resource;
public:
    int get_resource();
    void free_resource() {resource = 0;}
};
int cl::resource; // define resource
int cl::get_resource()
{
    if (resource) return 0; // resource already in use
    else {
        resource = 1;
        return 1;  // resource allocated to this object
    }
}
int main()
{
    cl ob1, ob2;
    if (ob1.get_resource()) cout << "ob1 has resource\n";
    if (!ob2.get_resource()) cout << "ob2 denied resource\n";
    ob1.free_resource();  // let someone else use it
    if (ob2.get_resource())
        cout << "ob2 can now use resource\n";
    return 0;
}
```

</details>

### Static Functions Member

- It is a member function that is used to access only static data members.
- Astatic member function does not have a this pointer.
- They cannot be declared as const or volatile

Let's see two example\
we can access static function

- CLASS_NAME::Function_Name()
- OBJECT_NAME::Function_Name()

<details>
<summary>1st example</summary>

```cpp
#include<bits/stdc++.h>
using namespace std;
class Employee
{
    int id;
    static int count;

public:
    void setData(void)
    {
        cout << "Enter the id" << endl;
        cin >> id;
        count++;
    }
    void getData(void)
    {
        cout << "The id of this employee is " << id << " and this is employee number " << count << endl;
    }

    static void getCount(void){
        // cout<<id; // throws an error
        cout<<"The value of count is "<<count<<endl;
    }
};
int main()
{
    Employee harry, rohan, lovish;
    // harry.id = 1;
    // harry.count=1; // cannot do this as id and count are private

    harry.setData();
    harry.getData();
    Employee::getCount();

    rohan.setData();
    rohan.getData();
    Employee::getCount();

    lovish.setData();
    lovish.getData();
    Employee::getCount();

    return 0;
}
```

</details>

<details>
<summary>2nd example</summary>

```cpp
#include <iostream>
using namespace std;
class cl {
    static int resource;
public:
    static int get_resource();
    void free_resource() { resource = 0; }
};
int cl::resource; // define resource
int cl::get_resource()
{
    if (resource) return 0; // resource already in use
    else {
        resource = 1;
        return 1;  // resource allocated to this object
    }
}
int main()
{
    cl ob1, ob2;
    /* get_resource() is static so may be called independent
    of any object. */
    if (cl::get_resource()) cout << "ob1 has resource\n";
    if (!cl::get_resource()) cout << "ob2 denied resource\n";
    ob1.free_resource();
    if (ob2.get_resource()) // can still call using object syntax
        cout << "ob2 can now use resource\n";
    return 0;
}
```

</details>

## When Constructors and Destructors Are Executed

- Alocal object's constructor is executed when the object's declaration statement is encountered
- Global objects have their constructors execute before main( ) begins execution.

Let's see and example of clear understanding
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

class myclass
{
public:
    int who;
    myclass(int id);
    ~myclass();
} global_obj1(1), global_obj2(2);

myclass::myclass(int id)
{
    cout << "Initializing " << id << "\n";
    who = id;
}
myclass::~myclass()
{
    cout << "Destructing " << who << "\n";
}

int main() {

    myclass local_obj1(3);
    cout << "This will not be first line displayed.\n";
    myclass local_ob2(4);
    return 0;
}
```

</details>

<details>
  <summary> Output </summary>

```
 Initializing 1
 Initializing 2
 Initializing 3
 This will not be first line displayed.
 Initializing 4
 Destructing 4
 Destructing 3
 Destructing 2
 Destructing 1
 ```

</details>

Look at the output.

## The Scope Resolution Operator

- As you know, the :: operator links a class name with a member name
- We can also use (::) this operator for access global member when same name also avalible in local.

```cpp
int i;  // global i
void f()
{
    int i; // local i
    ::i = 10; // now refers to global i
    .
    .
    .
}
```

Here global i=10;local i=undefined;

### Nested Classes

It is possible to define one class within another. Doing so creates a nested class.

### Local Classes or define class with in function

 A class may be defined within a function.
<details>
  <summary> Code </summary>

```cpp
#include<bits/stdc++.h>
using namespace std;

void f();

int main() {

    f();
    return 0;
}
void f()
{
    class myclass
    {
        int i;
    public:
        void put_i(int n) { i = n; }
        int get_i() { return i; }

    } ob;

    ob.put_i(10);
    cout << ob.get_i() << endl;
}
```

</details>

- The local class may not use or access local
 variables of the function
- Except that a local class has access
 to static local variables declared within the function

# Arrays of Objects and Pointer

## Arrays of Objects

 C++, it is possible to have arrays of objects.
 The syntax for declaring and using an object array is exactly the same as it is for any other type of array.
<details>
  <summary> Code </summary>

   ```cpp
 #include<bits/stdc++.h>
using namespace std;

class cl
{
    int i;
public:
    void set_i(int j) {i = j;};
    int get_i() {return i;};

};

int main() {

    cl ob[3];

    for (int i = 0; i < 3; i++)
    {
        ob[i].set_i(i + 1);
    }
    for (int i = 0; i < 3; i++)
    {
        cout << ob[i].get_i() << endl;
    }
    return 0;
}
```

</details>

if constructor has single argument.
>cl ob[3] = {1, 2, 3};\
> cl ob[3] = { cl(1), cl(2), cl(3) };
This two method we can use.

 If an object's constructor requires two or more arguments.

 ```cpp
cl ob[3] = {
    cl(1, 2), // initialize
    cl(3, 4),
    cl(5, 6)
};
 ```

If we have argument in constructor then constructor requires initializers
> cl a[9] // error if constructor has argument.

### Pointers to Objects

When accessing members of a class given a pointer to an object, use the arrow(–>) operator instead of the dot operator.

<details>
  <summary> Code </summary>

  ```cpp
#include<bits/stdc++.h>
using namespace std;

class cl
{
    int i;
public:
    cl(int j) {i = j;}
    int get_i( ) {return i;}
};

int main() {

    cl ob(88), *p;
    p = &ob;
    cout << p->get_i();// use -> to call get_i()
    return 0;
}
```

</details>

Another example
<details>
  <summary> Code </summary>

  ```cpp
#include <iostream>
using namespace std;
class cl {
    int i;
public:
    cl() { i = 0; }
    cl(int j) { i = j; }
    int get_i() { return i; }
};
int main()
{
    cl ob[3] = {1, 2, 3};
    cl *p;
    int i;
    p = ob; // get start of array
    for (i = 0; i < 3; i++) {
        cout << p->get_i() << "\n";
        cout<< p.get_i() <<endl;
        p++; // point to next object
    }
    return 0;
}

```

</details>

## The this Pointer

1. When local variable’s name is same as member’s name

<details>
   <summary> Code </summary>

 ```cpp
# include<iostream>
using namespace std;
  
/*local variable is same as a member's name*/
class Test
{
private:
   int x;
public:
   void setX (int x)
   {
       // The 'this' pointer is used to retrieve the object's x
       // hidden by the local variable 'x'
       this->x = x;
   }
   void print() { cout << "x = " << x << endl; }
};
  
int main()
{
   Test obj;
   int x = 20;
   obj.setX(x);
   obj.print();
   return 0;
}

```

</details>

2. To return reference to the calling object

<details>
  <summary> Code </summary>

 ```cpp
 #include<iostream>
using namespace std;

class Test
{
private:
    int x;
    int y;
public:
    Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
    Test &setX(int a) { x = a; return *this; }
    Test &setY(int b) { y = b; return*this; }
    void print() { cout << "x = " << x << " y = " << y << endl; }
};

int main()
{
    Test obj1(5, 5);

    // Chained function calls.  All calls modify the same object
    // as the same object is returned by reference
    obj1.setX(10).setY(20);

    obj1.print();
    return 0;
}

```

</details>

## Pointers to Derived Types

1. a pointer of one type cannot point to an object of a different type.
2. assume two classes called B and D.
3. D is derived from the base class B.
4. a pointer of type B*may also point to an object of type D.
5. the opposite is not true.

<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class base
{
    int i;
public:
    void set_i(int num) {i = num;}
    int get_i() {return i;}
};

class derived: public base {
    int j;
public:
    void set_j(int num) { j = num; }
    int get_j() { return j; }
};

int main() {
    base *bp;
    derived d;
    bp = &d; // base pointer points to derived object
    // access derived object using base pointer
    bp->set_i(10);
    cout << bp->get_i() << " ";
    /* The following won't work. You can't access elements of
    a derived class using a base class pointer.
    bp->set_j(88); // error
    cout << bp->get_j(); // error
    */
    return 0;
}

```

</details>

If we want to access drived class member we can't direct access becouse the pointer point into base class.

``` cpp
 // access now allowed because of cast
 ((derived *)bp)->set_j(88);
 cout << ((derived *)bp)->get_j()
```

Lets see another example
<details>
  <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
class base {
    int i;
public:
    void set_i(int num) { i = num; }
    int get_i() { return i; }
};
class derived: public base {
    int j;
public:
    void set_j(int num) {j = num;}
    int get_j() {return j;}
};
int main()
{
    base *bp;
    derived d[2];
    bp = d;
    d[0].set_i(1);
    d[1].set_i(2);
    cout << bp->get_i() << " ";
    bp++; // relative to base, not derived
    cout << bp->get_i(); // garbage value displayed
    return 0;
}```

</details>

## Pointers to Class Members

- A pointer to a member is not the same as a normal C++ pointer
- a pointer to a member provides only an offset into an object of the member's class at which that member can be found.
- To access a member of a class given a pointer to it, you must use the special pointer-to-member operators .*and –>*.

<details>
  <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
class cl {
public:
    cl(int i) { val = i; }
    int val;
    int double_val() { return val + val; }
};
int main()
{
    int cl::*data; // data member pointer
    int (cl::*func)(); // function member pointer
    cl ob1(1), ob2(2); // create objects

    data = &cl::val; // get offset of val
    func = &cl::double_val; // get offset of double_val()

    cout << "Here are values: ";
    cout << ob1.*data << " " << ob2.*data << "\n";

    cout << "Here they are doubled: ";
    cout << (ob1.*func)() << " ";
    cout << (ob2.*func)() << "\n";
    return 0;
}

```

</details>

Let's see another example
<details>
  <summary> Code </summary>

 ```cpp
 
 #include <iostream>
using namespace std;
class cl {
public:
    cl(int i) { val = i; }
    int val;
    int double_val() { return val + val; }
};
int main()
{
    int cl::*data; // data member pointer
    int (cl::*func)(); // function member pointer
    cl ob1(1), ob2(2); // create objects

    cl *p1, *p2;
    p1 = &ob1; // access objects through a pointer
    p2 = &ob2;

    data = &cl::val; // get offset of val
    func = &cl::double_val; // get offset of double_val()
    cout << "Here are values: ";
    cout << p1->*data << " " << p2->*data << "\n";

    
    cout << "Here they are doubled: ";
    cout << (p1->*func)() << " ";
    cout << (p2->*func)() << "\n";
    return 0;
}

```

</details>

## References

 There are three ways that a reference can be used:

- as a function parameter,
- as a function return value,
- as a stand-alone reference.

### Reference Parameters

<details>
    <summary> Code </summary>

 ```cpp
 // Use a reference parameter.

# include <iostream>

using namespace std;
void neg(int &i); // i now a reference
int main()
{
    int x;
    x = 10;
    cout << x << " negated is ";
    neg(x); // no longer need the & operator
    cout << x << "\n";
    return 0;
}
void neg(int &i)
{
    i = -i; // i is now a reference, don't need *
}

```

</details>

### Passing References to Objects

when you pass by reference, no copy of the object is made.
<details>
  <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;
class cl
{
    int id;
public:
    int i;
    cl(int i);
    ~cl();
    void neg(cl &o) {o.i = -o.i;}
};
cl::cl(int num)
{
    cout << "Constructing " << num << "\n";
    id = num;
}
cl::~cl()
{
    cout << "Destructing " << id << "\n";
}
int main() {

    cl o(1);
    o.i = 10;
    o.neg(o);

    cout << o.i << endl;
    return 0;
}

```

</details>

## C++'s Dynamic Allocation Operators

 The newoperator allocates memory and returns a pointer to the start of it. The delete operator frees memory previously allocated using new. The general forms of newanddelete are shown here:

```c++
 p_var = new type;
 delete p_var;
```

<details>
   <summary> Code </summary>

  ```cpp

# include<bits/stdc++.h>

using namespace std;

int main() {

    int *p;
    try {

        p = new int;

    } catch (bad_alloc xa) {
        cout << "Allocation Failure\n";
        return 1;
    }

    *p = 100;

    cout << "At " << p << " ";
    cout << "is the value " << *p << "\n";
    delete p;

    return 0;
}

```

</details>

 This program gives the allocated integer an initial value of 87:
 <details>
   <summary> Code </summary>

  ```cpp

# include <iostream>
# include <new>

using namespace std;
int main()
{
    int *p;
    try {
        p = new int (87); // initialize to 87
    } catch (bad_alloc xa) {
        cout << "Allocation Failure\n";
        return 1;
    }
    cout << "At " << p << " ";
    cout << "is the value " <<*p << "\n";
    delete p;
    return 0;
}

```

</details>

### Allocating Arrays

 ```cpp
 p_var = new array_type [size];
 delete [ ] p_var;
 ```

<details>
   <summary> Code </summary>

 ```cpp
 #include <iostream>
# include <new>
using namespace std;
int main()
{
    int *p, i;
    try {
        p = new int[10];
    } catch (bad_alloc xa) {
        cout << "Allocation Failure\n";
        return 1;
    }
    for (i = 0; i < 10; i++ )
        p[i] = i;
    for (i = 0; i < 10; i++)
        cout << p[i] << " ";
    delete []p;
    return 0;
}

```

</details>

### Allocating Objects

<details>
   <summary> Code </summary>

 ```cpp
 #include <iostream>
# include <new>
# include <cstring>
using namespace std;
class balance {
    double cur_bal;
    char name[80];
public:
    balance(double n, char *s) {
        cur_bal = n;
        strcpy(name, s);
    }
    balance() {} // parameterless constructor
    ~balance() {
        cout << "Destructing ";
        cout << name << "\n";
    }
    void set(double n, char*s) {
        cur_bal = n;
        strcpy(name, s);
    }
    void get_bal(double &n, char *s) {
        n = cur_bal;
        strcpy(s, name);
    }
};
int main()
{
    balance*p;
    char s[80];
    double n;
    int i;
    try {
        p = new balance [3]; // allocate entire array
    } catch (bad_alloc xa) {
        cout << "Allocation Failure\n";
        return 1;
    }
// note use of dot, not arrow operators
    p[0].set(12387.87, "Ralph Wilson");
    p[1].set(144.00, "A. C. Conners");
    p[2].set(-11.23, "I. M. Overdrawn");
    for (i = 0; i < 3; i++) {
        p[i].get_bal(n, s);
        cout << s << "'s balance is: " << n;
        cout << "\n";
    }
    delete [] p;
    return 0;
}

```

</details>

# Function Overloading Copy Constructors, and Default Arguments

## Function Overloading

1. The **type** and/or number of the **parameters** of each overloaded function must differ.
2. It is not **sufficient** for two functions to differ only in their **return types**. Return types do
 not provide sufficient information in all cases for the compiler to decide which function
 to use. Of course, overloaded functions may differ in their return types, too.

The example of function overloading is **abs()** function. Which work for int,float,double.
<details>
  <summary> Code </summary>

```cpp
# include <stdio.h>
int abs(int a) {
  return a >= 0 ? a : -a;
}
float abs(float a) {
  return a >= 0 ? a : -a;
}
double abs(double a) {
  return a >= 0 ? a : -a;
}

int main() {
  float x = -5.68;
  printf("%f", abs(x));
}

```

</details>

<details>
  <summary> Code </summary>

  ```cpp
  #include <iostream>
using namespace std;
int myfunc(int i); // these differ in number of parameters
int myfunc(int i, int j);
int main()
{
    cout << myfunc(10) << " "; // calls myfunc(int i)
    cout << myfunc(4, 5); // calls myfunc(int i, int j)
    return 0;
}
int myfunc(int i)
{
    return i;
}
int myfunc(int i, int j)
{
    return i * j;
}
```

</details>

## constuctors overloading

<details>
  <summary> Code </summary>

 ```cpp
 #include <iostream>

# include <cstdio>

using namespace std;
class date {
    int day, month, year;
public:
    date(char *d);
    date(int m, int d, int y);
    void show_date();
};
// Initialize using string.
date::date(char*d)
{
    sscanf(d, "%d%*c%d%*c%d", &month, &day, &year);
}
// Initialize using integers.
date::date(int m, int d, int y)
{
    day = d;
    month = m;
    year = y;
}
void date::show_date()
{
    cout << month << "/" << day;
    cout << "/" << year << "\n";
}
int main()
{
    date ob1(12, 4, 2003), ob2("10/22/2003");
    ob1.show_date();
    ob2.show_date();
    return 0;
}

```

</details>

### Initialized and Uninitialized Objects

<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class powers
{
    int x;
public:
    powers() { x = 0; } // no initializer
    powers(int n) { x = n; } // initializer
    int getx() { return x; }
    void setx(int i) {
        x = i;
    }
}

int main() {
    powers ofTwo[] = {1, 2, 4, 8, 16}; // initialized
    powers ofThree[5]; // uninitialized

    return 0;
}

```

</details>

## Copy Constructors

MyClass B = A;
If a bitwise copy is performed, then B will be an exact copy of A. This means that B will be using the same piece of allocated memory that A is using, instead of allocating its own. Clearly, this is not the desired outcome. For example, if MyClass includes a destructor that frees the memory, then the same piece of memory will be freed twice when A and B are destroyed!
<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class array
{
    int *p;
    int size;
public:
    array(int sz) {
        try {
            p = new int[sz];
        } catch (bad_alloc xa) {
            cout << "Allocation Failure\n";
            exit(EXIT_FAILURE);
        }
        size = sz;
    };
    array(const array &a);
    ~array(delete []p);
    void put(int i, int j) {
        if (i >= 0 && i < size) p[i] = j;
    }
    int get(int i) {
        return p[i];
    }

};

array::array(const array &a)
{
    int i;
    try {
        p = new array[a.size];
    } catch (bad_alloc xa) {
        cout << "Allocation Failure\n";
        exit(EXIT_FAILURE);
    }
    for (i = 0; i < a.size; i++)p[i] = a.p[i];
}

int main()
{
    array num(10);
    int i;
    for (i = 0; i < 10; i++) num.put(i, i);
    for (i = 9; i >= 0; i--) cout << num.get(i);
    cout << "\n";
// create another array and initialize with num
    array x(num); // invokes copy constructor
    for (i = 0; i < 10; i++) cout << x.get(i);
    return 0;
}

```

</details>

## Default Function Arguments

<details>
  <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class cube
{
    int x, y, z;
public:
    cube(int i = 0, int j = 0, int k = 0)
    {
        x = i, y = j, z = k;
    }
    int sum()
    {
        return x + y + z;
    }

};

int main() {

    cube a(2, 3, 4), b;//we can also send 2 arguments the k defult value

    cout << a.sum() << endl;
    cout << b.sum() << endl;

    return 0;
}

```

</details>

- Ambiguous

<details>
   <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
int myfunc(int i);
int myfunc(int i, int j = 1);
int main()
{
    cout << myfunc(4, 5) << " "; // unambiguous
    cout << myfunc(10); // ambiguous
    return 0;
}
int myfunc(int i)
{
    return i;
}
int myfunc(int i, int j)
{
    return i * j;
}

```

</details>

# Operator Overloading

## Operator Overloading

As we know, In c++ if a and b is number , we can use a+b then the result give use the sum of a and b. But if we want to sum a+b where a and b is complex number then this will not work. Using operator overloading we can make a overloading function where we will define how the struct or class or complex sum process should work.

Let's see a Inheritance example

In the code three(building,school,house) class writen. where school and house inherite building and use funciton of building. We will learn more about it leter.

<details>
  <summary> Code </summary>

  <blockquote>
  <blockquote>

  ```cpp
  #include <bits/stdc++.h>
using namespace std;

class building {
    int rooms;
    int floors;
    int area;

public:
    void set_rooms(int num);
    int get_rooms();
    void set_floors(int num);
    int get_floors();
    void set_area(int num);
    int get_area();
};
class house : public building {
    int bedrooms;
    int baths;

public:
    void set_bedrooms(int num);
    int get_bedrooms();
    void set_baths(int num);
    int get_baths();
};
class school : public building {
    int classrooms;
    int offices;

public:
    void set_classrooms(int num);
    int get_classrooms();
    void set_offices(int num);
    int get_offices();
};
  ```

  </blockquote>
  <details><summary>click for see getter and setter </summary><blockquote>

  ```cpp
 void building::set_rooms(int num) {
    rooms = num;
}
void building::set_floors(int num) {
    floors = num;
}
void building::set_area(int num) {
    area = num;
}
int building::get_rooms() {
    return rooms;
}
int building::get_floors() {
    return floors;
}
int building::get_area() {
    return area;
}
void house::set_bedrooms(int num) {
    bedrooms = num;
}
void house::set_baths(int num) {
    baths = num;
}
int house::get_bedrooms() {
    return bedrooms;
}
int house::get_baths() {
    return baths;
}
void school::set_classrooms(int num) {
    classrooms = num;
}
void school::set_offices(int num) {
    offices = num;
}
int school::get_classrooms() {
    return classrooms;
}
int school::get_offices() {
    return offices;
}
  ```

</blockquote></details>

<blockquote>

  ```cpp
int main() {
    house h;
    school s;
    h.set_rooms(12);
    h.set_floors(3);
    h.set_area(4500);
    h.set_bedrooms(4);
    h.set_baths(3);
    cout << "house has " << h.get_bedrooms() << " bedrooms\n";

    s.set_rooms(200);
    s.set_classrooms(180);
    s.set_offices(5);
    s.set_area(25000);
    cout << "school has " << s.get_classrooms();
    cout << " classrooms\n";
    cout << "Its area is " << s.get_area();
    return 0;
}
  ```

  </blockquote>
  </blockquote>
</details>

Operator overloading allows C++ operators to have user-defined meanings on user-defined types or classes.

It's work for + operator where 2 complex number will summation.
<details>
  <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class Complex
{
    int real, imag;
public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }
    Complex operator+(Complex const& obj) {
        Complex res;
        res.real = real + obj.real;
        res.imag = imag + obj.imag;
        return res;
    }
    void print() { cout << real << " + i" << imag << '\n'; }

};

int main() {

    Complex c1(10, 5), c2(2, 4), c3(3, 4);
    
    // c3=c1+c4
    // error becouse compiler doesnot know about my class. 

    Complex c4 = c1 + c2;
    c4.print();
    c4 = c1 + c2 + c3;
    c4.print();

    return 0;
}

```

</details>

- Some extra operator overloded.

<details>
    <summary> Code </summary>

 ```cpp
 
 #include<bits/stdc++.h>
using namespace std;

class Complex
{
    int real, imag;
public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }
    Complex operator+(Complex const& obj);
    Complex operator-(Complex const& obj);
    Complex operator=(Complex const& obj);
    Complex operator++();
    void print() { cout << real << " + i" << imag << '\n'; }

};
// summation
Complex Complex::operator+(Complex const& obj) {
    Complex res;
    res.real = real + obj.real;
    res.imag = imag + obj.imag;
    return res;
}
// subtraction
Complex Complex::operator-(Complex const& obj) {
    Complex res;
    res.real = real - obj.real;
    res.imag = imag - obj.imag;
    return res;
}
// Increment
Complex Complex::operator++() {
    Complex res;
    res.real = real + 1;
    res.imag = imag + 1;
    return res;
}
// assigement
Complex Complex::operator=(Complex const& obj) {

    real =  obj.real;
    imag =  obj.imag;
    return *this;
}
int main() {

    Complex c1(10, 5), c2(2, 4), c3(3, 4);

    // c3=c1+c4
    // error becouse compiler doesnot know about my class.

    Complex c4 = c1 + c2;
    c4.print();
    c4 = c1 + c2 + c3;
    c4.print();

    c4 = c1 + c2 - c3;
    c4.print();

    Complex c5 = ++c4;
    c5.print();


    return 0;
}

```

</details>

We can't overload below operator

1. scope operator(::)
2. sizeof
3. member selector(.)
4. member pointer selector(*)
5. ternary operator (?:)

### perfix and postfix increment and decrement operator

```cpp
// Prefix increment
 type operator++( ) {
     // body of prefix operator
 }
 // Postfix increment
 type operator++(int x) {
 // body of postfix operator
 }

 // Prefix decrement
 type operator– –( ) {
 // body of prefix operator
 }
 // Postfix decrement
 type operator– –(int x) {
 // body of postfix operator
 }
 ```

### Overloading the Shorthand Operators( +=, –=,)

```cpp
Complex Complex::operator+=(Complex op2)
{
    real = op2.real + real;
    imag = op2.imag + imag;
    return *this;
}
```

### Operator Overloading Using a Friend Function

 Since a friend function is not a member of the class, it does not have a this pointer. Therefore, an overloaded friend operator function is passed the operands explicitly. This means that a friend function that overloads a binary operator has two parameters, and a friend function that overloads a unary operator has one parameter.
 <details>
   <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class Complex
{
    int real, imag;
public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }
    friend Complex operator+(Complex obj1, Complex obj2);
    friend Complex operator++(Complex &obj2);
    friend Complex operator++(Complex &obj2, int);
    void print() { cout << real << " + i" << imag << '\n'; }

};
// summation
Complex operator+(Complex obj1, Complex obj2) {
    Complex res;
    res.real = obj2.real + obj1.real;
    res.imag = obj2.imag + obj1.imag;
    return res;
}

// prefix increment
Complex operator++(Complex &obj2) {

    obj2.real++;
    obj2.imag++;
    return obj2;
}
// suffix increment
Complex operator++(Complex &obj2, int) {

    obj2.real++;
    obj2.imag++;
    return obj2;
}

int main() {

    Complex c1(10, 5), c2(2, 4), c3(3, 4);

    // c3=c1+c4
    // error becouse compiler doesnot know about my class.

    Complex c4 = c1 + c2;
    c4.print();

    ++c1;
    c1++;
    c1.print();
    return 0;
}
 ```

</details>

### Overloading new and delete

<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class loc
{
    int longitude, latitude
public:
    loc() {longitude = latitude = 0;}
    loc(int lg, int lt) {
        longitude = lg;
        latitude = lt;
    }
    void show() {
        cout << longitude << " ";
        cout << latitude << "\n";
    }
    void *operator new(size_t size);
    void operator delete(void*p);
};
void *loc::operator new(size_t size)
{
    void*p;
    cout << "In overloaded new.\n";
    p = malloc(size);
    if (!p) {
        bad_alloc ba;
        throw ba;
    }
    return p;
}
void loc::operator delete(void *p)
{
    cout << "In overloaded delete.\n";
    free(p);
}

int main() {

    loc *p1, *p2;

    try {
        p1 = new loc (10, 20);
    } catch (bad_alloc xa) {
        cout << "Allocation error for p1.\n";
        return 1;
    }
    try {
        p2 = new loc (-10, -20);
    } catch (bad_alloc xa) {
        cout << "Allocation error for p2.\n";
        return 1;;
    }
    p1->show();
    p2->show();
    delete p1;
    delete p2;
    return 0;
}

```

</details>

## Overloading Some Special Operators

- []
- ()
- –>,

Let see for this [ ]
<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class atype
{
    int a[3];
public:
    atype(int i, int j, int k)
    {
        a[0] = i;
        a[1] = j;
        a[2] = k;
    }
    int operator[](int i)
    {
        return a[i];
    }

};

int main() {

    atype ob(1, 2, 3);

    cout << ob[1] << endl;
    ob[1]=10;
    cout<<ob[1]<<endl;
    return 0;
    // output  2,10;
}

```

</details>

# Inheritance

![](./inheritance.png)

 Base-Class Access Control

## Base-Class Access Control

- private means private. It's can not be access withot friend function.
- If no access specifier is present, the access specifier is private
- If the derived class is a struct, then public is the default

### public

- base class is public, all **public members** of the base become public members of the derived class
- all protected members of the base become protected members of the derived class.

<details>
    <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class base
{
    int i, j;
public:
    void set(int a, int b) { i = a; j = b; }
    void show() { cout << i << " " << j << "\n"; }
};
class derived: public base {
    int k;
public:
    derived(int x) {k = x;}
    void showk() {cout << k << endl;}
};

int main() {

    derived ob(3);
    ob.set(1, 2);
    ob.show();
    ob.showk();
    return 0;
}

```

</details>

### Private

- all public and protected members of the base class become private members of the derived class

<details>
    <summary> Code </summary>

  ```cpp
  #include<bits/stdc++.h>
using namespace std;

class base
{
    int i, j;
public:
    void set(int a, int b) { i = a; j = b; }
    void show() { cout << i << " " << j << "\n"; }
};
class derived: private base {
    int k;
public:
    derived(int x) {k = x;}
    void showk() {cout << k << endl;}
};


int main()
{
    derived ob(3);
    ob.set(1, 2); // error, can't access set()
    ob.show(); // error, can't access show()
    return 0;
}
```

</details>

### protected

- When a member of a class is declared as protected, that member is not accessible by other, nonmember elements of the program
- inherit a base class as protected.all public and protected members of the base class become protected members of the derived class.
- If the base class is inherited as public, then
the base class' protected members become protected members of the derived class

<details>
 <summary> Code </summary>

 ```cpp
 // This program won't compile.

# include <iostream>

using namespace std;

class base {
protected:
    int i, j;
public:
    void set(int a, int b) { i = a; j = b; }
    void show() { cout << i << " " << j << "\n"; }
};

// Now, all elements of base are private in derived1.
class derived1 : private base {
    int k;
public:
// this is legal because i and j are private to derived1
    void setk() { k = i * j; } // OK
    void showk() { cout << k << "\n"; }
};

// Access to i, j, set(), and show() not inherited.
class derived2 : public derived1 {
    int m;
public:
// illegal because i and j are private to derived1
    void setm() { m = i - j; } // Error
    void showm() { cout << m << "\n"; }
};

int main()
{
    derived1 ob1;
    derived2 ob2;
    ob1.set(1, 2); // error, can't use set()
    ob1.show(); // error, can't use show()
    ob2.set(3, 4); // error, can't use set()
    ob2.show(); // error, can't use show()
    return 0;
}
 ```

</details>

<details>
  <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;

class base {
protected:
    int i, j; // private to base, but accessible by derived
public:
    void setij(int a, int b) { i = a; j = b; }
    void showij() { cout << i << " " << j << "\n"; }
};

// Inherit base as protected.
class derived : protected base {
    int k;
public:
// derived may access base's i and j and setij().
    void setk() { setij(10, 12); k = i * j; }
// may access showij() here
    void showall() { cout << k << " "; showij(); }
};

int main()
{
    derived ob;
//  ob.setij(2, 3); // illegal, setij() is
//                     protected member of derived
    ob.setk(); // OK, public member of derived
    ob.showall(); // OK, public member of derived
// ob.showij(); // illegal, showij() is protected
//                 member of derived
    return 0;
}

```

</details>

## Inheriting Multiple Base Classes

 It is possible for a derived class to inherit two or more base classes. For example, in this short example, derived inherits both base1 and base2.
<details>
  <summary> Code </summary>

  ```cpp
  #include <iostream>
using namespace std;

class base1 {
protected:
    int x;
public:
    void showx() { cout << x << "\n"; }
};

class base2 {
protected:
    int y;
public:
    void showy() {cout << y << "\n";}
};

// Inherit multiple base classes.
class derived: public base1, public base2 {
public:
    void set(int i, int j) { x = i; y = j; }
};

int main()
{
    derived ob;
    ob.set(10, 20); // provided by derived
    ob.showx(); // from base1
    ob.showy(); // from base2
    return 0;
}
```

</details>

## Constructors, Destructors, and Inheritance

## Constructors and Destructors

### Constructors

1. An object's constructor is automatically called when the object is created.
2. In C++, constructors cannot return values and, thus, have **no return type.**
3. An object's constructor is called once for global or static local objects

### Destructors

1. When an object is destroyed, its destructor (if it has one) is automatically called.
2. Local objects
 are created when their block is entered, and destroyed when the block is left. Global objects are destroyed when the program terminates.
3. The destructor has the same name as the constructor, but it is preceded by a ~.
4. like constructors, destructors do not have return values.

<details>
<summary> <b>Click</b> Build a stack using  Constructors and Destructors</summary>
<details>
  <summary> Code </summary>

</details>

```cpp
#include <iostream>
using namespace std;
#define SIZE 100

class stack {
    int stck[SIZE];
    int tos;
public:
    stack();  // constructor
    ~stack(); // destructor
    void push(int i);
    int pop();
};
// stack's constructor
stack::stack()
{
    tos = 0;
    cout << "Stack Initialized\n";
}
// stack's destructor
stack::~stack()
{
    cout << "Stack Destroyed\n";
}
void stack::push(int i)
{
    if (tos == SIZE) {
        cout << "Stack is full.\n";
        return;
    }
    stck[tos] = i;
    tos++;
}
int stack::pop()
{
    if (tos == 0) {
        cout << "Stack underflow.\n";
        return 0;
    }
    tos--;
    return stck[tos];
}
int main()
{
    stack a, b;  // create two stack objects
    a.push(1);
    b.push(2);
    a.push(3);
    b.push(4);
    cout << a.pop() << " ";
    cout << a.pop() << " ";
    cout << b.pop() << " ";
    cout << b.pop() << "\n";
}
```

</details>

Two mejor questions

1. when are base-class and derived-class constructors and
 destructors called?
2. how can parameters be passed to base-class constructors?

### When Constructors and Destructors Are Execute

lets see and example
<details>
  <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
class base {
public:
    base() { cout << "Constructing base\n"; }
    ~base() { cout << "Destructing base\n"; }
};
class derived: public base {
public:
    derived() { cout << "Constructing derived\n"; }
    ~derived() { cout << "Destructing derived\n"; }
};
int main()
{
    derived ob;
// do nothing but construct and destruct ob
    return 0;
}

```

</details>

<details>
  <summary> Output </summary>

```

 Constructing base
 Constructing derived
 Destructing derived
 Destructing base

 ```

</details>

**Anothe example**
 <details>
   <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
class base {
public:
    base() { cout << "Constructing base\n"; }
    ~base() { cout << "Destructing base\n"; }
};
class derived1 : public base {
public:
    derived1() { cout << "Constructing derived1\n"; }
    ~derived1() { cout << "Destructing derived1\n"; }
};
class derived2: public derived1 {
public:
    derived2() { cout << "Constructing derived2\n"; }
    ~derived2() { cout << "Destructing derived2\n"; }
};
int main()
{
    derived2 ob;
// construct and destruct ob
    return 0;
}

```

</details>

<details>
  <summary> Output </summary>

```

 Constructing base
 Constructing derived1
 Constructing derived2
 Destructing derived2
 Destructing derived1
 Destructing base

 ```

</details>

**Anothe example**
<details>
   <summary> Code </summary>

  ```cpp
  #include <iostream>
using namespace std;
class base1 {
public:
    base1() { cout << "Constructing base1\n"; }
    ~base1() { cout << "Destructing base1\n"; }
};
class base2 {
public:
    base2() { cout << "Constructing base2\n"; }
    ~base2() { cout << "Destructing base2\n"; }
};
class derived: public base1, public base2 {
public:
    derived() { cout << "Constructing derived\n"; }
    ~derived() { cout << "Destructing derived\n"; }
};
int main()
{
    derived ob;
// construct and destruct ob
    return 0;
}

```

</details>
<details>
  <summary> Output </summary>

```

 Constructing base1
 Constructing base2
 Constructing derived
 Destructing derived
 Destructing base2
 Destructing base1

 ```

</details>

**Anothe example**
<details>
  <summary> Code with output </summary>

```cpp
 class derived: public base2, public base1 
//  output
 Constructing base2
 Constructing base1
 Constructing derived
 Destructing derived
 Destructing base1
 Destructing base2
```

</details>

## Passing Parameters to Base-Class Constructors

- Form  the derived class's constructor declaration that passes along arguments to one or more base-class constructors.
- derived(int x, int y): base(y)

<details>
 <summary> Code </summary>

 ```cpp
# include<bits/stdc++.h>
using namespace std;

class base
{
protected:
    int i;
public:
    base(int x) {i = x; cout << "constructing base\n";}
    ~base() {cout << "Destructing base";}
};
class derived: public base
{
    int j;
public:
    derived(int x, int y): base(y)
    {
        j = x; cout << "Constructing derived\n";
    }
    ~derived() { cout << "Destructing derived\n"; }
    void show() { cout << i << " " << j << "\n"; }

};

int main() {

    derived ob(3, 4);
    ob.show();
    return 0;
}

```

</details>

- Two base class and one derived class

<details>
   <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class base1
{
protected:
    int i;
public:
    base1(int x) {i = x; cout << "constructing base 1\n";}
    ~base1() {cout << "Destructing base 1";}
};
class base2
{
protected:
    int k;
public:
    base2(int x) {k = x; cout << "constructing base 2\n";}
    ~base2() {cout << "Destructing base 2";}
};
class derived: public base1, public base2
{
    int j;
public:
    derived(int x, int y, int z): base1(y), base2(z)
    {
        j = x; cout << "Constructing derived\n";
    }
    ~derived() { cout << "Destructing derived\n"; }
    void show() { cout << i << " " << j << " " << k << "\n"; }

};

int main() {

    derived ob(3, 4, 5);
    ob.show();// display 4 3 5
    return 0;
}

```

</details>

Derived constructor uses no parameter, but still must be declared as taking them to pass them along to base classes.
<details>
   <summary> Code </summary>

 ```cpp
 #include <iostream>
using namespace std;
class base1 {
protected:
    int i;
public:
    base1(int x) { i = x; cout << "Constructing base1\n"; }
    ~base1() { cout << "Destructing base1\n"; }
};
class base2 {
protected:
    int k;
public:
    base2(int x) { k = x; cout << "Constructing base2\n"; }
    ~base2() { cout << "Destructing base2\n"; }
};
class derived: public base1, public base2 {
public:
    /*Derived constructor uses no parameter,
    but still must be declared as taking them to
    pass them along to base classes.
    */
    derived(int x, int y): base1(x), base2(y)
    { cout << "Constructing derived\n"; }
    ~derived() { cout << "Destructing derived\n"; }
    void show() { cout << i << " " << k << "\n"; }
};
int main()
{
    derived ob(3, 4);
    ob.show(); // displays 3 4
    return 0;
}

```

</details>

## Granting Access

 you might want to grant certain public members of the base class public status in the derived class even though the base class is inherited as private.

 ```cpp
 class base {
public:
    int j; // public in base
};
// Inherit base as private.
class derived: private base {
public:
// here is access declaration
    base::j; // make j public again
    .
    .
    .
};
```

<details>
 <summary> Code </summary>

 ```cpp
 #include<iostream>
using namespace std;

class base {
protected: int x;    // x is protected
};

class derived: private base {
public: base::x;     //demoting from protected to public must not happen
};

int main() {
    derived d1;
    d1.x = 10;          //protected variable x is being accessed using an object**
    cout << d1.x << endl;
}

```

</details>

Look at this example.
<details>
 <summary> Code </summary>

 ```cpp
 #include<iostream>
using namespace std;

class base {
protected: int x;    // x is protected
};

class derived: private base {
public:
    base::x;     //demoting from protected to public must not happen
};
class derived1: private derived {
public:
    derived::x;     //demoting from protected to public must not happen
};

int main() {
    derived1 d1;
    d1.x = 10;          //protected variable x is being accessed using an object**
    cout << d1.x << endl;
}

```

</details>

## Virtual Base Classes

![image](virtual-base-class.webp)
Lets take grand have an member and child want to access this member. So child can access this member through parent1 or parent. So compiler ambiguous shown here. where compiler confused about that which through this member should be access.
<details>
 <summary> Code </summary>

 ```cpp
 #include<iostream>
using namespace std;
class GrandParent
{
public:
    void print()
    {
        cout << "Hello" << endl;
    }
};
class Father : public GrandParent
{
};
class Mother : public GrandParent
{
};
//multiple inheritance
class Child : public Father, public Mother
{
};
int main()
{
    Child c;

    c.print(); // will generate error here
//print function is inherited two times from Grandparent via Father and mother both
//This causes ambiguity for the compiler

    return 0;
}

```

</details>

There are two ways to remedy the preceding program.

- apply the scope resolution operator
- virtual function

Using scope resolution operator
<details>
  <summary> Code </summary>

  ```cpp
  #include <iostream>
using namespace std;
class base {
public:
    int i;
};
// derived1 inherits base.
class derived1 :  public base {
public:
    int j;
};
// derived2 inherits base.
class derived2 : public base {
public:
    int k;
};
/* derived3 inherits both derived1 and derived2.
This means that there are two copies of base
in derived3! */
class derived3 : public derived1, public derived2 {
public:
    int sum;
};
int main()
{
    derived3 ob;
    ob.derived1::i = 10; // scope resolved, use derived1's i
    ob.j = 20;
    ob.k = 30;
// scope resolved
    ob.sum = ob.derived1::i + ob.j + ob.k;
// also resolved here
    cout << ob.derived1::i << " ";
    cout << ob.j << " " << ob.k << " ";
    cout << ob.sum;
    return 0;
}
```

</details>

Using virtual class
What if only one copy of base is actually required? Is there some way to prevent two copies from  being included in derived3? The answer, as you probably have guessed, is yes. This
 solution is achieved using virtual base classes.

When two or more objects are derived from a common base class, you can prevent
 multiple copies of the base class from being present in an object derived from those
 objects by declaring the base class as virtual when it is inherited.
<details>
 <summary> Code </summary>

 ```cpp
 #include<iostream>
using namespace std;

class GrandParent
{
public:
    void print()
    {
        cout << "Hello" << endl;
    }
};

class Father : virtual public GrandParent
{
//print function inherited from GrandParent
};

class Mother : virtual public GrandParent
{
//print function inherited from GrandParent
};

//multiple inheritance
class Child : public Father, public Mother
{
//print function only inherited once as both mother and father
//have virtual keywords before them

};

int main()
{
    Child c;

    c.print();
//No Ambiguity now

    return 0;
}

```

</details>

# Virtual Functions and Polymorphism

Polymorphism is supported by C++ both at compile time and at run time.

- compile-time polymorphism
  - Overloading functions
  - Overloading Operators
- Run-time polymorphism
  - Inheritance
  - Virtual functions

## Virtual Functions or virtual methods

When we try to access derived class member but the same name member also exist in base class then we can't  access derived class member function  **using base class pointer**. \
In simple When you refer to a derived class object using a pointer or a reference to the base class.
For solve this problem we use virtual functions.
<details>
 <summary> Code </summary>

 ```cpp
 #include<bits/stdc++.h>
using namespace std;

class base
{
public:

    virtual void print() {cout << "Print base class" << endl;}
    void show() { cout << "show base class\n"; }

};
class derived : public base {
public:
    void print() { cout << "print derived class\n"; }
    void show() { cout << "show derived class\n"; }
};

int main() {

    base *bptr;
    derived d;
    bptr = &d;

// Virtual function, binded at runtime
    bptr->print();

// Non-virtual function, binded at compile time
    bptr->show();

    return 0;
}

```

</details>

### Calling a Virtual Function Through a Base Class Reference

<details>
  <summary> Code </summary>

  ```cpp
#include <iostream>
using namespace std;
class base {
public:
    virtual void vfunc() {
        cout << "This is base's vfunc().\n";
    }
};
class derived1 : public base {
public:
    void vfunc() {
        cout << "This is derived1's vfunc().\n";
    }
};
class derived2 : public base {
public:
    void vfunc() {
        cout << "This is derived2's vfunc().\n";
    }
};
// Use a base class reference parameter.
void f(base &r) {
    r.vfunc();
}
int main()
{
    base b;
    derived1 d1;
    derived2 d2;
    f(b); // pass a base object to f()
    f(d1); // pass a derived1 object to f()
    f(d2); // pass a derived2 object to f()
    return 0;
}
```

</details>

### The Virtual Attribute Is Inherited

No matter how many times a virtual function is inherited, it remains virtual

### Virtual Functions Are Hierarchical

```cpp
class base {
public:
 virtual void vfunc() {
  cout << "This is base's vfunc().\n";
 }
};
class derived1 : public base {
public:
 void vfunc() {
  cout << "This is derived1's vfunc().\n";
 }
};
class derived2 : public base {
public:
 // LookHere
 // vfunc() not overridden by derived2, base's is used
};
```

## Pure Virtual Functions and Abstract Classes

- if a function doesn't have any use in the base class
- but the function must be implemented by all its derived classes

### abstract class

- An **abstract class** is a class in C++ which have at least one pure virtual function.
- We cannot create objects of an abstract class.
  
<details>
  <summary> Code </summary>
  
  ```cpp
// C++ program to calculate the area of a square and a circle

# include <iostream>
using namespace std;

// Abstract class
class Shape {
   protected:
    float dimension;

   public:
    void getDimension() {
        cin >> dimension;
    }

    // pure virtual Function
    virtual float calculateArea() = 0;
};

// Derived class
class Square : public Shape {
   public:
    float calculateArea() {
        return dimension * dimension;
    }
};

// Derived class
class Circle : public Shape {
   public:
    float calculateArea() {
        return 3.14 *dimension* dimension;
    }
};

int main() {
    Square square;
    Circle circle;

    cout << "Enter the length of the square: ";
    square.getDimension();
    cout << "Area of square: " << square.calculateArea() << endl;

    cout << "\nEnter radius of the circle: ";
    circle.getDimension();
    cout << "Area of circle: " << circle.calculateArea() << endl;

    return 0;
}

```

</details>

Some source where i collect code and ideas

# Collect resource

- Book ->C++: THE COMPLETE REFERENCE by Schildt, Herbert
- Fuad <https://github.com/fuad7161/Interview-Preparation/tree/main/OOP_in_C%2B%2B>
- <https://github.com/Devinterview-io/oop-interview-questions>
