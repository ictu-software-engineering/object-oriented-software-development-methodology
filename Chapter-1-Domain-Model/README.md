# Giới thiệu sơ đồ miền
![Domain](/images/Domain-Model.png)
Đây là sơ đồ đầu tiên chúng ta cần phải tạo trong quy trình ICONIX. Về cơ bản sơ đồ miền được coi là phiên bản đơn giản của sơ đồ lớp. Sự khác biệt đó là: sơ đồ miền chỉ có tên, trong khi sơ đồ lớp có đủ cả 03 thông tin: tên lớp, thuộc tính và phương thức như được minh hoạ dưới đây.
![Domain](/images/Domain_Class.png)

# Tạo sơ đồ miền
Chúng ta có một số hướng dẫn để tạo sơ đồ miền. Về mặt tổng thể trên một sơ đồ chúng ta có 2 thứ cần quan tâm: các hình vẽ trong sơ đồ và mối quan hệ giữa các hình vẽ. Hình vẽ trên sơ đồ được gọi là đối tượng miền (domain object), và mối quan hệ giữa các đối tượng miền là các loại đường kết nối. Đầu tiên chúng ta phải xác định được đối đượng miền, dựa vào đâu? Đầu vào của chúng ta có ban đầu chính là yêu cầu hệ thống (yêu cầu chức năng + phi chức năng) và giao diện demo (GUI storyboard hoặc HTML demo). Chúng ta hãy xem xét yêu cầu sau (yêu cầu được cho trước).

## Yêu cầu hệ thống
1. **Hiệu sách** [1] ban đầu sẽ dựa trên web, nhưng nó phải có kiến trúc đủ linh hoạt để có thể phát triển các giao diện người dùng thay thế (Swing/applet, dịch vụ web, v.v.)
2. Hiệu sách phải có khả năng bán **sách** [2] với các **đơn hàng** [3] được chấp nhận qua **Internet** [4].
3. Người dùng phải thêm được sách vào **giỏ hàng** [5] trực tuyến, trước khi **thanh toán** [6]
- Tương tự, người dùng phải có khả năng xoá **mặt hàng** [7] ra khỏi giỏ hàng
4. Người dùng phải có khả năng duy trì một **danh sách mong muốn** [8] các sách mà họ muốn mua sau này
5. Người dùng phải có khả năng huỷ hoá đơn trước khi nó được vận chuyển
6. Người dùng phải có khả năng thanh toán qua **thẻ tín dụng** [9] hoặc **đơn đặt hàng** [10]
7. Người dùng phải có khả năng trả sách
8. Cửa hàng phải có khả năng nhúng vào các trang web **đối tác liên kết** [11] sử dụng **danh mục nhỏ** [12] được trích xuất từ **danh mục lớn** [13] trong **cơ sở dữ liệu** [14]
- Danh mục nhỏ cần được định nghĩa dưới dạng XML
- **Hệ thống vận chuyển** [15] sẽ được thực hiện bởi Amazon Web Services
9. Người dùng phải có khả năng tạo **tài khoản khách hàng** [16] để hệ thống có thể lưu thông tin chi tiết về người dùng (ví dụ: tên, địa chỉ, thông tin chi tiết thẻ tín dụng,,) khi đăng nhập
  - Hệ thống cần phải duy trì **danh sách tài khoản** [17] trong cơ sở dữ liệu trung tâm
  - Khi người dùng đăng nhập, **mật khẩu** [18] của họ cần phải khớp với mật khẩu trong **danh sách tài khoản chính** [19].
10. Người dùng phải có khả năng tìm kiếm sách theo các **phương pháp tìm kiếm** [20] khác nhau như **tiêu đề** [21], **tác giả** [22], **từ khoá** [23] hoặc **danh mục** [24] - và sau đó xem **chi tiết sách** [25]
11. Người dùng phải có khả năng đăng các nhận xét của các sách ưa thích; **đánh giá bình luận** [26] cần phải xuất hiện trong màn hình chi tiết sách. Nhận xét cần có **đánh giá của khách hàng** [27] (1-5) - đánh giá này thông thường sẽ được hiển thị cùng với tiêu đề sách trong **danh sách các sách** [28]
- **Đánh giá sách** [29] cần phải được quản lý - phải được đánh dấu "OK" bởi nhân viên trước khi hiển thị lên website
- Những nhận xét dài cần phải được làm ngắn gọn lại trên trang chi tiết sách; **khách hàng** [30] có thể bấm vào xem nhận xét đầy đủ để xem trên trang web khác
12. Hệ thống phải cho phép nhân viên **đánh giá biên tập** [31]. Nhận xét biên tập phải xuất hiện trên trang chi tiết sách.
13. Cửa hàng cho phép **người bán** [32] (bên ngoài hệ thống) thêm **danh mục sách** [33] của họ. Danh mục sách này sẽ được thêm vào **danh mục sách chính** [34] để có thể hiển thị trên **trang kết quả tìm kiếm** [35]
14. Hiệu sách phải có khả năng mở rộng, với những yêu cầu cụ thể sau:
  - Hiệu sách phải có khả năng duy trì **tài khoản người dùng** [36] đến 100,000 khách hàng trong 6 tháng đầu tiên và sau đó là 1000,000 tài khoản
  - Hiệu sách phải có khả năng đáp ứng 1,000 lượt truy cập đồng thời (10,000 sau 6 tháng)
  - Hiệu sách phải có khả năng đáp ứng 100 truy vấn trên một phút (1,000 phút sau 6 tháng)
  - Hiệu sách phải có khả năng đáp ứng xử lý 100 đơn hàng trên một giờ (1,000 đơn hàng/giờ sau 6 tháng)

Chúng ta để ý tất cả những từ bôi đậm - đó là các **danh từ/cụm danh từ** mà chúng ta quan tâm. Đây chính là các ứng viên để giúp chúng ta điền thông tin vào tên lớp hoặc thuộc tính bởi vì cả tên và thuộc tính đều là danh từ.

Chúng ta tách các từ bôi đậm thành một danh sách riêng như sau:

- ~~Hiệu sách [1]~~
- Sách [2]
- Đơn hàng [3]
- ~~Internet [4]~~
- Giỏ hàng [5]
- Thanh toán [6]
- Mặt hàng [7]
- Danh sách mong muốn [8]
- Thẻ tín dụng [9]
- Đơn đặt hàng [10]
- Đối tác liên kết [11]
- Danh mục sách nhỏ [12]
- ~~Danh mục chính [13]~~
- Cơ sở dữ liệu [14]
- Hệ thống vận chuyển [15]
- Tài khoản khách hàng [16]
- ~~Danh sách tài khoản [17]~~
- ~~Mật khẩu [18]~~
- Danh sách tài khoản chính [19]
- Phương pháp tìm kiếm [20]
- ~~Tiêu đề [21]~~
- Tác giả [22]
- ~~Từ khóa [23]~~
- Danh mục [24]
- ~~Chi tiết sách [25]~~
- ~~Đánh giá bình luận [26]~~
- Đánh giá của khách hàng [27]
- Danh sách các sách [28]
- Đánh giá sách [29]
- ~~Khách hàng [30]~~
- Đánh giá biên tập [31]
- ~~Người bán [32]~~
- ~~Danh mục sách [33]~~
- Danh mục sách chính [34]
- Kết quả tìm kiếm [35]
- ~~Tài khoản người dùng [36]~~

Chúng ta tiến hành tinh chỉnh lại danh sách dựa trên một số các tiêu chí sau:
- Loại bỏ các danh từ quá rộng
- Loại bỏ các danh từ quá hẹp
- Loại bỏ các danh từ bị trùng lặp
- Loại bỏ các danh từ nằm ngoài hệ thống

Dựa vào các tiêu chí trên ta tiến hành phân tích như sau:
- Thuật ngữ Khách hàng [30], Người bán [32] bị loại bỏ do nằm ngoài hệ thống. Chúng ta sẽ sử dụng danh từ này là các tác nhân trong biểu dồ use case
- Thuật ngữ "Tài khoản người dùng" [36] "Tài khoản khách hàng" [16] bị trùng lặp. Ta giữ lại "Tài khoản khách hàng" [16] vì nó phù hợp với nghiệp vụ kinh doanh hơn
- Danh sách tài khoản [17] và Danh sách tài khoản chính [19] bị trùng lặp, ta giữ lại Danh sách tài khoản chính [19] vì nó sẽ nhất quán với Danh mục sách chính [34]
- Thuật ngữ Đánh giá bình luận [26] và Đánh giá sách [29] bị trùng lặp, ta sẽ giữ lại Đánh giá sách [29]
- Chúng ta có một vài các thuật ngữ là ứng viên cho danh mục sách bao gồm: Danh mục sách [33], Danh sách các sách [28], Danh mục sách nhỏ [12] và Danh mục sách chính [34]. Danh mục sách [33] và Danh mục sách chính [34] bị trùng lặp, chúng ta giữ lại Danh mục sách chính [34] vì nó tương phản với Danh mục sách nhỏ [12]. Danh sách các sách [28] là một thuật ngữ rộng nhưng ta vẫn để lại xem xét
- Thuật ngữ Danh mục chính [13] và Danh mục sách chính [34] bị trùng lặp, ta giữ lại Danh mục sách chính [34]
- Thuật ngữ "Internet" [4] quá rộng nên chúng ta sẽ bỏ
- Thuật ngữ Mật khẩu [18] quá hẹp và chi tiết để có thể trở thành một đối tượng và nó hiển thị trên giao diện như là một thành phần. Vì vậy ta sẽ bỏ ra khỏi mô hình miền. Tương tự như vậy đối với Tiêu đề [21] và Từ khóa [23]
- Thuật ngữ "Chi tiết sách" [25] và "Sách" [2] bị trùng lặp. Ta giữ lại "Sách" [2] vì nó mang nhiều ý nghĩa đối tượng hơn
- Thuật ngữ "Mặt hàng" (item) [7] là khá mơ hồ, chúng ta đổi tên lại thành "Mục hàng" (line item) [7] cho rõ nghĩa
- Thuật ngữ "Hiệu sách" [1] khá rộng nên chúng ta sẽ bỏ.

Sau khi tinh tỉnh ta còn lại một danh sách các ứng viên đối tượng miền như sau:
1. Sách [2]
2. Đơn hàng [3]
3. Giỏ hàng [5]
4. Thanh toán [6]
5. Mục hàng [7]
6. Danh sách mong muốn [8]
7. Thẻ tín dụng [9]
8. Đơn đặt hàng [10]
9. Đối tác liên kết [11]
10. Danh mục sách nhỏ [12]
11. Cơ sở dữ liệu [14]
12. Hệ thống vận chuyển [15]
13. Tài khoản khách hàng [16]
14. Danh sách tài khoản chính [19]
15. Phương pháp tìm kiếm [20]
16. Tác giả [22]
17. Danh mục [24]
17. Đánh giá của khách hàng [27]
19. Danh sách các sách [28]
20. Đánh giá sách [29]
21. Đánh giá biên tập [31]
22. Danh mục sách chính [34]
23. Kết quả tìm kiếm [35]

## Vẽ sơ đồ miền sơ bộ
Chúng ta có sơ đồ miền sơ bộ như sau. Chúng ta chỉ sử dụng một loại mối quan hệ trong sơ đồ trên - mối quan hệ kết tập (aggregation). Lưu ý mối quan hệ trong sơ đồ có thể KHÔNG ĐÚNG:

![Sơ đồ miền sơ bộ](/images/Initial-Domain-Model.png)
Trong sơ đồ trên, một số đối tượng miền không có mối quan hệ với các đối tượng khác. Chúng ta sẽ tiến hành cập nhật lại sơ đồ miền khi chúng ta xây dựng sơ đồ mạnh mẽ (robustness diagram ở phần sau)

## Tinh chỉnh sơ đồ miền
Chúng ta cần phải tinh chỉnh sơ đồ miền sau khi đã có bản sơ bộ đầu tiên. Đây là giai đoạn tương đối khó vì nó đòi hỏi chúng ta cần phải tư duy. Có một cách mà chúng ta có thể tiếp cận để tư duy trong giai đoạn này đó là tham khảo các hệ thống tương đương. Sau khi tham khảo ta bổ sung 04 đối tượng miền mới mà không có rõ ràng trong yêu cầu của hệ thống bao gồm: Lịch sử đơn hàng [37] và Lệnh chuyển đơn hàng [38], Kho hàng [39], Hàng tồn kho [40] bởi vì chúng ta muốn các đối tượng miền của chúng ta có sự kết nối với nhau. Hiếm có đối tượng miền nào trong hệ thống đứng độc lập

Chúng ta loại bỏ đối tượng "Thanh toán" ra khỏi mô hình vì "Thanh toán" giống động từ hơn là danh từ. Chúng ta cũng loại bỏ "Tác giả" ra khỏi mô hình cho tinh gọn vì ta sẽ coi tác giả là một thuộc tính ở trong sách.

Sau khi tư duy và tham khảo các trang web bán sách, chúng ta thấy rằng để đi từ Danh mục sách chính [34] đến Sách vẫn phải qua một bước trung gian nữa, đó là trong danh mục sách chính cũng lại có danh mục sách. Vì vậy ta bổ sung lại Danh mục sách (đã loại bỏ ở bước trước) vào lại sơ đồ miền, đồng thời chỉnh lại mối quan hệ giữa chúng.

Sơ đồ miền sau khi được tinh chỉnh lần 1 sẽ được biểu diễn như sau (nền đỏ là những đối tượng mới được thêm vào, nền đen là những đối tượng bị loại bỏ):

![Domain](/images/Domain-Updated-V1.png)

Nhìn vào sơ đồ trên ta thấy một mớ các mối quan hệ. Chúng ta cần làm gọn lại với tư tưởng hướng đối tượng - đó chính là tính kế thừa (nhìn từ trên xuống) hoặc khái quát hoá (nhìn từ dưới lên)

## Khái quát hoá (generalization)
Mối quan hệ khái quát hóa là mối quan hệ trong đó một lớp là một “loại” của một số lớp khác— ví dụ: Mèo là một loại Động vật. Đây là lý do tại sao sự khái quát hóa thường được gọi là mối quan hệ "là - một" (is-a)

Mèo cụ thể hơn Động vật (Mèo là sự “tinh chỉnh” của lớp Động vật tổng quát hơn), do đó có thuật ngữ “khái quát hóa”. Lớp cụ thể hơn được gọi là lớp con và lớp tổng quát hơn là siêu lớp. Tạo ra các lớp con của các lớp tổng quát hơn được gọi là phân nhóm.

Trong "Hiệu sách" trên Internet, "Danh mục sách" là một ứng cử viên sáng giá cho việc phân loại sách, vì làm như vậy sẽ giúp “làm mờ” mối quan hệ giữa Danh mục nhỏ và Danh mục sách chính. Danh sách sách cũng là một lựa chọn phù hợp để phân loại vì có thể có nhiều loại tài khoản và các loại danh sách sách khác nhau.

Khi chúng ta nghiên cứu sâu hơn về nhu cầu của người dùng đối với hệ thống Hiệu sách Internet, chúng ta bắt đầu xác định các loại danh sách sách khác nhau: Danh sách mong muốn của khách hàng, Danh sách đề xuất, Sách liên quan, Kết quả tìm kiếm, v.v. Rõ ràng rằng đây đều chỉ là danh sách Sách, vì vậy chúng có thể (ít nhất về mặt khái niệm) có một lớp cha chung. Chúng ta đã phát hiện ra rằng thực sự có những khía cạnh của Danh sách mong muốn, Sách liên quan và sẽ sớm đủ khác biệt để biện minh cho việc xử lý riêng biệt, trong khi chúng vẫn có đủ điểm chung để chúng là tất cả các loại Danh sách sách. Mối quan hệ khái quát hoá được minh hoạ như trong hình sau

![Generalization](/images/generalization.png)

Các lớp mới (Sách liên quan, Danh sách đề xuất, Danh sách mong muốn và Kết quả tìm kiếm) kế thừa các thuộc tính và thao tác mà chúng ta xác định cho Danh sách sách: Một danh sách sách có sách. Sách liên quan là một danh sách sách. Danh sách đề xuất là một danh sách sách. Danh sách mong muốn là một danh sách sách. Kết quả tìm kiếm là một danh sách sách


![Final](/images/Final-domain-v1.png)

Chúng ta cũng đã thay đổi định nghĩa về Đánh giá sách để giờ đây nó là lớp cha của Đánh giá biên tập và lớp mới - Đánh giá của người đọc. Và cuối cùng, chúng ta đã gỡ rối các mối quan hệ xung quanh Đơn hàng và các loại thanh toán của nó (Thẻ tín dụng và Đơn đặt hàng), bằng cách thêm một siêu lớp mới - Loại thanh toán.

Như vậy về sơ bộ chúng ta đã xây dựng xong sơ đồ miền ở bước đầu tiên. Cần nhớ rằng đây là cách làm tốt nhất của chúng ta ở thời điểm hiện tại. Sơ đồ này chỉ là sơ đồ thô với các lập luận của ta và nó có thể cần cập nhật ở các bước sau này. Điểm nổi bật của sơ đồ miền khi chúng ta xây dựng đó chính là việc nó đóng vai trò là quyển **TỪ ĐIỂN SỐNG** khi chúng ta xây dựng đặc tả use case. Sau khi xây dựng xong sơ đồ miền, chúng ta đã sẵn sàng sang sơ đồ [Use Case](/Chapter-2-Use-Case-Model/README.md)

## Ví dụ tương tự
Chúng ta hãy xem một ví dụ tương tự sau với
- Đầu vào: yêu cầu hệ thống (giống chúng ta vừa làm xong)
- Đầu ra: Sơ đồ lớp (cũng là cái chúng ta muốn trong khoá học này):

## Problem Statement
*"Develop a graphic editor that can draw different geometric shapes such as line, circle and triangle. User can select, move or rotate a shape. To do so, editor provides user with a menu listing different commands. Individual shapes can be grouped together and can behave as a single shape."* 

---
### Step 1). Identify Classes
Extract nouns in the problem statement.

Develop a graphic **editor** that can draw different geometric **shapes** such as **line**, **circle** and **triangle**. **User** can select, move or rotate a **shape**. To do so, **editor** provides **user** with a **menu** listing different **commands**. Individual **shapes** can be grouped together and can behave as a single **shape**. 

Eliminate irrelevant classes.
* Editor - Very broad scope
* User – Out of system boundary
* commands – Broad scope

Add more classes by analyzing requirements
* Group - required to behave as a shape
  * Individual shapes can be grouped together and can behave as a single shape
* View – editor must have a display area

Following classes have been identified:
* Shape
* Line
* Circle
* Triangle
* Menu
* **Group**
* **View**
### Basic Object Model - Graphic Editor
![initial](https://user-images.githubusercontent.com/41892175/45860923-6614ff00-bd9c-11e8-87fb-530b0b6dc907.jpg)

---
### Step 2). Identify Associations
Extract verbs connecting objects.

**"Individual shapes can be grouped together"**
* Group consists of lines, circles, triangles
* Group can also consists of other groups

(Composition)

Verify access paths.

**View contains shapes**
* View contains lines
* View contains circles
* View contains triangles
* View contains groups

(Aggregation)

**Menu sends message to View**

(Simple One-Way Association)
### Basic Object Model - Graphic Editor
![45861910-dbcf9980-bda1-11e8-9004-d37512a6f1fe](https://user-images.githubusercontent.com/41892175/45867325-c8c6c480-bdb5-11e8-9e97-c83869ab384d.jpg)


---
### Step 3). Identify Attributes
Extract properties of the object from the domain knowledge.
* **Shape**
  * Color
  * Vertices
* **Line**
  * Color
  * Vertices
  * Length
* **Circle**
  * Color
  * Vertices
  * Radius
* **Triangle**
  * Color
  * Vertices
  * Angle
* **Menu**
  * Name
  * isOpen
* **Group**
  * noOfObjects
* **View**
  * noOfObjects
  * selected
### Basic Object Model - Graphic Editor
![initial](https://user-images.githubusercontent.com/41892175/45867370-e7c55680-bdb5-11e8-8a42-be5fcbee820b.jpg)

---
### Step 4). Identify Operations
Extract verbs connected with an object.

**Develop** a graphic editor that can **draw** different geometric shapes such as line, circle and triangle. User can **select**, **move** or **rotate** a shape. To do so, editor **provides** user with a menu listing different commands. Individual shapes can be **grouped** together and can **behave** as a single shape.

Eliminate irrelevant operations.
* Develop - out of system boundary
* Provides - have broad semantics
* Behave – broad semantics

Following are selected operations:
* **Shape**
  * Draw
  * Select
  * Move
  * Rotate
* **Line**
  * Draw
  * Select
  * Move
  * Rotate
* **Circle**
  * Draw
  * Select
  * Move
  * Rotate
* **Triangle**
  * Draw
  * Select
  * Move
  * Rotate
* **Menu**
  * Open
  * Select
  * Move
  * Rotate
* **Group**
  * Draw
  * Select
  * Move
  * Rotate

Extract operations using domain knowledge
* **View**
  * Add
  * Remove
  * Group
  * Show
### Basic Object Model - Graphic Editor
![initial](https://user-images.githubusercontent.com/41892175/45868828-5657e380-bdb9-11e8-8a65-c63c00f45aec.jpg)

---
### Step 5). Identify Inheritance
Search “is a kind of” by looking at keywords like “such as”, “for example”, etc

**"…shapes such as line, circle and triangle…"**
   * Line, Circle and Triangle inherits from Shape

By analyzing requiremens

**"Individual shapes can be grouped together and can behave as a single shape"**
   * Group inherits from Shape
### Refined Object Model - Graphic Editor
![initial](https://user-images.githubusercontent.com/41892175/45870172-d895d700-bdbc-11e8-86c9-048304dd22a2.jpg)


Rõ ràng cách thức xây dựng mô hình miền Y CHANG như cách chúng ta đang tiếp cận: đó là tìm kiếm danh từ/cụm danh từ, tinh chỉnh (thêm/xoá) và vẽ sơ đồ chỉ có tên. Như vậy cách chúng ta đi theo tài liệu ICONIX là đang đúng hướng.