# Programming in C and C++ Supervision 2 Questions


## Question 1
Explain what (and why) will be the value of `i` after executing each of the following commands:

```c
i = sizeof(char);

i = sizeof(int);

int a; i = sizeof a;

char b[5]; i = sizeof(b);

char *c = b; i = sizeof(c);

struct { int d; char e;} s; i = sizeof(s);

void f(int j[5]) { i = sizeof(j); }

void f(int j[][10]) { i = sizeof(j); }
```
---

## Question 2

In the following code we would like to set a value for the variable `N`. Find the maximum possible value that we can set for `N`. How did you make the particular choice? Explain any assumptions that you might have made.

```c
#include <stdio.h>
#include <stdlib.h>
#include <limits.h>

int main() {

    int N = 0; // Change the value of N

    void *array = malloc(34);

    char *cp = &array[0];
    short *sp = &array[0];
    long *lp = &array[0];

    for (int i = 0; i != N; ++i) {
        cp[i] = '5';
        printf("%c\n", cp[i]);
    }

    for (int i = 0; i != N; ++i) {
        sp[i] = 10;
        printf("%d\n", sp[i]);
    }

    for (int i = 0; i != N; ++i) {
        lp[i] = 15;
        printf("%ld\n", lp[i]);
    }

}
```

---

## Question 3

In the code given in the previous question what will happen if:

1. We set `int N = MAX_INT` ? Do you think this is a bug?

2. We set `int N = -1` ? Do you think this is a bug?

3. If you think that these values for `N` are problematic, is there any way to debug the program in each case?

---
## Question 4

Are there any problems with the following function? How can we find out?

```c
int16_t divide(int32_t a, int32_t b) {

    return a / b;

}
```

---


## Question 5

Are there any problems with the following function? How can we find out?

```c
void foo() { 
   int *ptr = (int *) malloc(sizeof(int)); 
  
   *ptr = 10;

   printf("%d", *ptr * 2);
  
   return;
} 
```

---

## Question 6

You are given the following implementation of the arena:

```c
typedef struct node Tree;
struct node {
    int value;
    struct node *left;
    struct node *right;
};

typedef struct arena *arena_t;
struct arena {
    int size;
    int current;
    Tree *elts;
};
```

1. Explain simply how the arena works. Also:

    a. What is the purpose of each variable?

    b. Can you provide a schematic of the logic behind the arena?

2. Is there any limitations with the implementation of the arena? If yes, then explain how you would fix it.

---
## Question 7
What will the following C program print?

```c

void fun(int y) {
    static int x = 2;
    x++;
    printf("%d\n", y + x);
}

int main() {

    fun(4);
    fun(2);

}
```

---
## Question 8
What does the following program do?

```c
struct my_vector{
    int x, y;
} vec;

int *get_x()
{
    return &vec.x;
}

int main() {

    int vector_point = get_x();
}

```

---
## Question 9
What will be the value of `x`, `y`, `z`, `i` at the end of the `main()` function (where the comment is)?

```c
int main() {

    int x = 0; 
    int y = 10;
    int i = 0;

    {
        for (; i < 10; i++) {
            x += y;
        }
        int z = x + y;
    }

    // What is the value of x, y, z, i
}
```


---
## Question 10
A file named `in.txt` contains the following entries:

```
5
15 21
6 24 11
1
2 5
```

Write a C program that:
1. Reads the numbers from the file `in.txt`
2. Sorts the numbers into ascending order
3. Writes the numbers into another file called `out.txt`

---
## Question 11

In C++ there is container called `vector` which works as a dynamically allocated array. In this excercise we would like to implement it's two basic functionalities `push_back()`, which takes a value and places it at the end of the container, and `pop_back()`, which removes (and returns) the last value of the container. We are going to do that in C.

You are given the structure:

```c
struct my_vec {
    int *array;
    // you can add more varibles that will help you to anser the question
};

typedef struct my_vec vec;
```

Implement the two functions:

1. `void push_back(int value, vec *v)` which gets a value and places it at the end of the container. If the container is full then it needs to reallocate memory to be able to hold twice as much data. This is done to avoid reallocating everytime a new element is pushed back.

2. `int pop_back(vec *v)` which erases the last value from the container and returns the value. If, after removing the value, less than half of the allocated size for the array is used then reallocate the pointer to reduce the amount of memory used.

You will need to:

* Take care of initialiseing the pointer of the container `int *array` in order to hold the first value.
* Use additional variables within the structure to keep track of the state of the container.

---
## Question 12
Is there any bug in any of the following programs?

Program 1:
```c
int main()
{
    char hello[] = "hello";
    char *hp = hello;
}
```

Program 2:

```c
int main()
{
    char hello[6];
    char *hp = "hello";
    hello = hp;
}
```

---
## Question 13
What is the value of `i` on `Position 1` and on `Position 2`?


```c
int main() {
    int i = 0;
    
    {
        int i = 1;

        for (int i = 2; i < 5; ++i) {
            
            // do something
        }

        // Position 1
    }
    
    // Position 2
}
```