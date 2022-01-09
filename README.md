# LLVM note
###### tags: `llvm`

## Environment
> ubuntu 21.10
> linux-5.14.15

## Installation
```bash
sudo apt install llvm clang -y
```

## Sample code
```c
// main.c
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int main() {
    int a = 1;
    int b = 2;
    printf("a = %d\n", a);
    printf("b = %d\n", b);

    int a_plus_b = add(a, b);
    printf("a + b = %d\n", a_plus_b);

    return 0;
}
```
### test
```bash
clang -S -emit-llvm main.c
lli main.ll
```

### compile
```bash
clang -emit-llvm -o main.bc -c main.c
clang -o main main.bc
````