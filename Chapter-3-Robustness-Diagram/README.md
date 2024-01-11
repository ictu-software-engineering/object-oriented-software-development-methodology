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

## Hướng dẫn vẽ sơ đồ độ bền
### Copy kịch bản use case vào sơ đồ độ bền




## Công cụ vẽ Robustness Diagram
[Visual Paradigm - Robustness Diagram templates](https://online.visual-paradigm.com/diagrams/templates/robustness-diagram/)