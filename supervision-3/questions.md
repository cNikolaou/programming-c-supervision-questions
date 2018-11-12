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



---

## Question 5

---

## Question 6

---

## Question 7

---

## Question 8

---