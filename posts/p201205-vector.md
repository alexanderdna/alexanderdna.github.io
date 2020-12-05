# Sử dụng Vector trong Unity

Bạn còn nhớ khái niệm vector khi học môn toán ngày xưa không? Hy vọng bạn nhớ, như vậy mọi thứ sẽ dễ dàng hơn. Còn không thì coi như làm quen lại hen!

## Tại sao lại có vector?

Trong Unity, các object tồn tại trong một không gian 3 chiều, tương ứng các trục X, Y và Z.

Nếu không có gì tác động, thì mặc định ta có:

* **X** là trục hoành: số âm là trái, dương là phải.
* **Y** là trục tung: số âm là dưới, dương là trên.
* **Z** là trục chiều sâu: số âm là gần, dương là xa.

Mọi thứ dẫn tới việc phải có một kiểu dữ liệu dùng để chứa được vị trí, phương hướng, góc xoay, hay thậm chí độ lớn nhỏ, theo từng trục nhất định.

Từ đó, **vector** ra đời.

* `Vector2` chứa thông tin x và y.
* `Vector3` chứa thông tin x, y và z.

Hai kiểu dữ liệu đó có thể chuyển đổi qua lại nếu chiều Z không quá quan trọng.

## Vector là một struct, hay *lời dối gian của property*

Chắc bạn từng không hiểu tại sao Visual Studio lại than phiền khi bạn ghi code thế này:

```csharp
transform.position.x = 10;
```

Có 2 thủ phạm gây ra lời cằn nhằn đó: struct và property.

### Nói về struct

Nếu click vào kiểu dữ liệu `Vector2` hay `Vector3` rồi bấm F12 thì các bạn sẽ thấy nó được định nghĩa đại khái thế này:

```csharp
public struct Vector3
{
    public float x;
    public float y;
    public float z;

    // ...
}
```

Cái bạn cần thấy ở đây là từ khóa **struct**.

Trong môi trường .NET (mà C# và Unity đang dựa trên), **struct** là một kiểu dữ liệu có cách làm việc giống với **class** về mặt thiết kế, *nhưng khác về mặt lưu trữ*.

So sánh giữa struct và class theo kiểu sách vở trong thư viện:

| | struct | class |
| --- | --- | --- |
| Loại sách | sao chép | mượn |
| Mỗi lần gán giá trị hoặc return | photocopy ra một quyển mới | mượn quyển gốc về coi |
| Mỗi lần thay đổi nội dung bên trong | viết lên bản sao | viết lên bản gốc |
| Lúc quay lại thư viện | bản gốc vẫn nguyên vẹn | bản gốc đã thay đổi |

Bạn có thể xem thử code dưới đây:

```csharp
Vector3 a = new Vector3(1, 1, 1);
Vector3 b = a;
b.x = 5;
// Giờ thì kết quả là:
//   a.x == 1
//   b.x == 5
```

### Nói về property

Property là một loại hình kết hợp giữa biến và hàm.

```csharp
class Car
{
    // Đây là biến
    private int _speed;

    // Đây là hàm truy cập
    public int GetSpeed()
    {
        return _speed;
    }

    public void SetSpeed(int speed)
    {
        _speed = speed;
    }
}
```

Đoạn code trên nếu dùng property thì sẽ như sau:

```csharp
class Car
{
    public int Speed
    {
        get;
        set;
    }
}
```

Hoặc:

```csharp
class Car
{
    private int _speed;

    public int Speed
    {
        get { return _speed; }
        set { _speed = value; }
    }
}
```

Bây giờ có một vấn đề. Bạn thấy rằng property thực chất chỉ là hàm `get` và `set` được C# viết thay bạn bằng một cú pháp ngắn gọn mà thôi. Nó không phải là biến để có thể truy cập trực tiếp.

* Biến: _Ê thủ thư, cho tôi xem và sửa quyển sách gốc trên kệ._
* Property: _Ê thủ thư, photo cho tôi quyển sách trên kệ._

Nếu kiểm tra lớp `Transform` của Unity (bằng phím F12), bạn sẽ thấy:

```csharp
public class Transform
{
    public Vector3 position { get; set; }
}
```

Và như phần nói về struct đã đề cập, một giá trị kiểu struct khi được return thì sẽ được sao y bản chính để cung cấp cho bạn. Nói cách khác, đoạn code bị lỗi mà chúng ta thấy khi nãy sẽ tương đương như sau:

```csharp
// Code gây lỗi
transform.position.x = 10;

// Code tương đương
Vector3 positionCopy = transform.position; // thực chất là transform.get_position()
positionCopy.x = 10;
```

Bạn thấy đó. Bạn đang viết lên bản photocopy chứ không phải bản chính. GameObject sẽ chẳng dịch chuyển tới vị trí x = 10 như bạn muốn. Visual Studio nhận ra được bản chất vấn đề, nên lập tức cảnh tỉnh bạn.

Để làm điều mình muốn, ta sửa lại code như sau:

```csharp
Vector3 position = transform.position;
position.x = 10;
transform.position = position;
```

Nghĩa là: ta bắt gã thủ thư ném quyển sách gốc đi, và thế chỗ bằng quyển photocopy mà ta đã chỉnh sửa.

### Chỉ mặt những kẻ dối gian

Tới đây (hy vọng) bạn đã biết lý do và cách giải quyết vấn đề. Còn dưới đây là một số property có đặc tính đã nêu:

* `transform.position`
* `transform.localPosition`
* `transform.eulerAngles`
* `transform.localEulerAngles`
* `transform.localScale`
* `rigidbody.velocity`
* Hay bất cứ property kiểu struct nào khác.
