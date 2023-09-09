---
tags:
    - Computer Architecture
title: Little endian và Big endian 
date: 2022-05-05
authors: [betty]
categories:
  - tech
---
<!-- more -->

## Về cái tiêu đề

* Cả Little endian và Big endian là các cách mà máy tính hiểu và cách thức đọc dữ liệu tư `input` của chúng ta. Bình thường ta hay đọc theo thứ tự từ trái sang phải, nhưng không phải máy tính nào cũng đọc giống thế cả, mà chúng cũng thích tự có cách đọc riêng cơ 🤣.
* Little endian hay Little-end, là cách đọc mà các byte ở vị trí nhỏ nhất (nôm na là lại đọc số  từ hàng đơn vị) sẽ được đọc trước. Điều ngược lại với Big endian - đọc các byte giống với con người.
* Lưu ý rằng sự khác biệt chỉ đến từ vị trí của các byte, còn thứ tự các bit trong 1 byte thì vẫn không đổi. Nên nếu dữ liệu chỉ gồm 1 byte, thì 2 kiến trúc này không có sự khác biệt. 
* Mình tìm hiểu được thì các chip [intel](https://en.wikipedia.org/wiki/Endianness#:~:text=However%2C%20as%20Intel%20was%20unable%20to%20deliver%20the%208008%20in%20time%2C%20Datapoint%20used%20a%20medium%20scale%20integration%20equivalent%2C%20but%20the%20little%2Dendianness%20was%20retained%20in%20most%20Intel%20designs%2C%20including%20the%20MCS%2D48%20and%20the%208086%20and%20its%20x86%20successors.) theo kiến trúc Little endian này. 

### Yeah!

Hôm nay là ngày đầu tiên quay lại trường học sau gần 11 tháng học off. Có khá nhiều cảm xúc đan xen :v, vui có mà buồn cũng có.
Nhưng giờ không phải là lúc để than thở bạn ơi! Từ giờ sẽ cố gắng rèn luyện thêm 1 thói quen nữa là viết blog về mỗi ngày nhé :v. 

## References

* https://en.wikipedia.org/wiki/Endianness
* https://viblo.asia/p/little-endian-vs-big-endian-E375z0pWZGW