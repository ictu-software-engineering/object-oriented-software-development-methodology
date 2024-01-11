# Giới thiệu
Khi chúng ta có sơ đồ miền sơ bộ ở Chương 1, chúng ta có thể bắt đầu viết use case. Về cơ bản, sơ đồ use case cung cấp cho chúng ta một cách có cấu trúc để nắm bắt các yêu cầu hành vi của hệ thống, để ta có thể tạo một thiết kế từ chúng một cách hợp lý.

![Use Case](/images/Chapter-2-Overview.png)

## Tại sao tôi cần các use case bên cạnh các yêu cầu về chức năng?
Các yêu cầu chức năng có xu hướng là sự kết hợp giữa các yêu cầu cấp cao và cấp thấp—gần như là một luồng ý thức từ người quản lý, khách hàng và nhóm tiếp thị được ghi lại dưới dạng nối tiếp và được đưa vào tài liệu Word. Không có gì sai với điều đó; đó chỉ là bước khởi đầu đầu tiên trên con đường đạt được một bản hoàn thiện, rõ ràng về các yêu cầu hành vi mà ta có thể tạo ra một thiết kế từ đó một cách thực tế.

Khi ta viết các use case, hãy viết chúng theo cách nắm bắt hành động của người dùng và phản hồi của hệ thống liên quan. Hay nói cách khác, là cuộc đối thoại giữa người dùng và hệ thống.

![Use Case](/images/User-System.png)


Việc lập mô hình use case bao gồm việc phân tích **basic course** (cách sử dụng hệ thống điển hình vào “ngày nắng” của người dùng; thường được coi là 90% hành vi) và các **alternate courses** (điều gì xảy ra khi có sự cố xảy ra hoặc khi người dùng thử một số tính năng ít được sử dụng của chương trình). Nếu ta nắm bắt được tất cả những điều này trong các use case, ta sẽ xây dựng được phần lớn hệ thống.

Ví dụ về một đặc tả use case:
```
BASIC COURSE:

Khách hàng nhấp vào nút Viết đánh giá cho cuốn sách hiện đang được xem và hệ thống hiển thị màn hình Viết đánh giá. Khách hàng nhập Đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi. Hệ thống đảm bảo rằng Đánh giá sách không quá dài hay quá ngắn và Xếp hạng sách nằm trong khoảng từ một đến năm sao. Sau đó, hệ thống sẽ hiển thị màn hình xác nhận và bài đánh giá sẽ được gửi đến Người điều hành, sẵn sàng để thêm vào.


ALTERNATE COURSE:
- Người dùng chưa đăng nhập: Trước tiên, người dùng được đưa đến màn hình Đăng nhập, sau đó đến màn hình Viết đánh giá sau khi đăng nhập.
- Người dùng nhập đánh giá quá dài (văn bản > 1MB): Hệ thống từ chối đánh giá và phản hồi bằng thông báo giải thích lý do đánh giá bị từ chối.
- Đánh giá quá ngắn (< 10 ký tự): Hệ thống từ chối đánh giá.
```
## Tại sao viết use case lại sau mô hình miền?

Use case được viết trong ngữ cảnh của mô hình miền—nghĩa là, tất cả các thuật ngữ (danh từ và cụm danh từ) đi vào mô hình miền cũng phải được sử dụng trực tiếp trong đặc tả use case

Cách tiếp cận ICONIX giả định rằng mô hình miền ban đầu là sai và đưa ra cách cải thiện dần dần mô hình đó khi ta phân tích các use case. Đó là lý do tại sao ta chỉ nên dành tối đa vài giờ cho việc lập mô hình miền trước khi bắt đầu lập mô hình use case. Khi ta viết các use case, nếu danh từ chưa có trong "từ điển" thì ta phải cập nhật từ điển. Chúng ta luôn phải đảm bảo rằng danh từ/cụm danh từ dùng trong đặc tả use case phải lấy từ "từ điển" - mô hình miền ra.

Trong quá trình thiết kế sơ bộ, mô hình miền biến thành mô hình miền cập nhật, mô hình miền này cuối cùng (trong quá trình thiết kế chi tiết) trở thành mô hình lớp (tức là mô hình tĩnh xác định các lớp phần mềm). Ta nên cập nhật mô hình miền không chỉ khi lập mô hình các use case mà còn khi vẽ sơ đồ độ bền/mạnh mẽ và sơ đồ trình tự.

## Sắp xếp các use cases thành các gói (Packages)
Các gói về cơ bản là các thùng chứa có thứ bậc có thể chứa hầu hết mọi cấu trúc UML, bao gồm cả các gói khác. Nếu bạn là lập trình viên Java, các gói UML không hoàn toàn khác với các gói Java, ở chỗ chúng cho phép bạn chia công việc của mình thành các khu vực khác nhau.

Chúng ta sẽ chia use case thành 04 nhóm: chúng, mua hàng, admin và tìm kiếm. Lưu ý: Đây chỉ là một trong các cách nhóm - thực tế có thể có cách nhóm khác.
1. Chung (general)
- Thêm sản phẩm vào Danh sách mong muốn
- Huỷ Đơn hàng
- Cập nhật Giỏ hàng
- Đăng nhập
- Đăng xuất
- Tạo Tài khoản
- Trả sách
- Xem Lịch sử đơn hàng

2. Mua sắm
- Khách hàng (tác nhân)
- Thêm sản phẩm vào giỏ hàng
- Thanh toán
- Cập nhật Giỏ hàng
- Nhập Địa chỉ
- Thanh toán qua Thẻ tín dụng
- Thanh toán qua Đơn đặt hàng
- Thanh toán bằng Séc
- Xoá sản phẩm ra khỏi Giỏ hàng
- Xem Sách đề xuất
- Xem Đánh giá
- Viết đánh giá khách hàng

3. Quản trị (admin)
+ Dịch vụ chăm sóc khách hàng
+ Người bán
+ Nhân viên chuyển hàng
+ Nhân viên Quản trị web

- Thêm mới sách vào Danh mục
- Thêm đánh giá biên tập
- Thêm sách ngoài hệ thống vào Danh mục
- Gửi đơn hàng
- Quản trị Đánh giá của khách hàng
- Quản lý Hàng tồn kho
- Đặt sách từ Nhà xuất bản
- Xử lý Hoàn tiền
- Xoá sách khỏi danh mục
- Xoá sách ngoài hệ thống khỏi danh mục
- Trả lời câu hỏi
- Mở khoá tài khoản bị khoá

4. Tìm kiếm
- Tìm kiếm nâng cao
- Tìm kiếm theo tác giả
- Tìm kiếm theo tiêu đề
- Tìm kiếm theo danh mục
- Tìm kiếm theo từ khoá
- Tìm kiếm sách

## Vẽ sơ đồ use case tổng quát
Dựa vào 4 nhóm (hoặc gói) trên, ta sẽ có 04 sơ đồ use case tổng quát tương ứng với mỗi nhóm. Hình bên dưới minh hoạ một sơ đồ use case tổng quát cho nhóm Chung. Các bạn làm tương tự với ba gói còn lại

![Use Case Tổng quát](/images/Use-case-tong-quat.png)

Có một điểm lưu ý trong sơ đồ use case tổng quát trên đó là sự vắng mặt của các đường kết nối gữa các tác nhân với use case hoặc giữa các use case với nhau. Điều này là do (theo cách tiếp cận của ICONIX) những đường kết nối này không quá quan trọng bằng việc viết ĐẶC TẢ use case - cái mà chúng ta sẽ dùng rất nhiều khi xây dựng sơ đồ mạnh mẽ (robustness diagram) và sơ đồ trình tự (sequence diagram)