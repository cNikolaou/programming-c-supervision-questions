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

    for (int i = 0; i < N; ++i) {
        cp[i] = '5';
        printf("%c\n", cp[i]);
    }

    for (int i = 0; i < N; ++i) {
        sp[i] = 10;
        printf("%d\n", sp[i]);
    }

    for (int i = 0; i < N; ++i) {
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
void foo() 
{ 
   int *ptr = (int *) malloc(sizeof(int)); 
  
   /* Do some work */
  
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
    1. What is the purpose of each variable?
    2. Can you provide a schematic of the logic behind the arena?
2. Is there any limitations with the implementation of the arena? If yes, then explain how you would fix it.

---
## Question 7

---
## Question 8

---
## Question 9