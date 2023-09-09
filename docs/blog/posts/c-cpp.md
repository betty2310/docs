---
tags:
    - C & C++
title: Về gcc và g++
date: 2022-05-05
authors: [betty]
categories:
  - tech
---

Nếu tìm `man gcc` và `man g++`, bạn đều thấy đều trỏ về 1 page với tiêu đề:

!!! info
    gcc - GNU project C and C++ compiler
<!-- more -->

Vậy thì khác biệt ở 2 giữa chúng là gì? Cơ bản nhất, `gcc` sử dụng để biên dịch các file `.c`, ngược lại với `g++` sẽ biên dịch các file `.cpp`. Thực tế, có thể dùng cả 2 trình biên dịch cho cả 2 ngôn ngữ, tuy nhiên vẫn có sự khác biệt: `g++` nếu biên dịch file `c` sẽ vẫn coi nó là file `cpp` bình thường, còn `gcc` sẽ coi `c` và `cpp` là riêng biệt.

Ngoài ra, cái khác biệt nhất mà mình muốn đề cập đến:

| `gcc`                                                                                     | `g++`                   |
| ----------------------------------------------------------------------------------------- | ----------------------- |
| Using `g++` to link the object files, files automatically links in the std C++ libraries. | `gcc` does not do this. |

Ví dụ cho khác biệt trên là thư viện `math.h`, ví dụ với đoạn code `c` sau:

```c
#include <math.h>

int isPrime(int number) {
    if (number <= 1) {
        return 0;
    }
    double sqrtOfNumber = sqrt(number); 
    for (int i = 2; i < sqrtOfNumber; i++) {
        if (number % i == 0) {  
            return 0;
        }
    }
    return 1;
}
```

Sử dụng câu lệnh `gcc main.c -o main`, `gcc` sẽ vả vào mặt bạn với lỗi sau:

```bash
/usr/bin/ld: /tmp/cccVnyTo.o: in function `isPrime':
main.c:(.main+0x5a): undefined reference to `sqrt'
```

Tuy nhiên, nếu biên dịch lại với `g++`, vẫn câu lệnh có cú pháp trên: `g++ main.c -o main`, chương trình sẽ chạy ngon ơ. 

Khác biệt ở đây chính thư viện `math.h` không được link 1 cách tự động khi sử dụng `gcc`, ngược lại với `g++`. Nên nếu muốn sử dụng `gcc` để biên dịch, bạn cần thêm arg `-lm` để **l**ink các thư viện **m**aths. 

```bash
$ gcc main.c -o main -lm
```

### Bonus

Có thể coi `g++` tương đương với `gcc -xc++ -lstdc++ -shared-libgcc`.

### References

+ https://stackoverflow.com/questions/172587/what-is-the-difference-between-g-and-gcc
+ https://stackoverflow.com/questions/19372317/c-failing-to-compile-cant-find-math-h-functions
+ https://www.geeksforgeeks.org/difference-between-gcc-and-g/