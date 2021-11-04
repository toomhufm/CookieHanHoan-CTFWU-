# CookieHanHoan-CTFWU-
## Forensics 

### _Tên bài_ : Streamer ( 121 solves ) 

_Mô tả_ : Anh nghệ sĩ nhiều đam mê đang vớt rác bên tàu. Ta lang thang với bản vẽ đời ta tự tô màu.
Ô! Vớt được cái gì thú zị này!

![Đề bài cho chúng ta 1 file pcapng](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/Chall.png)

Đề bài cho chúng ta 1 file PCAPNG , nên mình sẽ sử dụng **Wireshark** để xử lý bài này. 

Đầu tiên mình kiểm tra phần Export Object thì thấy 1 file zip khả nghi tên là evilcontent.zip

![ExportObj](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/ExportObj.png)

Sau khi xuất ra và mở file này thì mình thấy file flag.txt, mình thử giải nén thì nó yêu cầu mật khẩu 

![Password](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/Password.png) 

**Nhưng mình làm gì có password :<**  
Nhắc đến password thì mình nhớ lại lúc nãy trong phần export object có 1 số file **Login** 

![Login](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/Login.png)

Follow TCP Stream thì mình tìm thấy dòng **username=travisscott&password=truongvinhcuc** 
![TCP](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/FollowTCP.png)

_Vậy là mình đã tìm thấy password rồi, nhập thử vô nào_ 
**Ting ting, đúng password rồi, giờ thì đọc file flag thôi* 

![Flag](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Picture/Flag.png)

____________________________________________________________________________________________________________

### _Tên bài_ : Audacity ( 143 solves )  
_Mô tả_ : Hazy gửi cho Gà một thông điệp bí mật, kèm một lời nhắn "Đừng vội vàng kết luận môt vấn đề, luôn phải để mắt thấy tai nghe" 

Bài cho chúng ta 1 file âm thanh, trong đề cho chúng ta 2 hint là sử dụng **Audacity** và **"Mắt thấy tai nghe"** , vậy mình mở Audacity lên thôi nào :> 

![Audacity](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Audacity/Audacity.png) 

Đây là 1 dạng bài khá quen thuộc, mình sẽ sử dụng chức năng view Spectrogram của âm thanh để xem có gì ở trong. 
Thoạt đầu thì khá là khó nhìn đúng không ? Mình chỉ nhìn được 1 phần của flag **Flag{No_Bull???_???_????er_001}** 

Nhưng mình có để ý tên file âm thanh là squitgeam.wav ( Điều này làm mình nhớ đến bộ phim Squid Game đang làm mưa làm gió ). May mắn thay là mình đã xem bộ phim này rồi :3 

Dựa vào tên của file và những phần có thể nhìn rõ trong Spectrogram mình có thể đoán được dòng chữ **No Bullets for player 001** 

_Nhận xét_ : Đây là một chall khá đơn giản và dễ đoán ra nếu như tiếng Anh của bạn tốt và bạn đã xem qua bộ phim Squid Game. Mình thấy nhiều bạn than nhìn căng cả mắt mới ra flag thì chắc là chưa xem phim rồi hehe 

____________________________________________________________________________________________________________

### _Tên bài_ : ExSeller ( 143 solves )  
_Mô tả_ : Để không bị Mèo nhòm ngó tệp tài liệu quan trọng. Gà nhanh tay đặt mật khẩu, nhưng lại vô tình quên mất. Làm thế nào bây giờ T_T 

Bài cho chúng ta 1 file Excel. Mở lên xem coi bên trong có gì nào 

![Excel](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Exceller/Excel.png) 

Ơ kìa , chả có gì bên trong cả :((( 

Vì bên trong chả có thông tin gì hữu ích nên mình sử dụng công cụ **Binwalk** để kiểm tra coi file Excel có giấu gì ở trong không 

![Binwalk](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Exceller/Binwalk.png)

Sau khi xài binwalk thì mình thấy ẩn trong file Excel này có kha nhiều tập tin, vì vậy mình sử dụng option *-e* để extract toàn bộ ra 

Mình lục xem ở trong các file này coi có gì hữu ích không thì phát hiện ra flag nằm ở trong file sharedStrings.xml 

![Flag](https://raw.githubusercontent.com/toomhufm/CookieHanHoan-CTFWU-/main/Exceller/Flag.png)


____________________________________________________________________________________________________________




