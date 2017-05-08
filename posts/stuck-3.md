# Giữ nhịp tiến bước

_Bài gốc của **Jeff Wofford**: [Keep Taking Steps
Forward](http://www.jeffwofford.com/?p=843)_

Trong hai bài trước, tôi có bàn về kẻ thù số một của người lập trình: sự bế tắc.
Tôi đã nói về các mức độ bế tắc mà bạn có thể mắc phải, từ việc hì hụi đọc tài
liệu cho tới thiếu tập tin, mất mật mã nên không làm việc được.

Điều này đưa đến lời khuyến nghị tối hậu của tôi về cách làm sao tránh được sự
bế tắc và làm sao thoát khỏi nó.

Bí quyết để vượt qua bế tắc là giữ được nhịp độ tiến về phía trước. Nghe thì có
vẻ đơn giản nhưng ít có lập trình viên nào đạt tới cảnh giới này.

Để giữ nhịp tiến về phía trước thì đầu tiên phải biết tiến về phía trước nghĩa
là sao. Bạn đang cố gắng thực hiện việc gì? Công việc thật sự của bạn là gì?
Đáng buồn là lập trình viên thường mắc kẹt trong những việc đúng ra không phải
việc họ cần làm hoặc việc không đáng làm khi ấy. Khi bạn truy lùng một cái lỗi
trong một công cụ dùng để giúp tối ưu hóa một lớp bạn đang sửa chữa để giải
quyết lời than phiền từ người dùng, bạn dễ quên rằng lời than phiền từ người
dùng mới chính là việc bạn thực sự cần chú ý, chứ không phải lỗi trong công cụ
kia.

Từ các quan sát của tôi thì nhìn chung lập trình viên chúng ta ưa bị ám ảnh. Ta
thường thích đào sâu vào tận gốc rễ của mọi thứ. Và ta có khuynh hướng xao
nhãng, mê đắm với mấy điểm ảnh xinh xinh trên màn hình, những trở ngại phiền
toái, những vấn đề thách thức xảy đến trong khi lập trình. Rất mau sau đó, chúng
ta vò đầu bứt tóc chỉ vì những rắc rối chẳng mấy liên quan.

Chuyện này xảy ra với tôi khi tôi xài chương trình _awk_. Awk là một ngôn ngữ lập
trình nho nhỏ giúp người ta xử lý chuỗi trong Unix. Thường tôi dùng nó để xử lý
các nhóm tập tin. Thí dụ, tôi có một thư mục chứa nhiều hình trong đó. Tôi muốn
đổi tên hết thảy sao cho tên mỗi tập tin sẽ có số thứ tự theo sau. Awk rất ngầu
đời mấy vụ này. Bạn chỉ cần biên hai dòng mã awk để đọc tên các tập tin, tính số
thứ tự, gắn vào đằng chót và thế là đổi tên.

Nhưng tôi thì không rành awk cho lắm. Vậy nên cứ mỗi lần tôi cần viết một tiểu
trình awk là tôi phải lật tài liệu ra, nghiên cứu lại một chút, rồi thử cách này
cách kia xem thế nào. Không lâu sau, tôi bắt đầu phải chẩn lỗi một đoạn mã awk
không chạy đúng ý tôi. Hai tiếng đồng hồ sau, tôi mới chợt nhớ là _"Ờ ha, mình
chỉ định đổi tên tập tin thôi mà. Nếu tự gõ thì xong từ mấy kiếp rồi..."_

Để tránh bế tắc, bạn phải biết hướng nào là hướng đi tới. Thành ra trước khi lao
vào săm soi Google hoặc mày mò sửa một cái lỗi thì hãy tự hỏi mình, rằng "Bữa
nay tôi thực sự tính làm gì? Cái việc cỏn con mà lâu lắc này có cần thiết hay
không?" Thường thì không đâu. Và hễ đã không thì hãy bỏ nó qua một bên. Hãy sáng
suốt lên. Bạn sẽ không làm được gì hữu ích ở đây đâu. Hãy quay lại với những
việc thực sự quan trọng đi.

Một khi đã biết hướng đi tới là hướng nào thì bạn có thể bắt đầu bước tới. Bước
tới tức là tiến tới việc giải quyết vấn đề. Đó không chỉ là một bước đi mà là
một bước đi về phía trước.

Lấy ví dụ trong chuyện chẩn lỗi. Tôi từng thấy nhiều lập trình viên cứ loay hoay
tìm hoài một cái lỗi. Họ tự nhủ rằng mất hết mấy tiếng đồng hồ là tại cái lỗi
quá khó. Nhưng rồi một nhà lập trình gạo cội đi tới và sửa lỗi đó chỉ trong vòng
mấy phút. Đúng là đau!

Giữa lập trình viên non tay loay hoay hàng giờ với cao thủ làm xong trong phút
chốc thì có gì khác biệt? Khác biệt chính là một người khéo chẩn lỗi biết cách
đưa ra một nước đi dứt khoát mỗi lúc chạy chương trình lên.

Nhiều người lập trình chẩn lỗi bằng cách đoán mò, rồi chạy thử coi đoán trúng
hay trật. Cứ chạy như vậy hết hai trăm lần cũng chưa thấy được gì.

Lập trình viên thượng thặng không có đoán mò. Mỗi bước đi đều là một thử nghiệm
rõ ràng, xác định và dứt khoát, để kiểm chứng cho giả thuyết của họ về nguyên
nhân gây lỗi.

Lập trình viên non tay đã thực hiện thuật toán O(n). Họ đoán đại. Làm thử. Đoán
tiếp. Rồi thử tiếp. Cứ đi theo linh cảm.

Cái kiểu làm này dẫn bạn thẳng tới bế tắc.

Lập trình viên lành nghề thì tệ lắm là O(logn). Tệ lắm là mỗi thử nghiệm chỉ
loại bỏ một nửa nguyên nhân khả dĩ. Một số thử nghiệm được suy xét cẩn thận có
thể loại trừ một phần lớn hơn nhiều. Do đó cho dù có cả triệu khả thể gây lỗi –
cả triệu dòng mã – thì các kiểm tra cuối cùng cũng sẽ tụ lại đâu đó. Và họ sẽ
làm được chuyện đó chỉ với vài bước mà thôi.

Thành ra phải tiến lên chứ không đi loanh quanh.

Cuối cùng là tiến những bước dứt khoát. Lập trình viên thường làm việc theo trực
giác, và thế thì rất tốt. Trực giác về những lớp cần viết, những hàm cần cài
đặt, và một biến nào đó nên là int hay unsigned int hay char. Trực giác thì ổn
thôi, và không phải trực giác nào cũng cần suy xét tỉ mỉ.

Nhưng khi bạn đối diện với một trở ngại lớn khiến bạn mất rất nhiều thời giờ thì
cái bạn cần không thể chỉ là trực giác. Bạn cần những tiến trình rõ ràng và xác
định. Bạn cần những nước đi cụ thể giúp bạn nhận biết là bạn đang tiến, đang lùi
hay chẳng nhúc nhích chi ráo.

Thí dụ như tôi, khi phải sửa một lỗi lớn, tôi thường viết ra những thao tác đã
làm trong tiến trình đó. Chẳng hạn như sau đây là một số ghi chú từ một lỗi tôi
sửa trong năm nay. Đối với bạn thì trông chúng không có nghĩa gì – đó là một lỗi
trong một lớp con trỏ thông minh (con trỏ tự biết trả bộ nhớ – ND) mà tôi viết –
nhưng chúng sẽ giúp bạn hình dung là tôi ghi chép ra sao. Mỗi dòng ghi lại một
thứ tôi tìm ra sau khi đặt giả thuyết và kiểm chứng.

* Xảy ra ở `Object::Release()`. Xác minh bất thành. Vấn đề là `m_nReferences` bằng 0
khi hàm được gọi.
* Trong trường hợp này hàm được gọi bởi
`ObjectSingleton<AssetManager>::~ObjectSingleton()`, vốn là thứ khiến con trỏ
`s_pInstance` bị rỗng, thành ra dẫn tới việc gọi `Release()`.
* Trớ trêu thay, `Object::Release()` lại gọi hàm hủy, vẫn là khi `this == asset manager`.
* Vậy nói cách khác, hàm trao trả của asset manager đã được gọi, khiến bộ đếm tham
chiếu quay về 0, thành ra đối tượng bị hủy, khiến self-pointer bị rỗng, và hàm
`Release()` lại bị gọi lần nữa.
* Tôi không chắc dữ kiện này mô tả được hết vấn đề hay còn có gì cần xem xét nữa
(ví dụ như vì sao `Object::Release()` được gọi lần đầu?). Nhưng cứ xem tới giờ ta
đã có gì...

Mỗi dòng trên đây mất khoảng 2-3 phút. Đó là thời gian dùng để thiết lập mã kiểm
tra, biên dịch và chạy thử để xác nhận kết quả. Bằng cách viết ra những gì mình
tìm thấy, tôi đã có một cái nhìn rõ ràng hơn về việc tôi đã thực hiện và biết
làm sao để tiến tới. Tôi đã ghi chép đầy đủ nên không phải mắc công truy vết
lại. Và bởi vì đã ghi ra những suy nghĩ của mình nên tôi bảo đảm được rằng tôi
biết mình đang làm gì và tại sao.

Trực giác là một điều tốt, nhưng nó hay đi lạc đề. Lạc đề thì lại không tốt nếu
muốn hoàn thành công việc. Để tránh bế tắc, tôi đặt ra rào chắn cho trực giác
của mình bằng cách ghi chép. Và chuyện đó đúng là hữu dụng. Ngay cả những lỗi
trầm trọng từng đòi hỏi nhiều ngày để sửa nay cũng chỉ tốn vài giờ là cùng. Và
cũng hiếm có lỗi nào trầm trọng đến thế. Một khi tôi có những bước tiến cụ thể,
ít có lỗi nào phải sửa quá mấy phút.

Trên đây tôi nói về việc chẩn lỗi để minh họa cho chuyện tiến bước về phía
trước. Nhưng tôi thấy rằng những ý tưởng này cũng hữu ích trong bất cứ công việc
lập trình nào. Dù là thiết kế lớp, viết ra giải thuật, đưa chương trình lên App
Store hay thậm chí là tụng tài liệu API, thì việc hiểu rõ phương hướng tiến lên
và tiến những bước vững chắc là một bài thuốc tuyệt vời để tránh khỏi sự bế tắc.

Nếu bạn muốn giảm thiểu bế tắc trong cuộc đời lập trình của mình, hãy chắc chắn
rằng bạn tìm ra hướng đi về phía trước, và giữ nhịp tiến bước theo phương hướng
ấy.