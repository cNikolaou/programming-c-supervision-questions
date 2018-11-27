# Programming in C and C++ Supervision 3 Questions


## Question 1

Consider the following C program:

```c
void swap(int x, inty) {
    int temp = x;
    x = y;
    y = temp;
}

int main(int argc, char **argv) {
    int x = 0;
    int y = 1;
    swap(x,y);
    assert(x == 1);
    return 0;
}
```

1. Explain what is the role of the `assert` statement and why will this program trigger the `assert`.

2. Provide two modified versions of the `swap` function:
    * One version should use the C language features.
    * The other version should use the C++ language features.

---

## Question 2

What is the value of `x` at the end of the `main` function:

```c
int x = 9;

void f() {
    ::x = 8;
}

int main() {
    f();
    return 0;
}
```

---

## Question 3

In the C language we can dynamically allocate memory space and then we need to deallocate that memory. For managing IO between programs and files we can use the following code:

```c
FILE *fp = fopen("input.txt", "w+");
// Read and write in the file
fclose(fp);
```

1. What makes this style of resource management problematic in C++? What can go wrong between creating the file pointer and deallocating the file pointer (which also closes the file).

2. Define a C++ class that acts as a wrapper around allocating and deallocating file pointers and solves the problem that the previous code sample has.

---

## Question 4

Why might it be useful to define a copy constructor for a C++ class? Give an example of a copy constructor for a simple class.

---

## Question 5

Why might it be useful to explicitly define the assignment operator (=) for a C++ class? Give an example definition of the assignment operator for a simple class.

---

## Question 6

Why a function might be declared virtual in a C++ superclass?

---

## Question 7

What is the difference between `malloc()` and `free()` versus `new` and `delete`?

---

## Question 8

Consider the following C function that receives a string as an argument and returns a reversed string as a result. The `strlen` function returns the number of the characters in the string, e.g. `strlen("hello")` returns `5`.

```c
#include <string.h>
#include <stdlib.h>

char *reverse(char *in_string) {
    int len = strlen(in_string);
    char out_string[len];
    for (int i = 0; i < len; ++i) {
        out_string[len - i - 1] =  in_string[i];
    }
    return out_string;
}
```


1. Identify three bugs with this function.

2. Write a correct version of this function.

---

## Question 9

Is there any error with `Base b;` and/or with `Base *bp;` in the `main` function?

```c
#include<iostream> 
using namespace std; 
  
class Base  { 
public: 
    virtual void show() = 0; 
}; 
  
int main() { 
    Base b; 
    Base *bp; 
    return 0; 
} 
```


---

## Question 10

Which constructors are called and in which order?

```c
#include<iostream> 
   
using namespace std; 
class Base1 { 
 public: 
    Base1() { 
         //constructor for Base1  
    } 
}; 
   
class Base2 { 
 public: 
    Base2() { 
        //constructor for Base2  
    } 
}; 
   
class Derived: public Base1, public Base2 { 
   public: 
    Derived() {  
        //constructor for Delivered  
    } 
}; 
   
int main() { 
   Derived d; 
   return 0; 
} 
```



---

## Question 11

Is there any problem with the following program?

```c
#include<iostream> 
using namespace std; 
  
int main() { 
    int *ptr = new int; 
    delete ptr; 
    delete ptr; 
    return 0; 
}
```

---

## Question 12

Is there any problem with the following program?

```c
#include <iostream> 
using namespace std; 
  
class Test { 
  int x; 
  Test() { x = 5;} 
}; 
  
int main() { 
   Test *t = new Test; 
   cout << t->x; 
}
```

---

## Question 13

What will the following program print?

```c
#include <iostream> 
using namespace std; 
  
template <typename T> 
void fun(const T&x) { 
    static int count = 0; 
    cout << "x = " << x << " count = " << count << endl; 
    ++count; 
    return; 
} 
  
int main() { 
    fun<int> (1);  
    cout << endl; 
    fun<int>(1);  
    cout << endl; 
    fun<double>(1.1); 
    cout << endl; 
    return 0; 
} 
```

---

## Question 14

Is the following program correct? If yes, what will it print? If no, why is it wrong?

```c
#include<iostream>
using namespace std;
 
class Base {
public:
    virtual void show() { 
        printf("In Base\n"); 
    }
};
 
class Derived: public Base {
public:
    void show() { 
        printf("In Derived\n"); 
    }
};
 
int main(void) {

    Derived d;
    d.show();

    Base *bp = new Derived;
    bp->show();
 
    Base &br = *bp;
    br.show();
 
    return 0;
}
```

---

## Question 15

Add a second parameter to the following template class and add one private member of that type. Then create an object of that class whith first type `int` and second type `double`. What is the size of the object in bytes?

```c
#include <iostream> 
using namespace std; 
  
template <typename T> 
class MyClass { 
    private:
        T x,y;
        static double d;
} 
  
int main() { 
    
    MyClass<int> obj = new MyClass<int>();

} 
```