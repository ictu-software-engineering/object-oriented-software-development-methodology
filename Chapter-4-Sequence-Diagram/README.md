# SƠ ĐỒ TRÌNH TỰ
Đến bước này kịch bản use case của bạn phải **đầy đủ, chính xác, chi tiết và rõ ràng**
![Quy trình ICONIX - Sequence Diagram](/images/Sequence-Analysis.png)

Ký pháp đồ hoạ của sơ đồ trình tự

![Sequence Diagram - Notations](/images/Sequence-Diagram-Notation.png)

Về cơ bản, sơ đồ trình tự là một cách thể hiện khác của sơ đồ mạnh mẽ. Chỉ có một điểm lưu ý duy nhất đó là: Controller --> Message. Phía trên cùng đó là các đối tượng (nhớ lại chúng ta có 03 loại: biên, thực thể và controller). Đường đứt nét thẳng đứng thể hiện thời gian. 

Có một điểm lưu ý trên sơ đồ này đó là chúng ta không nhìn thấy đối tượng Controller đâu, đó chính là vì controller lúc này đã chuyển hoá thành message nhằm trao đổi thông tin giữa các đối tượng.

# Vai trò của sơ đồ trình tự
Sơ đồ trình tự có ba vai trò chính trong quy trình ICONIX
- Phân phối hành vi/hàm cho các lớp: Trong quá trình vẽ sơ đồ trình tự, các thông điệp (message) sẽ được chuyển hoá thành các hàm trên các lớp. Không nhất thiết chúng ta phải ánh xạ 1:1 từ controller sang hàm. Thực tế, một controller có thể có nhiều hàm. Hoặc thậm chí chúng ta cũng có lớp Controller (**Controller class**)
- 

