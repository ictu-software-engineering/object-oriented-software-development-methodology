# Giới thiệu sơ đồ miền
![Domain](/images/Domain-Model.png)
Đây là sơ đồ đầu tiên chúng ta cần phải tạo trong quy trình ICONIX. Về cơ bản sơ đồ miền được coi là phiên bản đơn giản của sơ đồ lớp. Sự khác biệt đó là: sơ đồ miền chỉ có tên, trong khi sơ đồ lớp có đủ cả 03 thông tin: tên lớp, thuộc tính và phương thức như được minh hoạ dưới đây.
![Domain](/images/Domain_Class.png)

# Tạo sơ đồ miền
Chúng ta có một số hướng dẫn để tạo sơ đồ miền. Về mặt tổng thể trên một sơ đồ chúng ta có 2 thứ cần quan tâm: các hình vẽ trong sơ đồ và mối quan hệ giữa các hình vẽ. Hình vẽ trên sơ đồ được gọi là đối tượng miền (domain object), và mối quan hệ giữa các đối tượng miền là các loại đường kết nối. Đầu tiên chúng ta phải xác định được đối đượng miền, dựa vào đâu? Đầu vào của chúng ta có ban đầu chính là yêu cầu hệ thống (yêu cầu chức năng + phi chức năng) và giao diện demo (GUI storyboard hoặc HTML demo). Chúng ta hãy xem xét yêu cầu sau (yêu cầu được cho trước).

## Yêu cầu hệ thống
1. **Hiệu sách** ban đầu sẽ dựa trên web, nhưng nó phải có kiến trúc đủ linh hoạt để có thể phát triển các giao diện người dùng thay thế (Swing/applet, dịch vụ web, v.v.)

2. Hiệu sách phải có khả năng bán **sách** với các **đơn đặt hàng** được chấp nhận qua **Internet**.
3. Người dùng phải thêm được sách vào **giỏ hàng trực tuyến**, trước khi **thanh toán**
- Tương tự, người dùng phải có khả năng xoá **mặt hàng** ra khỏi giỏ hàng
4. Người dùng phải có khả năng duy trì một **danh sách mong muốn** các sách mà họ muốn mua sau này
5. Người dùng phải có khả năng huỷ hoá đơn trước khi nó được vận chuyển
6. Người dùng phải có khả năng thanh toán qua **thẻ tín dụng** hoặc **hoá đơn mua**
7. Người dùng phải có khả năng trả sách
8. Cửa hàng phải có khả năng nhúng vào các trang web **đối tác liên kết** sử dụng **danh mục nhỏ** được trích xuất từ **danh mục lớn** trong **cơ sở dữ liệu**
- Danh mục nhỏ cần được định nghĩa dưới dạng XML
- **Hệ thống vận chuyển** sẽ được thực hiện bởi Amazon Web Services
9. Người dùng phải có khả năng tạo **tài khoản khách hàng** để hệ thống có thể lưu thông tin chi tiết về người dùng (ví dụ: tên, địa chỉ, thông tin chi tiết thẻ tín dụng,,) khi đăng nhập
  - Hệ thống cần phải duy trì **danh sách các tài khoản** trong cơ sở dữ liệu trung tâm
  - Khi người dùng đăng nhập, **mật khẩu** của họ cần phải khớp với mật khẩu trong **danh sách tài khoản chính**.
10. Người dùng phải có khả năng tìm kiếm sách theo **các phương thức tìm kiếm** khác nhau - **tiêu đề, tác giả, từ khoá **hoặc **danh mục** - và sau đó xem **chi tiết sách**
11. Người dùng phải có khả năng đăng các nhận xét của các sách ưa thích; **các nhận xét** cần phải xuất hiện trong màn hình chi tiết sách. Nhận xét cần có **đánh giá của khách hàng** (1-5) - đánh giá này thông thường sẽ được hiển thị cùng với tiêu đề sách trong **danh sách các sách**
- **Nhận xét sách** cần phải được quản lý - phải được đánh dấu "OK" bởi nhân viên trước khi hiển thị lên website
- Những nhận xét dài cần phải được làm ngắn gọn lại trên trang chi tiết sách; **khách hàng** có thể bấm vào xem nhận xét đầy đủ để xem trên trang web khác
12.

    
    
