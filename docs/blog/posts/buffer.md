---
tags:
    - Computer Architecture 
title: Keyboard Buffer
date: 2022-05-05
authors: [betty]
categories:
  - tech
--- 

1 vài khái niệm cái nhể :grin:
<!-- more -->

!!! notes
    === "Buffer"
        Một vùng đệm, something like một vùng ảo, temp :v. 

    === "Keyboard buffer"
        Khi ta tương tác với bàn phím, những phím mình gõ không được gửi thẳng trực tiếp đến bộ xử lý của máy tính ngay, mà nó được gửi vào 1 vùng buffer để lưu giữ các keystrokes này lại, sau 1 số bước xử lý mới send vào cpu. Vùng buffer nằm trên RAM, dung lượng rất nhỏ.


### Yeah what it do and why exits?

Vậy thì mình tự hỏi, sao phải vẽ ra cái buffer này để làm gì nhỉ? Trước hết thì:

+ Giúp mình có thể control được các tổ hợp phím. Giả sử như `control + shift + Esc` để mở Task manager (trên Window) chẳng hạn. Buffer cho cpu 1 quãng nghỉ để đợi các chuỗi phím được hoàn thành hết, rồi mới xử lý. 
+ Lỡ đâu mình bấm nhanh quá, Cpu còn không kịp xử lý mình bấm cái gì thì sao :v, buffer cũng giải quyết vấn đề này. 
+ Mình nghĩ được thế này thôi :((.

### Buffer in Programming language

Trong ngôn ngữ `C`, sử dụng các hàm đọc dữ liệu từ bàn phím như `scanf` , tưởng rằng như nó đọc trực tiếp: ta bấm gì thì nó đọc đấy, nhưng thật ra nó chỉ đọc qua buffer mà thôi.
Việc kiểm soát các ký tự trong buffer lúc này rất là important, giả sử như các phím ta bấm nhưng `scanf` không đọc hết, nó sẽ còn thừa 1 số kí tự trong buffer, và sẽ ảnh hưởng đến các lần đọc input từ bàn phím tiếp theo.

Xét 1 cái ví dụ nhỉ. 1 đoạn code `C` như sau:

```c++
int n;
scanf("%d" &n);
char c;
getchar(c);
```

Mình nghĩ `c` sẽ có giá trị là gì?
Khi nhập giá trị cho `n`, đúng như những gì ta gõ trên bàn phím, sẽ là 1 loạt các số (muốn gán cho `n`) và phím `Enter` nữa :v. Vậy trong buffer bây giờ ta có các số và `\n` ở cuối buffer. Hàm `scanf` với format `%d` sẽ đọc các số và dừng lại khi gặp ký tự `\n` (see [**Whitespace character**](https://www.cplusplus.com/reference/cstdio/scanf/)). Vậy lúc này trong buffer còn 1 ký tự là `\n`. Tiếp theo là `getchar()`, tưởng rằng ta sẽ lại nhập 1 ký tự từ bàn phím và gán nó cho biến `c`. Nhưng `getChar()` đọc 1 ký tự từ buffer, và đó là `\n`, nên nó đọc và gán luôn giá trị này cho `c`, đến đây dễ thấy ta đã gặp lỗi. 

Nhớ chú ý vấn đề này nha.

### Vễ dữ liệu đầu vào, đầu ra và virus, hack.

Như 1 [thầy giáo](https://soict.hust.edu.vn/ths-nguyen-duc-tien.html) mà mình yêu quí đề cập trong giờ học. Các thiết bị như bàn phím, máy in, máy đọc vân tay hay QR đưa dữ liệu mà chúng đọc được vào máy tính chả khác gì nhau cả, hãy đều coi chúng là 1 cái bàn phím và ta đều dùng hàm `scanf()` để đọc dữ liệu từ chúng. 
Vậy thì hãy hiểu rõ việc control buffer này. Nó như 1 cửa ngõ để chui vào cpu. Và các virus hay hacker sẽ luôn muốn phá cái cửa ngõ này để hack máy tính của chúng ta (giống việc lan truyền covid 19 ở cái cửa ra vào lớp :v).