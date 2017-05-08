# Kẻ thù lớn nhất của lập trình viên

_Bài gốc của **Jeff Wofford**: [A Programmer's Greatest
Enemy](http://www.jeffwofford.com/?p=835)_

Kẻ thù lớn nhất của lập trình viên là sự bế tắc. Cái kỹ năng quan trọng nhất khi
lập trình – mà nhiều sinh viên nhập môn thường thiếu sót – là khả năng nhận ra
lúc nào mình bế tắc, làm sao ra khỏi bế tắc và tránh để xảy ra bế tắc.

Thật ra chính tôi cũng đang phải học kỹ năng đó, dù rằng qua thời gian, qua học
tập và kinh nghiệm thì tôi đã dần bớt gặp phải bế tắc rồi.

Hồi sáng, tôi tải về một bản báo lỗi sụp chương trình từ Apple, và tự nhiên thấy
ngán cái công việc bữa nay tôi phải làm. Thành ra tôi bắt đầu kiếm chuyện khác –
như coi thư từ, đọc tin tức – bất cứ thứ gì giúp cho tôi né cái mà tôi thấy hẳn
là một buổi lập trình chán ngắt.

Tôi tự hỏi là chính xác thì tôi đang ngán cái gì, và một lúc sau tôi mới nhận
ra. Câu trả lời chính là bị bế tắc.

Tôi không chán việc sửa lỗi chương trình. Tôi cũng không ớn mấy cái lỗi. Thường
thường tôi thấy những cái lỗi gây sụp chương trình còn dễ sửa hơn là bộ nhớ bị
rò rỉ hoặc các biến chưa khởi tạo. Khi chương trình sụp thì ít ra bạn còn biết
phải xem xét chỗ nào: ngay tại nơi mà bản báo lỗi đã chỉ ra.

À mà lại nói tới mấy cái bản báo lỗi phiền phức ấy. Chúng là ngọn nguồn nỗi sợ
của tôi. Bạn thấy đó, hồi đó tôi coi các báo cáo sụp chương trình để chẩn lỗi,
nhưng không phải là mấy cái từ Apple và không bao giờ từ Xcode. Vậy thì coi mấy
cái báo cáo này sẽ giúp được gì? Tôi có thể thẩy nó vô Xcode đặng nó chỉ cho tôi
cái mã nguồn hay tôi lại phải cặm cụi đọc hết báo cáo và tự mò mẫm phân tích nó
đây? Nó có giúp cho tôi tìm ra ngay cái chỗ gây sụp không?

Một phần vấn đề này là bản báo cáo không có những danh biểu chẩn lỗi (tên biến,
tên hàm, v.v. – ND). Tôi có thể thấy được module nào gây lỗi, nhưng ngoài ra thì
chỉ có toàn địa chỉ byte – không có tên tập tin mã nguồn, càng không có số dòng.
Cho nên để xài được bản báo cáo thì tôi phải kiếm cái tập tin .dSYM liên quan
tới phiên bản chương trình đã gây lỗi, và (bằng cách nào đó) móc nối nó với bản
báo cáo. Nhưng làm sao tôi “móc nối” nó bây giờ? Và thậm chí tôi có còn giữ tập
tin đó không?

Tất cả những ý niệm này hoàn toàn theo trực giác, và chúng cứ ám ảnh tôi khi tôi
duyệt qua các bản báo cáo lỗi. Chỉ khi tôi ngừng lại và suy nghĩ thì tôi mới
chợt nhận ra rằng, tôi đang ớn óc việc lập trình trong buổi sáng này do tôi sợ
bị bế tắc.

Rủi cái việc móc nối danh biểu vào bản báo lỗi nó lại quá phức tạp và rắc rối
thì sao? Tôi sẽ phải mất mấy tiếng đồng hồ đọc tài liệu hướng dẫn và lục tung
các diễn đàn đặng tìm cho ra cách liên kết danh biểu với bản báo lỗi. Nghe thì
có vẻ buồn cười, nhưng mà nhiều lúc mấy chuyện lặt vặt này lại lố bịch như thế.
Cứ hỏi bất cứ ai đã từng kiếm cách đăng ký chứng thực mã trên iOS trong thời
gian trước là biết. Tôi ghét phải đọc tài liệu hướng dẫn và đào bới trong mấy
cái diễn đàn chẳng mấy liên quan để tìm phương cách giải quyết những rào cản ngớ
ngẩn. Tôi sợ là sợ cái đó.

Thậm chí tệ hơn nữa, rủi tôi không còn giữ mấy tập tin .dSYM thì sao? Làm thế
nào tôi coi được bản báo lỗi mà không biết tên biến? Có lẽ chúng còn lưu trong
gói chương trình chăng? Còn không, có lẽ tôi đã sao lưu chúng bằng Time Machine.
Nhưng lỡ như tôi không có sao lưu, lỡ như tôi phải tự mình phân tích bản báo
lỗi, không có tên biến nên sẽ phải coi địa chỉ bộ nhớ? Bỏ xừ! Sắp chán chết tới
nơi rồi!

Tôi biết là chuyện này nghe phát rầu. Đúng vậy. Nhưng tôi rên rỉ cả buổi sáng
nay chỉ là để minh họa về một lối suy nghĩ mà tất cả lập trình viên nhiều lúc sẽ
gặp phải.

Sau mấy năm kinh nghiệm làm lập trình viên trưởng và dạy môn lập trình, tôi đúc
kết được rằng khi một người thảo chương đang phải vật lộn thực sự – khi năng
suất của họ tụt xuống đáy và ngày qua ngày chẳng mần ăn được gì – nỗi sợ sẽ xuất
hiện. Lập trình viên đó đang bế tắc. Và nếu họ bế tắc thường xuyên thì sớm muộn
họ sẽ bị buộc bái-bai công việc của mình.

Hồi tôi mới có công việc thực thụ về lập trình game ở Origin Systems khoảng năm
1995, tôi quen được một lập trình viên đã làm trong công ty đó mấy năm. Ổng là
một người rất tốt bụng và đối đãi với tôi khá tử tế khi tôi chân ướt chân ráo
vào nghề làm game. Tôi khoái ông ta, nhưng sau khi vô mần được vài tuần thì ổng
thú nhận với tôi là ổng đang đánh vật với đống mã. Ông ta vừa phải ngưng lập
trình C, mà C++ ổng lại chẳng hiểu gì. Công ty thì đang chuyển qua lập trình
hướng đối tượng nên ổng theo không kịp. Mặc dù khi ấy tôi là tay mơ nhưng tôi đã
học C++ trong trường nên tôi hiểu về nó khá rõ. Thành thử tôi giải nghĩa cho ổng
nghe về OOP, chỉ cho ổng thấy vì sao C++ ngon hơn C, và giúp ổng “hiện đại hóa”.

Lúc bấy giờ tôi không nhận ra là việc ấy đã quá muộn màng. Ông ta hiểu được
những khái niệm mà tôi đã chỉ dạy. Nhưng sự tự tin của ổng thì không ổn rồi. Cứ
mỗi khi họp nhóm là ổng lại đưa ra một lý do vì sao cả tuần chưa làm được gì.
“Tôi gặp một cái lỗi khủng khiếp, mất mấy bữa mới dò ra. Đúng là giết người
thiệt. Tony có giúp tôi tìm nó, còn nhớ chứ hả Tony?” (Tony trông không mấy tin
tưởng) “Ờ phải, đúng là giết người thiệt.” “Rồi tôi lại phải giúp một nhóm khác
làm cái trình cài đặt, rồi tôi lại mắc vài chuyện trong cuộc họp của ban thiết
kế…” Ông ta có đủ các thể loại công chuyện hay ho mà ổng đã làm trong tuần,
nhưng không cái nào giúp ổng hoàn thành việc được giao.

Từ đó tới giờ tôi thấy cả ngàn trường hợp như vậy. Ôi dào, chính tôi còn làm vậy
nhiều hơn số lần tôi dám thừa nhận. Vô họp và viện lý do hay ho.

Chỉ hai tháng sau – tức là vài tháng từ lúc tôi đi làm – cái ông lập trình đó bị
đuổi việc. Tôi hết hồn – không có gì trong công việc mà dễ sợ hơn lần đầu bạn
nghe tin ai đó bị tống cổ. Nó giống như là chứng kiến cái chết. Bạn cứ có cảm
tưởng như mình mới né được làn đạn – mất việc chẳng bao giờ hay ho.

“Ổng chẳng mần ăn được gì cả,” người ta nói vậy khi tôi hỏi tại sao họ đuổi ổng.
“Ổng không hoàn thành được công việc.” Ông ta bị bế tắc thực sự, và đã không kịp
thời thoát khỏi tình trạng đó.

Thường thì sự bế tắc không đến nỗi tệ như vậy. Phần lớn chỉ là chuyện nửa ngày
hoặc một ngày – có thể là vài ba ngày né cặp mắt theo dõi của ông sếp và chơi
vài màn Robot Unicorn Attack trong khi đúng ra bạn đang phải gõ code. Nhưng dù
sao thì vẫn rất khó chịu khi chỉ lượn tới lượn lui, không thể làm công chuyện mà
bạn (thường) yêu thích, chỉ vì bạn không tài nào tìm ra cách tiếp tục. Dù lớn
hay nhỏ, sự bế tắc vẫn khiến bạn buồn phiền.

Kẻ thù lớn nhất của một lập trình viên không phải là bộ công cụ, hay ông sếp,
hay mấy tay đồ họa, hay bản thiết kế, hay mã hợp chuẩn, hay mã của third party,
hay API, hay hệ điều hành. Kẻ thù lớn nhất của lập trình viên là sự bế tắc.

Vậy nên, một bước quan trọng trong việc trở thành một lập trình viên giỏi hơn là
học cách làm sao tránh được bế tắc, nhận ra bạn đang bế tắc và thoát ra khỏi nó.
Bài viết tiếp theo sẽ nói rõ về chuyện này.