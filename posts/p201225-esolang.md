# Esolang

Trong một số dự án gần đây, tôi sử dụng Golang làm ngôn ngữ để viết
chương trình trên server. Thiệt tình, dù không thể phủ nhận sức mạnh
nó đem đến, tôi lại không ham cú pháp của nó một chút nào. Nó quái đản,
gai góc, kỳ cục, mỗi lần viết thấy rất bực. Nó làm tôi nhớ tới mấy lần
ghé mắt qua Xcode của anh đồng nghiệp, nhìn cái cách viết hàm của
Objective-C xong tự nhiên thấy tức cái mình hết sức.

Nhưng dù là Golang hay Objective-C thì cũng chỉ là hạng tép riu khi so
về độ khùng điên với một phân nhóm ngôn ngữ có tên là **esolang**.

Viết đầy đủ là **esoteric programming language**, tạm dịch ngôn ngữ
lập trình dị biệt, đây là một khái niệm nói về những ngôn ngữ lập trình
ra đời không nhằm mục đích viết ứng dụng thực tế. Người ta phát minh
ra một esolang có thể vì muốn thử nghiệm một ý tưởng mới trong kỹ thuật,
muốn làm cái gì đó lạ lùng khác người, hoặc đơn giản là cho vui.
Trong phần sau đây, tôi mời các bạn tham khảo một số đại diện tiêu biểu nhất.

## INTERCAL

> Tác giả: Don Woods & James M. Lyon

Có thể được xem như tằng tổ của người chơi hệ dị hợm, ra đời vào năm 1972,
tên đầy đủ của ngôn ngữ này là **Compiler Language With No Pronounceable
Acronym** (cắt nghĩa đùi: ngôn ngữ biên dịch không có cách viết tắt nào
có thể phát âm được) và rút gọn thành **INTERCAL**. Tôi biết bạn nghĩ gì.
Kệ nó đi.

Cú pháp của INTERCAL rất phức tạp và mang tính làm tình làm tội người sử dụng,
nên mạn phép chỉ kể vài đặc điểm nổi bật.

Chương trình sẽ gồm các câu lệnh bắt đầu với từ khoá `DO`, `PLEASE`, hoặc
`PLEASE DO`. Nếu muốn ghi comment thì dùng `DON'T` hoặc `PLEASE DO NOT`
nhưng nếu chạy lại chỗ đó thì nó không còn là comment nữa và sẽ thi hành
như bình thường. Nên để chắc chắn thì có thể ghi `PLEASE NOTE` thay vì
`PLEASE NOT`, gây ra lỗi cú pháp và trình dịch sẽ ngó lơ.

Trình biên dịch của INTERCAL có lẽ nên được gọi là "trình hách dịch". Nếu
mã lệnh có quá ít dòng xài từ khoá `PLEASE` thì sẽ bị coi là bất lịch sự
và bị trình biên dịch từ chối. Nhưng nếu xài quá nhiều thì sẽ bị coi là
thảo mai và cũng bị từ chối luôn. Ok chưa bạn ơi?

## FALSE

> Tác giả: Wouter van Oortmerssen

Ra đời vào năm 1993, với cái tên ám chỉ giá trị Boolean ưa thích của tác giả,
ngôn ngữ này tính ra cũng không quá hợm hĩnh so với người tiền nhiệm.
Nó chỉ khó đọc, chứ không khó ở.

Để lấy ví dụ, trước hết mời bạn xem đoạn mã giả trình bày hàm tính giai thừa:

```
func f(n) {
  if (n == 1)
    return 1;
  else
    return n * f(n - 1);
}
```

Không có gì cầu kỳ khó hiểu ha. Giờ nếu viết bằng ngôn ngữ FALSE,
đoạn chương trình trên sẽ trở thành như thế này:

```
[$1=$[\%1\]?~[$1-f;!*]?]f:
```

Khỏi phân tích nha. Muốn hiểu sao hiểu. Không hiểu cũng được.

À và có một sự thật thú vị là trình dịch của FALSE có kích thước chỉ
1024 bytes mà thôi.

## Befunge

> Tác giả: Chris Pressey

> Năm ra đời: 1993

Chương trình viết bằng **Befunge** có một bộ nhớ dạng stack (ngăn xếp,
dữ liệu đưa vào sau cùng sẽ được lấy ra đầu tiên). Mã lệnh không phải
là từng dòng như các ngôn ngữ bình thường mà tổ chức thành một bảng
hai chiều. Ở đó sẽ có một đầu đọc lệnh chạy tới ô nào thì thực hiện
lệnh tại ô đó. Bốn ký tự `<>^v` được dùng làm mũi tên định hướng cho
đầu đọc.

Ví dụ chương trình Hello World kinh điển viết theo cách tương đối đơn giản:

```
>              v
v  ,,,,,"Hello"<
>48*,          v
v,,,,,,"World!"<
>25*,@
```

Cách hiểu như sau:

* Đầu tiên là di chuyển qua phải.
* Sau đó đi xuống.
* Rồi qua trái.
* Lần được lưu các ký tự `o l l e H` vô stack.
* In ra các ký tự trong stack bằng lệnh dấu phẩy.
* Đi xuống.
* Qua phải.
* Nhập `4` và `8` vào stack.
* Lấy ra nhân để được 32 (tức là mã của ký tự khoảng trắng) rồi in ra.
* Đi xuống.
* Qua trái.
* Tiếp tục lưu và in chuỗi ký tự `World!`.
* Đi xuống.
* Qua phải.
* Lấy 2 * 5 = 10, là mã của ký tự xuống dòng. Xong in ra.
* Kết thúc chương trình bằng lệnh `@`.

Một phiên bản ngắn hơn chút đỉnh:

```
 >25*"!dlrow ,olleH":v
                  v:,_@
                  >  ^
```

Trên đây, lệnh hai chấm `:` nghĩa là duplicate phần tử mới nhất trên stack.
Còn lệnh gạch dưới `_` là rẽ nhánh, bằng cách pop phần tử mới nhất trên
stack ra và kiểm tra, nếu bằng 0 thì đi qua phải, khác 0 thì đi qua trái.
Rồi đó. Bạn hãy thử tự mình giải thích cách đoạn mã trên hoạt động nhé.

## brainfuck

> Tác giả: Urban Müller

> Năm ra đời: vẫn là 1993

Cái tên nói lên tất cả. Ngôn ngữ này được tạo ra chỉ nhằm một mục đích
tàn bạo là thông não cực mạnh cho người dùng.

Cú pháp của **brainfuck** chỉ gồm 8 lệnh có dạng ký tự. Chương trình cũng
có một đầu đọc lệnh chạy từ đầu tới cuối, nhưng là tuyến tính chứ không
tung hoành ngang dọc như Befunge. Ngoài ra, chương trình chứa một mảng
dữ liệu kiểu byte, truy cập bằng một con trỏ.

8 lệnh gồm:

* `>` đẩy con trỏ qua phải
* `<` đẩy con trỏ qua trái
* `+` cộng thêm 1 vào giá trị ở chỗ con trỏ
* `-` trừ đi 1 từ giá trị ở chỗ con trỏ
* `.` xuất giá trị ở chỗ trỏ ra dạng ký tự có mã tương ứng
* `,` nhập một ký tự, quy ra mã rồi gán vào chỗ con trỏ
* `[` nếu giá trị chỗ con trỏ khác 0 thì đi tiếp, bằng 0 thì nhảy
tới lệnh ] tương ứng
* `]` nếu giá trị chỗ con trỏ bằng 0 thì đi tiếp, khác 0 thì nhảy
ngược về lệnh [ tương ứng

Chương trình Hello World không thể loạn trí hơn:

```
++++++++++[>+++++++>++++++++++>+++<<<-]>++.>+.+++++++
 ..+++.>++.<<+++++++++++++++.>.+++.------.--------.>+.
```

Mặc dù cổ quái như vậy nhưng brainfuck là một trong những esolang được
quan tâm nhiều nhất trong giới, bởi tính đơn giản của tập lệnh và tính
độc đáo của thiết kế. Và nếu đủ kiên nhẫn, người ta vẫn có thể viết ra
các chương trình tính toán phức tạp. Rất nhiều esolang sau này chịu
ảnh hưởng của brainfuck, như cái cách mà ngôn ngữ C làm nền móng cho
các ngôn ngữ "phàm tục" khác.

Trình dịch của ngôn ngữ nhìn như hàng rào ấp chiến lược này có kích thước
chỉ 200 bytes.

## Whitespace

> Tác giả: Edwin Brady & Chris Morris

> Năm ra đời: 2002, ra mắt 2003

Trong lập trình, khoảng trắng thường không đóng vai trò gì quan trọng ngoài
việc định dạng mã nguồn cho ngay ngắn, tránh bị mấy ông senior ngồi review
xong chửi là "cái đồ viết code dơ dáy". Và nếu có coi qua Python, bạn biết
khoảng trắng có thêm công dụng tương tự dấu ngoặc `{ }` trong họ C.

Nhưng đã là gì so với **Whitespace**.

Trong ngôn ngữ này, chỉ có 3 ký tự được sử dụng: dấu khoẳng trắng (space),
dấu tab, dấu xuống dòng (line feed). Mọi nội dung khác đều được xem là
comment.

Chẳng hạn, chuỗi _space-space_ là lệnh push một số lên stack, chuỗi
_tab-space-space-space_ là lệnh cộng hai số trên stack. Số thì điền ở
dạng nhị phân, với _space_ là 0 và _tab_ là 1. Định ghi ví dụ Hello World
nhưng chắc các bạn sẽ không thấy gì nên thôi.

Không biết có ứng dụng nào thực tế hay không, nhưng có lẽ Whitespace sẽ
chấm dứt cuộc chiến space/tab trong giới lập trình. Bởi lẽ, chỉ được xài
có 3 ký tự thì cũng không thể nào kén cá chọn canh được.

## Piet

![Piet Program](p201225-esolang/Piet_Hello_World.gif)

[Ảnh lấy từ đây](http://www.retas.de/thomas/computer/programs/useless/piet/explain.html)

> Tác giả: David Morgan-Mar

Ngôn ngữ **Piet** lấy cảm hứng từ những bức tranh lập thể của họa sỹ
_Piet Mondrian_. Hình bạn vừa thấy ở trên chính là chương trình Hello World.
Ngạc nhiên chưa?

Mã lệnh Piet hoạt động trên một bức hình 2D với các ô màu khác nhau.
Đầu đọc lệnh di chuyển qua các ô màu và tính toán sự thay đổi về Hue
(màu) và Lightness (độ sáng tối) để đưa ra quyết định tương ứng. Hay ghê ha!

---

## Kết

Còn rất rất nhiều ngôn ngữ dị biệt khác mà tôi không thể kể ra hết trong
một bài viết thế này. Cho nên nếu cảm thấy hứng thú với _esolang_, các bạn
có thể bấm vô các đường dẫn tôi sẽ liệt kê bên dưới. Cảm ơn các bạn đã
ghé chơi. Chào thân ái và hẹn gặp lại.

### Tham khảo

* Trang wiki: https://en.wikipedia.org/wiki/Esoteric_programming_language
* Wiki riêng của họ hàng esolang: https://esolangs.org/wiki/Main_Page
* FALSE: http://strlen.com/false-language/
* Befunge: https://github.com/catseye/Befunge-93/blob/master/doc/Befunge-93.markdown
* Piet: https://www.dangermouse.net/esoteric/piet.html
