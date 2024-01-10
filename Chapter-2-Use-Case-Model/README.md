# Giới thiệu
Khi chúng ta có sơ đồ miền sơ bộ ở Chương 1, chúng ta có thể bắt đầu viết use case. Về cơ bản, sơ đồ use case cung cấp cho chúng ta một cách có cấu trúc để nắm bắt các yêu cầu hành vi của hệ thống, để ta có thể tạo một thiết kế từ chúng một cách hợp lý.

![Use Case](/images/Chapter-2-Overview.png)

## Tại sao tôi cần các use case bên cạnh các yêu cầu về chức năng?
Các yêu cầu chức năng có xu hướng là sự kết hợp giữa các yêu cầu cấp cao và cấp thấp—gần như là một luồng ý thức từ người quản lý, khách hàng và nhóm tiếp thị được ghi lại dưới dạng nối tiếp và được đưa vào tài liệu Word. Không có gì sai với điều đó; đó chỉ là bước khởi đầu đầu tiên trên con đường đạt được một bản hoàn thiện, rõ ràng về các yêu cầu hành vi mà ta có thể tạo ra một thiết kế từ đó một cách thực tế.

Khi ta viết các use case, hãy viết chúng theo cách nắm bắt hành động của người dùng và phản hồi của hệ thống liên quan. Hay nói cách khác, là cuộc đối thoại giữa người dùng và hệ thống.

![Use Case](/images/User-System.png)


Việc lập mô hình use case bao gồm việc phân tích **basic course** (cách sử dụng hệ thống điển hình vào “ngày nắng” của người dùng; thường được coi là 90% hành vi) và các **alternate courses** (điều gì xảy ra khi có sự cố xảy ra hoặc khi người dùng thử một số tính năng ít được sử dụng của chương trình). Nếu ta nắm bắt được tất cả những điều này trong các use case, ta sẽ xây dựng được phần lớn hệ thống.

Ví dụ về một đặc tả use case:

BASIC COURSE:

Khách hàng nhấp vào nút Viết đánh giá cho cuốn sách hiện đang được xem và hệ thống hiển thị màn hình Viết đánh giá. Khách hàng nhập Đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi. Hệ thống đảm bảo rằng Đánh giá sách không quá dài hay quá ngắn và Xếp hạng sách nằm trong khoảng từ một đến năm sao. Sau đó, hệ thống sẽ hiển thị màn hình xác nhận và bài đánh giá sẽ được gửi đến Người điều hành, sẵn sàng để thêm vào.


ALTERNATE COURSE:
- Người dùng chưa đăng nhập: Trước tiên, người dùng được đưa đến màn hình Đăng nhập, sau đó đến màn hình Viết đánh giá sau khi đăng nhập.
- Người dùng nhập đánh giá quá dài (văn bản > 1MB): Hệ thống từ chối đánh giá và phản hồi bằng thông báo giải thích lý do đánh giá bị từ chối.
- Đánh giá quá ngắn (< 10 ký tự): Hệ thống từ chối đánh giá.

## Tại sao viết use case lại sau mô hình miền?

Use case được viết trong ngữ cảnh của mô hình miền—nghĩa là, tất cả các thuật ngữ (danh từ và cụm danh từ) đi vào mô hình miền cũng phải được sử dụng trực tiếp trong đặc tả use case

