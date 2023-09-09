---
tags:
  - Hackintosh 
  - Share
title: 1 tuần trải nghiệm Hackintosh - Phần 2
date: 2022-05-05
authors: [betty]
description: >
  1 tuần trải nghiệm Hackintosh - Phần 2
categories:
  - tech
links:
  - blog/posts/week-with-hackintosh-p1.md
---

[Phần 1](./week-with-hackintosh-p1.md)

Hihi, bẩu 1 tuần viết tiếp bài nữa về chủ đề này mà hoá ra thành cmn nó 3 tuần 🤣🤣. Chắc sẽ viết 1 bài tâm sự nhỉ. Nhưng mà giờ tập trung vào chủ đề **Hackintosh** nào.

Sau khi mất boot window thì mình buộc phải tìm cách để cài thêm window vào máy thôi. Mình chắc chắn học chương trình đại học như mình không thể bỏ window được (Ơ đổ cho đại học là không đúng :v, thật ra mình vẫn muốn chơi game 😢). 
<!-- more -->

Thế là giờ có 2 cách:

+ Dual boot luôn từ mac os (tức là phân vùng rồi cài). Nhưng việc không thể merge phân vùng win vào mac được (mình chỉ mất boot thôi mà) nên thôi sang cách 2.
+ Chơi khô máu hẳn, tức là xoá tất, format lại luôn ổ cứng. Cài lại cả win lẫn mac luôn.

Mình cũng muốn làm vậy hơn, cái win mình sử dụng lúc đó là win11 bản dev, tù vãi chày. Mà theo mình còn bloat nữa, mình cũng định cài lại vào 1 một dịp nào rồi, nên giờ là chuẩn cmnl, và sẽ dùng win 10. Mac os thì giờ dễ hơn, không đáng lo nữa, mà biết đâu cài lại thì các lỗi post trước nêu lại fix được nhỉ. Hơn nữa, mình cũng có thể chia lại dung lượng phân cho 2 os. Vì mac sẽ là hđh chính nên nó sẽ xơi nhiều hơn 1 tẹo, chắc là 4-6.

Thế là làm thôi. Nhưng dễ quá thì lại không thích, mà mình thấy dễ, nên ông trời tự làm khó mình luôn :v, buổi sáng mai hôm ấy, trời mất cmn điện.

Vcl mất điện, thế là hổng có mạng, đành phải ra quán net vậy :v.

Ra làm cái bộ cài win do mình quyết định cài win trước. Trời ơi lại không có USB để boot (có 2 cái để hết trên thủ đô rồi) nên lại phải lọ mọ đi mua thêm 1 cái nữa (hình như mấy gần 2 lốp lận).

Làm bộ cái giờ cũng dễ, làm xong cái usb thì về. Giờ cái win dễ thật đấy, chả phải làm gì nhiều ngoài next next y như lúc tải app trên win luôn. 

Sau khá lâu mới về lại win 10 (mình dùng win 11, Linux rồi đến Mac là chính), công nhận đôi khi đơn giản, vuông vức cũng không tệ. Trải nghiệm mượt mà, không nóng máy còn ngon chán so với quả 11 nửa vời. Xong thì mình không vội vàng cái Mac ngay mà cũng muốn trải nghiệm lại 1 lúc :v. Thế là lại lọ mò tải 1 số app cần thiết, rồi setup các thứ như cho 1 developer xịn luôn, chắc là sẽ có 1 bài viết về cái này thôi.

Mình muốn nói đến mac kìa, cơ bản thì vẫn thế, chả khác gì, vẫn dùng Opencore, vẫn dùng cái bộ [efi chôm từ 1 repo](https://github.com/ZoR3oL/t490-hackintosh) trên github ấy. Nhưng cái mình muốn nói là: gần như các lỗi mình kể lần trước giờ lại fix được hết luôn, ảo thật đấyyyy.

+ Airdrop không chấp :v
+ Bluetooth ngon luôn, không vấn đề gì hết.
+ System preference cũng chả lag, kể cả setting cho Siri.
+ Google Chrome cũng không crash lúc đăng nhập vào account khác nữa.
+ Âm thanh thì lâu lâu sleep xong wake up lại vẫn bị rè rè, nhưng khắc phục được bằng cách restart `coreaudioid` mà không cần phải restart hẳn lại máy.

Vậy nên, gần như là perfect.
Mà perfect thật mà :v, giờ cái lap của mình chuẩn đét luôn, bộ nhớ phân chia hợp lý cho 2 hệ điều hành, window trông thế những nhanh, nhẹ, tối giản, vẫn đầy đủ tool cho dev mình cài. Mac thì dùng làm hđh sử dụng chính.

Mình cũng sẽ lên thêm 1 bài nữa về setting cơ bản lúc dùng Mac của mình, khá nhiều điều để nói đấy, sau đó là các app nữa :v. Ơ vậy viết xong bài này thấy có mấy bài liền cần phải viết rồi đấy nhỉ.

Thế thì lại hẹn tuần sau (hoặc ngày mai, hoặc 3 tuần nữa, ai mà biết được giờ :v)