---
tags:
  - Hackintosh 
  - Share
title: 1 tuần trải nghiệm Hackintosh - Phần 1
---

Đúng ra mình phải viết bài này từ hôm qua, thế mới tròn 1 tuần :v, nhưng hôm qua lại gặp vấn đề lớn mà mình sẽ đề cập ngay bên dưới, nên nay mới viết được. Thôi vào luôn chủ đề chính thôi. 

Hackintosh - hiểu đơn giản là cài hệ điều hành MacOS trên các máy tính không phải của Apple sản xuất. Ví dụ nhưng laptop Thinkpad nhưng lại chạy macOS này (như mình - mình đổi tên nó thành ThinkMac luôn :v). 

2 phần quan trọng nhất của hackintosh là kexts và bootloader. Kexts thì tương tự như drives trên window, còn bootloader thì để đương nhiên để boot lên thôi :v, nó còn như kiểu giúp đánh lừa macOS nhận diện (từ các kext trên) rằng ừ, đây là máy tính của apple này vậy, boot vào đi bạn eii.

Kiến thức cần và đủ để hackintosh được là tương đối nhiều. Bạn phải hiểu rõ về phần cứng máy tính (để xem liệu phần cứng này có tương thích hay không - dù sao thì ta cũng chỉ đang đánh lừa macOS thôi mà, kiểu gì chả có 1 số thứ không thể lừa nó được), phân vùng, EFI, bios, rồi thì kĩ năng bình tĩnh nếu không thành công, kĩ năng google sau khi bạn kiếm soát được bản thân không bực tức nữa khi gặp lỗi, ..... Nhiều thế, nhưng mình vẫn thành công mặc dù không biết gì hết :v.

### Trải nghiệm bản thân

Tuần trước (ngay sau cái bài đi [phỏng vấn](https://www.betty2310.rocks/everyday/04-23-2022-linh-tinh-l-n-u-i-ph-ng-v-n-) ấy) tối về mình khá chán, nên muốn làm gì đó mà mình vẫn luôn thích - đó là vọc vạch cái gì đó mới. Nghe đến hackintosh đã lâu, lại cũng thích cái sự đẹp với mượt của mac nữa. Nên dù chỉ biết có tý tẹo kiến thức về những cái mình nêu bên trên, nhưng mình vẫn liều 1 phen (khổ thân cái máy của tôi, trải qua biết bao nhiêu hệ điều hành rồi :v)

Sau khi biết 2 thứ quan trọng nhất để hackintosh là kexts và bootloader, mình cũng gặp may là phần cứng của chiếc máy mình sử dụng là Thinkpad t490 cũng tương thích gần như 100% rồi. Nên sau đó mình gõ ngay trên google "hackintosh thinkpadt490"! Có hết mọi thứ luôn :v, khá nhiều người đi trước rồi, và quan trọng nhất là bài viết này trên [Github](https://github.com/yusifsalam/t490-macos). Mọi thông tin cần thiết đều được chỉ rõ hết. Kext và các config liên quan đều đã được làm sẵn :v, chỉ việc bê về mà dùng. Nhưng mà tác giả dùng bản MacOS Bigsur, mình nghe giờ mới nhất là Monsterey cơ, nên cũng thử tìm xem có ai đã làm chưa (tham lam), ờ thì có [thật](https://github.com/ZoR3oL/t490-hackintosh) :v

Xong kexts với config rồi nhé, giờ chọn booloader thôi, theo link tác giả mình đề cập trên thì anh ấy sử dụng [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/) và có link [hướng dẫn](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html) luôn. Nên mình cũng làm theo, hướng dẫn chi tiết lắm, nên cắm cái USB vào rồi xắn tay gõ phím luôn. 

Việc duy nhất phải tự làm chắc là gen [SMBIOS](https://hackintosh.vn/huong-dan-cai-hackintosh#:~:text=%C4%90%E1%BA%B7c%20%C4%91i%E1%BB%83m%20c%E1%BB%A7a%20SMBIOS,v%C3%A0%20CPU%20c%E1%BB%A7a%20m%C3%ACnh.) cá nhân để sử dụng. Bao gồm MLB, serial và UUID. Công cụ sử dụng ở đây là [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS), sau khi lấy được cái key trên thì tự nhập vào file `config.plist` thôi.

Xong các bước trên là bạn có 1 cái flash usb để boot rồi, giờ đến phần quan trọng hơn nào :v.

### Boot 🚀🚀

Mình cũng boot hệ điều hành nhiều rồi, Window cài lại với 1 đống distro Linux. Cơ bản là mọi việc cũng khá dễ, lần này mình nghĩ cùng vậy thôi. 

Cơ mà lúc đầu mình vẫn nhớ là lắm lỗi lắm, không thể nhớ chính xác là gì, nhưng đại khái chính là liên quan đến cái SMBIOS và các key liên quan đề cập trên kìa. Nên là phải gen ra rồi điền cho đúng nhớ :v. 

Sau đó thì đúng quy trình, mỗi tội hơi lâu, chắc phải cả 2-3 tiếng mới xong. 

Lúc xong rồi thì sướng thật, được trải nghiệm MacOS lổi tiếng về UI/UX với mượt thì thôi rồi :v, nhưng mình vẫn phải test xem có phần nào không hoạt động không, thì thấy có:

+ Bluetooth - khá bất ngờ, vì theo link github thì pass 100% :v.

+ Airdrop - chắc chắn là tạch!

+ Phần system preference khá lag, một số mục thì sau khi sleep xong vào lại không được (báo lỗi), restart lại là được.

+ Cũng liên quan đến việc sau sleep, đó là nếu vẫn cắm tai nghe và sau đó wake up, âm thanh lúc này khá lạ, không biết nói sao nữa :v

+ Lạ nhất phải là cứ lên Google Chrome đăng nhập account khác là lag, crash cmn cả chrome. 

Nhưng mấy cái trên không ảnh hưởng nhiều lắm :v, wifi, trackpad, bàn phím là đủ rồi, âm thanh thì reset lại card là ổn, nên về cơ bản là tạm hài lòng với thời gian bỏ ra.

Sau đó là phần mount efi từ USB về disk để lần sau boot không cần USB mồi nữa. Đến đây mới ối zời ôi, mình copy thẳng tay file EFI từ usb ra disk, nó ghi đè lên file efi sẵn ở đây (nhưng mình quên là trong máy mình còn Window cơ mà - mình tính dùng song song cơ mà) thế là mất luôn boot của window, chỉ còn Mac :v. Mình định cuối tuần nghỉ 30-4 và 1-5 sẽ xử lý vần đế này. 

Tức là hôm qua đấy, nhưng thôi bài dài lắm rồi, để mai viết tiếp phần 2 vậy.

### References

+ [Making the installer in Windows | OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html)

+ [GitHub - ZoR3oL/t490-hackintosh: This repo contains files needed to &quot;Hackintosh&quot; your Lenovo T490.](https://github.com/ZoR3oL/t490-hackintosh)

+ [GitHub - yusifsalam/t490-macos: Lenovo T490 running macOS Big Sur using OpenCore](https://github.com/yusifsalam/t490-macos)

+ [GitHub - corpnewt/GenSMBIOS: Py script that uses acidanthera&#39;s macserial to generate SMBIOS and optionally saves them to a plist.](https://github.com/corpnewt/GenSMBIOS)