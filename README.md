# Experiment-12
Aim:
To study and implement constructors and destructors.

Theory:
Constructors:

Constructors are unique member functions of a class that are automatically called when an object of the class is created. The object’s data members are initialized. Resources may also be allocated when required.
There are some key points about costructors which are:
→ The name of the constructor is same as its class name.
→ Constructors do not have a return type.
→ Constructors are mostly declared in the public section of the class.
→ Multiple constructors can be defined with different parameters, this is known as overloading.

There are mainly 3 types of constructors. They are:
Default Constructor:
A constructor which takes no arguments. It is also called a zero-argument constructor as it has no parameters.
Parameterized Constructor:
A constructor that takes parameters, allowing the object to be initialized with specific values.
Copy Constructor:
A constructor that initializes an object using another object of the same class. It is used for deep copying and when passing objects by value.


Destructors
A destructor is a special member function which destroys the class objects created by the constructor. It has the same name as their class name preceded by a tilde (~) symbol. There are some key points about destructors which are:
→ They neither require any argument nor do they return any value.
→ They release memory space which are occupied by the objects created by the constructor.
→ Destructor cannot be overloaded.
→ Objects are destroyed in the reverse of an object creation.
→ Only one destructor can be defined.

CODE:-

12
```
#include <iostream>
using namespace std;

//defining constructor inside the class
class student
{
    int rn;
    char n[50];
    float avg = 0.0;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<"%"<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}
```
