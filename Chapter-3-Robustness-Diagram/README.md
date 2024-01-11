# Sơ đồ mạnh mẽ/độ bền (robustness diagram)
![Robustness Diagram](/images/Robustness-Analysis.png)

Để chuyển từ các use cases sang thiết kế chi tiết (và sau đó là viết mã), ta cần liên kết các use cases với các đối tượng. Kỹ thuật mà chúng ta mô tả trong chương này, phân tích độ bền, giúp ta thu hẹp khoảng cách từ phân tích đến thiết kế. Tóm lại, đó là một cách phân tích kịch bản use cases và xác định tập hợp đối tượng được đoán đầu tiên cho từng use cases. Chúng được phân loại thành các đối tượng ranh giới (biên), đối tượng thực thể (entity) và bộ điều khiển (controller - thường giống chức năng hơn là đối tượng).

Sơ đồ mạnh mẽ là một hình ảnh khách quan của một use case. Sơ đồ mạnh mẽ và kịch bản use case phải khớp một cách chính xác, vì vậy sơ đồ độ mạnh mẽ buộc phải gắn kịch bản use case với các đối tượng. Điều này cho phép ta thiết kế hướng đối tượng từ các use case.

Việc vẽ sơ đồ mạnh mẽ đảm bảo rằng use case được viết trong ngữ cảnh của mô hình miền — nghĩa là, tất cả các thuật ngữ (danh từ và cụm danh từ) trong mô hình miền phải được sử dụng trực tiếp trong kịch bản use case.

## Giải phẫu sơ đồ mạnh mẽ.
Sơ đồ mạnh mẽ phần nào là sự kết hợp giữa sơ đồ lớp và sơ đồ hoạt động. Đó là sự thể hiện bằng hình ảnh của hành vi được mô tả bởi một use case, hiển thị cả các lớp tham gia và hành vi phần mềm, mặc dù nó cố tình tránh hiển thị lớp nào chịu trách nhiệm cho các phần hành vi nào. Mỗi lớp được thể hiện bằng một biểu tượng đồ họa kiểu lập thể (xem hình dưới). Tuy nhiên, sơ đồ mạnh mẽ trông giống sơ đồ hoạt động hơn, theo nghĩa là một đối tượng “giao tiếp” với đối tượng tiếp theo. Luồng hành động này được thể hiện bằng một đường nối giữa hai đối tượng đang giao tiếp với nhau.

![Robustness Notations](/images/Robustness-notations.png)

Có 03 ký phát đồ hoạ được sử dụng trong sơ đồ mạnh mẽ:
- Đối tượng biên (Boundary object): “Giao diện” giữa hệ thống và thế giới bên ngoài. Các đối tượng biên thường là màn hình hoặc trang web (tức là lớp trình bày mà tác nhân tương tác).
- Đối tượng thực thể (Entity object): Các lớp từ mô hình miền
- Bộ điều khiển (Controller): Chất “keo” giữa các đối tượng biên và thực thể.

Sẽ rất hữu ích khi coi các đối tượng biên và đối tượng thực thể là danh từ và bộ điều khiển là động từ. Hãy ghi nhớ các quy tắc sau khi vẽ sơ đồ mạnh mẽ:
- Danh từ có thể nói với động từ (và ngược lại).
- Danh từ không thể nói chuyện với danh từ khác (Boundary object không nói chuyện được với Entity object)
- Động từ có thể nói chuyện với động từ khác.

## Hướng dẫn vẽ sơ đồ mạnh mẽ
### Copy kịch bản use case vào sơ đồ mạnh mẽ
Làm điều này thực sự giúp củng cố thực tế rằng ta đang vẽ một bức tranh khách quan về các sự kiện được mô tả trong use case. Ngoài ra, ta sẽ xử lý từng câu trong use case khi vẽ sơ đồ, vì vậy, sẽ rất hữu ích khi có kịch bản bên cạnh. Hình bên dưới minh hoạ ví dụ về việc copy & paste kịch bản use case vào sơ đồ mạnh mẽ.

![Robustness Copy & Paste](/images/robustness-copy-paste.png)

### Lấy các lớp thực thể từ Mô hình miền và thêm bất kỳ lớp nào còn thiếu

Hầu hết các thực thể trên sơ đồ độ mạnh mẽ sẽ đến từ mô hình miền. Tuy nhiên, vì ta đã giới hạn nỗ lực lập mô hình miền ban đầu trong vài giờ nên việc ta có thể thiếu một số lớp miền là điều tự nhiên. Khi ta đang vẽ sơ đồ mạnh mẽ, hãy thêm các lớp còn thiếu vào mô hình miền.

Quy trình ICONIX giả định rằng mô hình miền ban đầu sẽ không đầy đủ và hy vọng rằng các đối tượng bị thiếu sẽ được phát hiện trong quá trình phân tích mạnh mẽ.

### Chuẩn bị tinh thần cập nhật lại kịch bản use case khi phân tích sơ đồ mạnh mẽ.
Kinh nghiệm của tác giả đã chỉ ra rằng các use case ở bản phác thảo đầu tiên có xu hướng thể hiện các đặc điểm sau: chúng thường mơ hồ, không đầy đủ và không chính xác. Không có gì ngạc nhiên khi rất nhiều dự án đã phải vật lộn với các use case khi không có kỹ thuật phân biệt rõ ràng như phân tích mạnh mẽ. Loại bỏ sự mơ hồ khỏi các use case là một trong những mục đích chính của kỹ thuật này.

“Điều kỳ diệu” của kỹ thuật này trên thực tế là công việc khó khăn: việc vẽ một sơ đồ mạnh mẽ buộc ta phải giải quyết từng use case một. Hành động đơn giản này hầu như luôn gây ra các lỗi bề mặt trong kịch bản use case với bản nháp đầu tiên, vì vậy điều quan trọng là phải viết lại kịch bản use case song song với việc vẽ sơ đồ độ mạnh mẽ.

### Tạo đối tượng biên cho mỗi màn hình
Vẽ sơ đồ mạnh mẽ có thể giúp việc đặt tên rõ ràng. Nếu ta thấy các đối tượng biên được gắn nhãn “trang web” trên sơ đồ độ mạnh mẽ, hãy dừng lại, tìm ra tên của trang và sử dụng tên thật.

### Không cần lo lắng về hướng mũi tên trong sơ đồ mạnh mẽ
Hãy nhớ rằng sơ đồ mạnh mẽ có hai nhiệm vụ chính:
- Làm rõ kịch bản use case
- Khám phá các đối tượng còn thiếu trong mô hình miền

Hướng mà các đầu mũi tên chỉ trên biểu đồ mạnh mẽ không giúp ích gì cho các mục tiêu này. Nói một cách chính thức, các mũi tên trên sơ đồ mạnh mẽ thể hiện các liên kết truyền thông. Ta có thể hiển thị luồng dữ liệu hoặc luồng điều khiển và trong trường hợp chúng ta chưa đề cập đến nó trước đó thì hướng của mũi tên không quan trọng. Hình dưới minh hoạ sơ đồ mạnh mẽ dạng đầy đủ. Chú ý: Màu đỏ là phần alternate course, màu còn lại trong basic course

![Login đầy đủ](/images/login-full.png)









## Công cụ vẽ Robustness Diagram
[Visual Paradigm - Robustness Diagram templates](https://online.visual-paradigm.com/diagrams/templates/robustness-diagram/customer-creation-process/)