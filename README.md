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

12a
```
#include <iostream>
using namespace std;

//defining the constructor outside the class
class student
{
    int rn;
    char n[50];
    float avg;
    public:
    student();
    void display();
};
student::student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void student::display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<endl;
}
int main()
{
    student s1;
    s1.display();
}
```

12b
```
#include <iostream>
using namespace std;

//types of constructor - default constructor
class student
{
    int rn;
    char n[50];
    double m1, m2, m3;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the subject 1 marks: ";
    cin>>m1;
    cout<<"Enter the subject 2 marks: ";
    cin>>m2;
    cout<<"Enter the subject 3 marks: ";
    cin>>m3;
}

void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Marks for subject 1: "<<m1<<endl;
    cout<<"Marks for subject 2: "<<m2<<endl;
    cout<<"Marks for subject 3: "<<m3<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}
```

12c
```
#include <iostream>
using namespace std;

//types of constructor - parameterized constructor
class maxop
{
    public:
    maxop(int a, int b)
{
    cout<<"First Number: "<<a<<endl;
    cout<<"Second Number: "<<b<<endl;
    cout<<endl;
    if (a>b)
    {
        cout<<"The first number is greater than the second.";
    }
    else if (b>a)
    {
        cout<<"The second number is greater than the first. ";
    }
    else
    {
        cout<<"Both numbers are equal. ";
    }
}
};

int main()
{
    maxop n1(23,76);
}
```

12d
```
#include<iostream>
#include<string.h>
using namespace std;

//types of constructors - copy constructor
class student
{
    int rn;
    char n[50];
    float avg = 0;
    public:
    student(int,char[],float);

    student(student &t)
    {
        rn=t.rn;
        strcpy(n,t.n);
        avg=t.avg;
    }
    void display();

};

 student::student(int rno,char na[],float av)
 {
    rn=rno;
    strcpy(n,na);
    avg=av;
 }

void student::display()
 {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<" %"<<endl;
 }

int main()
{
    student s1(36,"Lewis",93.7);
    s1.display();

    student lewis(s1);
    lewis.display();

    return 0;
}
```

12e
```
# include<iostream>
using namespace std;
int c = 0;
//using a destructor
class destruct
{
    public:
    destruct()
    {
        c++;
        cout<<"Number of objects created: "<<c<<endl;
    }
    ~destruct()
    {
        c--;
        cout<<"Number of objects destroyed: "<<c<<endl;
    }
};

int main()
{
    destruct aa,bb,cc,dd;
}
```

OUTPUT:-

12

![EX 12 JPG](https://github.com/user-attachments/assets/d6714061-72cf-4b60-9d7a-4356f57e8e42)

12a

![Ex 12a JPG](https://github.com/user-attachments/assets/defbd398-fea9-4d97-b651-2b775647939d)

12b

![Ex 12b JPG](https://github.com/user-attachments/assets/63a8c3c2-1a3b-4d4f-a4d1-d04cea56f507)

12c

![Ex 12c JPG](https://github.com/user-attachments/assets/e0824c30-eb52-4238-8c8d-acc597abf6f9)

12d

![Ex 12 d JPG](https://github.com/user-attachments/assets/569f473e-2b88-4afc-98d1-e58174d44370)

12e


![EX 12e JPG](https://github.com/user-attachments/assets/cb6d7310-00c8-4ec2-a3ea-c17c1426e1cc)










