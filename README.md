# Phương pháp phát triển phần mềm hướng đối tượng
Các tài liệu về phương pháp phát triển phần mềm hướng đối tượng tương đối nhiều, dài, ở mức trừu tượng cao và khó hiểu đặc biệt là đối với những người mới bắt đầu nghiên cứu về vấn đề này. Cái chúng ta thực sự cần ở thời điểm ban đầu đó là một thiết kế tối giản, chạy được để giúp cho chúng ta hình dung bức tranh tổng thể của hệ thống từ bước thiết kế đến lập trình sẽ như thế nào? tại sao lập trình viên chỉ cần nhìn vào bản thiết kế có thể code được. Khoá học này sẽ đồng hành cùng các bạn để vén bức màn đó. 

## Quy trình phát triển phần mềm
Trước khi đi chi tiết vào một vấn đề chúng ta cần phải nắm được các bước cụ thể mà chúng ta định làm là như thế nào? đầu vào chúng ta có gì ở mỗi bước và đầu ra chúng ta cung cấp cho các bước tiếp theo là gì. Có nhiều quy trình phát triển phần mềm như quy trình thác nước, xoắn ốc, lặp, gia tăng, Agile, RUP...Mỗi mô hình đều có những ưu điểm và nhược điểm riêng, không mô hình nào là "kinh thánh" chung. Khoá học này sẽ bám theo quy trình mà ít được nhắc đến trong các bài viết phổ biến. Đó là quy trình ICONIX.

Về cơ bản quy trình ICONIX được minh hoạ như hình dưới.
![Quy trình ICONIX](/images/ICONIX.png)

Cái hay nhất của quy trình ICONIX chính là việc trả lời câu hỏi **"Chúng ta viết code từ use case như thế nào?"** 
Cách tiếp cận để trả lời câu hỏi trên của ICONIX rất đơn giản: Tìm hiểu đầu vào và đầu ra của code và use case, truy vết để tìm mối liên hệ giữa chúng

Quy trình ICONIX có thể tóm tắt bằng chữ như sau:

1. Để viết code được chúng ta cần sơ đồ lớp (class diagram)
2. Để xây dựng được sơ đồ lớp chúng ta cần 03 thông tin: tên lớp, thuộc tính, và phương thức.

- Để tìm tên và thuộc tính chúng ta dựa và sơ đồ miền (domain model) và sơ đồ mạnh mẽ (robustness diagram).
- Để tìm được các phương thức chúng ta dựa vào sơ đồ trình tự. Để xây dựng được sơ đồ trình tự chúng ta cần dựa vào sơ đồ mạnh mẽ.

4. Để xây dựng được sơ đồ mạnh mẽ (robustness diagram), chúng ta cần dựa vào đặc tả use case
5. Để xây dựng được đặc tả use case chúng ta cần dựa và giao diện demo (hoặc GUI storyboard) và sơ đồ miền (domain model)
6. Để xây dựng được sơ đồ miền (domain model) chúng ta cần dựa vào yêu cầu hệ thống + giao diện demo (hoặc GUI storyboard)

Như vậy đầu vào của chúng ta bao gồm 02 thứ: yêu cầu hệ thống + giao diện demo (hoặc GUI storyboard). Hai thứ này có thể coi là tương đương, một cái ở dạng chữ và một cái ở dạng hình. Việc sử dụng qua lại giữa hai dạng này sẽ giúp chúng ta đảm bảo rằng hệ thống mà chúng ta đang xây dựng sẽ ít gặp sai sót.


