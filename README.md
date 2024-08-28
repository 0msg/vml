# vml
SIMD-accelerated Vector Math Library
### Prerequisites
+ [nasm](https://www.nasm.us "Nasm project page") (>= 2.15)

### Building
```bash
make
```
### Usage
```C
#include <stdio.h>
#include <stdlib.h>

#include "vml.h"

int main(int argc, char** argv) {
    float v1[] = {1, 3, 5, 7, 9};
    float v2[] = {2, 4, 6, 8, 10};
    float result[5];

    unsigned int size = sizeof(v1)/sizeof(float);
    
    _vec_add(result, v1, v2, size);
 
    for (int i = 0; i < size; i++) {
        printf("%f\n", result[i]);
    }

    return 0;
}
```
```bash
➜  vml git:(main) ✗ ./main 
3.000000
7.000000
11.000000
15.000000
19.000000
```

