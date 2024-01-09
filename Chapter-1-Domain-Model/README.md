# Giới thiệu sơ đồ miền
![Domain](/images/Domain-Model.png)
Đây là sơ đồ đầu tiên chúng ta cần phải tạo trong quy trình ICONIX. Về cơ bản sơ đồ miền được coi là phiên bản đơn giản của sơ đồ lớp. Sự khác biệt đó là: sơ đồ miền chỉ có tên, trong khi sơ đồ lớp có đủ cả 03 thông tin: tên lớp, thuộc tính và phương thức như được minh hoạ dưới đây.
![Domain](/images/Domain_Class.png)

# Tạo sơ đồ miền
Chúng ta có một số hướng dẫn để tạo sơ đồ miền. Về mặt tổng thể trên một sơ đồ chúng ta có 2 thứ cần quan tâm: các hình vẽ trong sơ đồ và mối quan hệ giữa các hình vẽ. Hình vẽ trên sơ đồ được gọi là đối tượng miền (domain object), và mối quan hệ giữa các đối tượng miền là các loại đường kết nối. Đầu tiên chúng ta phải xác định được đối đượng miền, dựa vào đâu? Đầu vào của chúng ta có ban đầu chính là yêu cầu hệ thống (yêu cầu chức năng + phi chức năng) và giao diện demo (GUI storyboard hoặc HTML demo). Chúng ta hãy xem xét yêu cầu sau (yêu cầu được cho trước).

## Yêu cầu hệ thống
1. Cửa hàng sách ban đầu sẽ dựa trên web, nhưng nó phải có kiến trúc đủ linh hoạt để có thể phát triển các giao diện người dùng thay thế (Swing/applet, dịch vụ web, v.v.)

2. Hiệu sách phải có khả năng bán sách với các đơn đặt hàng được chấp nhận qua Internet.