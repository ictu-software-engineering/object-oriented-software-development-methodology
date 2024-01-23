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

- Để tìm tên và thuộc tính chúng ta dựa và sơ đồ miền [domain model](/Chapter-1-Domain-Model/) và sơ đồ mạnh mẽ (robustness diagram).
- Để tìm được các phương thức chúng ta dựa vào sơ đồ trình tự. Để xây dựng được sơ đồ trình tự chúng ta cần dựa vào sơ đồ mạnh mẽ.

4. Để xây dựng được sơ đồ mạnh mẽ (robustness diagram), chúng ta cần dựa vào đặc tả use case
5. Để xây dựng được đặc tả use case chúng ta cần dựa và giao diện demo (hoặc GUI storyboard) và sơ đồ miền (domain model)
6. Để xây dựng được sơ đồ miền (domain model) chúng ta cần dựa vào yêu cầu hệ thống + giao diện demo (hoặc GUI storyboard)

Quy trình đó có thể được minh hoạ dưới dạng rút gọn như sau:
![Thông tin cần thiết để điền vào sơ đồ lớp](/images/Buc_tranh_chung.png)


Như vậy đầu vào của chúng ta bao gồm 02 thứ: yêu cầu hệ thống + giao diện demo (hoặc GUI storyboard). Hai thứ này có thể coi là tương đương, một cái ở dạng chữ và một cái ở dạng hình. Việc sử dụng qua lại giữa hai dạng này sẽ giúp chúng ta đảm bảo rằng hệ thống mà chúng ta đang xây dựng sẽ ít gặp sai sót.


# Tài liệu tham khảo
- [Công cụ vẽ visual-paradigm.com](visual-paradigm.com)
- [Tài liệu giảng dạy](https://drive.google.com/file/d/13uSf_5nDbEi86nC8fNb_SODEgC7evRYh/view?usp=sharing)
# Form mẫu báo cáo
Bản báo cáo sẽ gồm những nội dung sau:
1. Yêu cầu hệ thống
 Phần này chỉ cần liệt kê các yêu cầu chức năng và phi chức năng. Chúng ta không cần đi vào mức quá chi tiết: ví dụ xem trong trang 30 của tài liệu Use Case Driven Modeling with UML
2. Sơ đồ miền
Phần này cần trình bày đầy đủ các bước và phương pháp để xây dựng sơ đồ miền. Phân tích đầy đủ các bước từ trang 30 đến trang 38. Đây là bước đầu tiên để điền vào ngăn số 1 trong sơ đồ lớp
3. Viết use case
Trong phần này sẽ chia thành 2 mục nhỏ. Sơ đồ use case tổng quát và kịch bản use case. 
- Đối với sơ đồ use case tổng quát bám theo ví dụ mẫu trong trang 63. Bản chất là nhóm các use case thành các gói (package) và vẽ sơ đồ use case tổng quát cho các gói đó
- Đối với kịch bản use case: Bám theo ví dụ mẫu trang 73 sau đó nhân bản ra cho các use case còn lại

Lưu ý: Trọng số cho phần kịch bản use case sẽ cao hơn vì nó sẽ được sử dụng để vẽ sơ đồ mạnh mẽ và sơ đồ trình tự

4. Sơ đồ mạnh mẽ
Đối với mỗi use case cần có sơ đồ mạnh mẽ tương ứng. Về bản chất là chuyển từ chữ (kịch bản) sang hình (sơ đồ). Giữa kịch bản và sơ đồ phải khớp nhau. Không khớp thì sửa (2 chiều) cho khớp. 

Lưu ý: Thông tin từ sơ đồ mạnh mẽ sẽ được sử dụng để điền vào ngăn số 2 (thuộc tính) trong sơ đồ lớp

5. Sơ đồ trình tự
Sơ đồ mạnh mẽ và sơ đồ trình tự gần như là tương tự nhau, khi ta copy 3/4 thành phần của sơ đồ mạnh mẽ vào sơ đồ trình tự. Phần còn lại (controller) sẽ chuyển thành thông điệp

6. Sơ đồ lớp
Đây là sơ đồ cuối cùng mà chúng ta cần trong học phần này với 03 thông tin quan trọng
- Tên lớp lấy từ sơ đồ miền
- Thuộc tính lấy từ sơ đồ mạnh mẽ
- Phương thức lấy từ sơ đồ trình tự

7. Code demo (Optional)
Phần này là điểm khuyến khích, không yêu cầu sinh viên phải xây dựng hệ thống đầy đủ. Chỉ cần sinh viên biết được chuyển từ sơ đồ lớp sang code như thế nào. Sinh viên xem [Vide chuyển từ sơ đồ lớp sang code](https://youtu.be/pAAFXL_tWQ8?si=e4C7CaaD9joXNJG_) để làm tương tự, copy code do hệ thống tự sinh vào báo cáo là được.