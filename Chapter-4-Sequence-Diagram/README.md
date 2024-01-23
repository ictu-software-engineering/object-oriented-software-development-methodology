# SƠ ĐỒ TRÌNH TỰ
Đến bước này kịch bản use case của chúng ta phải **đầy đủ, chính xác, chi tiết và rõ ràng**
![Quy trình ICONIX - Sequence Diagram](/images/Sequence-Analysis.png)

Ký pháp đồ hoạ của sơ đồ trình tự

![Sequence Diagram - Notations](/images/Sequence-Diagram-Notation.png)

Về cơ bản, sơ đồ trình tự là một cách thể hiện khác của sơ đồ mạnh mẽ. Chỉ có một điểm lưu ý duy nhất đó là: Controller (điều khiển) sẽ chuyển thành Message (thông điệp). Phía trên cùng đó là các đối tượng (nhớ lại chúng ta có 03 loại: biên, thực thể và controller). Đường đứt nét thẳng đứng thể hiện thời gian. 

Có một điểm lưu ý trên sơ đồ này đó là chúng ta không nhìn thấy đối tượng Controller đâu, đó chính là vì controller lúc này đã chuyển hoá thành message nhằm trao đổi thông tin giữa các đối tượng.

# Vai trò của sơ đồ trình tự
Nhìn chung, sơ đồ trình tự có hai vai trò chính mà chúng ta thực sự quan tâm:
1. Cho ta thấy được các thông điệp (message), và đó chính là thông tin chúng ta cần để điền vào sơ đồ lớp.
2. Trình tự các message (hàm), đó chính là thứ mà chúng ta cần khi lập trình. Nó cho chúng ta biết hàm nào gọi trước, gọi sau, tham số truyền vào

# Thuật ngữ
Chúng ta có hàng loạt thuật ngữ đều ám chỉ một thứ nhưng có các tên khác nhau: message, method, function, operation, verb, controller, behavior, event,... - hay nói cách khác là ngăn số 03 của sơ đồ lớp, chỉ là ở các ngữ cảnh khác nhau chúng có các tên gọi khác nhau. Ví dụ

1. Khi đang nói chuyện về yêu cầu hệ thống, chúng ta dùng các thuật ngữ về danh từ (noun) và động từ (verb). Lúc này ngăn số 3 của sơ đồ lớp nó có tên là "động từ"
2. Khi chúng ta nói chuyện về sơ đồ mạnh mẽ thì nó có tên là controller
3. Khi chúng ta nói chuyện về sơ đồ trình tự thì nó có tên là message