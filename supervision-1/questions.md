# Programming in C and C++ Supervision 1 Questions


## Question 1

What is the difference between `'a'` and `"a"`? What is the memory representation of the values?

---

## Question 2

Will the following code terminate? Under which circumstances?

```c
char i, j; for (i = 0; i < 10, j != 5; i++, j++);
```

---
## Question 3

Write an implementation of bubble sort for a fixed array of **integers** (for example `int arr[] = {4, 2, 3, 1};`) in increasing order.

---
## Question 4

Write an implementation of bubble sort for a fixed array of **characters** (for example `char arr[] = {'b', 'c', 'e', 'a'};`) into lexicographical order.

---
## Question 5

Write a function definition which matches the declaration:

```c
int cntlower(char str[], unsigned int len)
```

The implementation should return the number of lower-case letters in a string `str` of length `len`.

---
## Question 6

Can we change `char str[]` to `const char str[]` in the previous question? What does the `const` operator mean for a variable?

---
## Question 7
Define a macro `SWAP(t,x,y)` that exchanges two arguments of type `t`.

---
## Question 8
Given the following code:

```c
int v[] = {0, 1, 2, 3, 4};
int i = 0;
SWAP(int, v[i++], v[4])
```

1. Does the macro work as expected?
2. How does the array look after executing the `SWAP`?
3. Is there any difference if we change the `SWAP(int, v[i++], v[4])` with `SWAP(int, v[++i], v[4])`?

---
## Question 9

Define a macro `SWAP(x,y)` that excanges two arguments of the same type **without using a temporary**.

---
## Question 10

If `p` is a pointer, what does `p[-2]` mean? When is this legal?

---
## Question 11

Write a string search function with a declaration of:

```c
char *strfind(const char *s, const char *f);
```

which returns a pointer to the first occurrence of the string `s` in the string `f` (and `NULL` otherwise).

---


## Question 12


Given the following code, we are interested on what values will be printed.


```c

// --- initialization ---
int struct_elements = 5;
int int_array[] = {0, 4, 8, 12, 16};
struct ex3 struct_array[struct_elements];

for (int idx = 0; idx < struct_elements; idx++) {
    struct_array[idx].vi = int_array[idx]/2;
    struct_array[idx].pi = &int_array[idx];
}

for (int idx = 0; idx < struct_elements; idx++) {
    printf("struct_array[%d].vi = %d  \n", idx, struct_array[idx].vi);
    printf("struct_array[%d].pi = %d  \n", idx, struct_array[idx].pi);
    printf("*struct_array[%d].pi = %d  \n", idx, *struct_array[idx].pi);
    printf("------------\n");
}

printf("\n\n\n");

struct ex3 *p;

p = struct_array;

// --- expressions to evaluate ---
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");

printf("++p->vi : %d\n", ++p->vi);
printf("++p->pi : %d\n", ++p->pi);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");

printf("p++->vi : %d\n", p++->vi);
printf("p++->pi : %d\n", p++->pi);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");

printf("*p->vi : %d\n", *p->vi);
printf("*p->pi : %d\n", *p->pi);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");    

printf("*p->vi++ : %d\n", *p->vi++);
printf("*p->pi++ : %d\n", *p->pi++);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");

printf("(*p->vi)++ : %d\n", (*p->vi)++);
printf("(*p->pi)++ : %d\n", (*p->pi)++);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");

printf("*p++->vi : %d\n", *p++->vi);
printf("*p++->pi : %d\n", *p++->pi);
printf("p->vi : %d\n", p->vi);
printf("p->pi : %d\n", p->pi);
printf("------------\n");


```

Examine the code. We are interested in the part after the `--- expressions to evaluate ---` comment:
1. Some of the `printf` expression are wrong. Figure out wich expressions are wrong.
2. Find out what the rest of the expression will print.

Mention any assumptions that you made.

---

## Question 13

Explain on which element do the pointers `pi` and `pli` point at the end of the following code:

```c
int arr[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 };
int *pi = &arr[0];
long *pli = &arr[0];

pi++;
pli++;
```

---

## Question 14

Write a program `calc` which evaluates a reverse Polish expression given on the command line; for example:

```bash
$ calc 2 3 4 + *
```

should print `14`.

---

## Question 15

Use function recursion to write an implementation of merge sort for a fixed **array** of integers. How much memory does your program use for an array of length `n`?
