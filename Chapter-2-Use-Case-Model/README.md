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

Khách hàng nhấp vào nút Viết đánh giá cho cuốn sách hiện đang được xem và hệ thống hiển thị màn hình Viết đánh giá. 
Khách hàng nhập Đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi. 
Hệ thống đảm bảo rằng Đánh giá sách không quá dài hay quá ngắn và Xếp hạng sách nằm trong khoảng từ một đến năm sao. 
Sau đó, hệ thống sẽ hiển thị màn hình xác nhận và bài đánh giá sẽ được gửi đến Người điều hành, sẵn sàng để thêm vào.


ALTERNATE COURSE:
- Người dùng chưa đăng nhập: Trước tiên, người dùng được đưa đến màn hình Đăng nhập, sau đó đến màn hình Viết đánh giá sau khi đăng nhập.
- Người dùng nhập đánh giá quá dài (văn bản > 1MB): Hệ thống từ chối đánh giá và phản hồi bằng thông báo giải thích lý do đánh giá bị từ chối.
- Đánh giá quá ngắn (< 10 ký tự): Hệ thống từ chối đánh giá.
```
## Tại sao viết use case lại sau mô hình miền?

Use case được viết trong ngữ cảnh của mô hình miền—nghĩa là, tất cả các thuật ngữ (danh từ và cụm danh từ) đi vào mô hình miền cũng phải được sử dụng trực tiếp trong đặc tả use case. 

Ví dụ sau minh hoạ viết kịch bản use case mà không dựa vào mô hình miền:


``
Người dùng chọn một tiêu đề sách và thêm nó vào danh sách sách của mình để lưu lại sau này. Hệ thống hiển thị một trang có danh sách cập nhật đồng thời cũng hiển thị danh sách các đầu sách trong giỏ hàng của người dùng, sẵn sàng để thanh toán.
``

Mặc dù kịch bản này có vẻ rõ ràng nhưng nó lại là điểm nóng của sự mơ hồ. Trong các use case tiếp theo, “Danh sách sách sẽ được lưu để sử dụng sau” có thể được rút ngắn thành “danh sách sách” hoặc “sách đã lưu”, cả hai đều có thể được hiểu là có ý nghĩa hoàn toàn khác.

Đây là văn bản đã sửa:


Người dùng chọn **Sách** và thêm nó vào **Danh sách mong muốn** của mình. Hệ thống hiển thị trang có danh sách cập nhật đồng thời hiển thị **Giỏ hàng** của người dùng.


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
- Viết đánh giá sách của người đọc

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

## Viết kịch bản use case -  basic course (ngày nắng)
Chúng ta sẽ bắt đầu viết đặc tả cho use case "Viết đánh giá sách" (Write Review). Mở lại sơ đồ miền ở Chương 1, chúng ta sẽ thấy có 02 loại đánh giá: Đánh giá từ độc giả và đánh giá từ ban biên tập. Chúng ta viết kịch bản cho use case Viết đánh giá sách của người đọc 

Chúng ta bắt đầu bằng những hành động đơn giản đầu tiên:

``
Khách hàng nhập đánh giá về sách đã chọn, cho điểm và gửi. 
Đánh giá được gửi đến người kiểm duyệt.
``

Kịch bản trên là khá ngắn gọn, chúng ta cần làm chi tiết hơn (nhớ quy luật 2-paragraph rule), nghĩa là nó không quá ngắn và không quá dài. Và chúng ta sẽ cùng cải tiến nó. Cụ thể, hãy đảm bảo rằng nó được viết ở dạng chủ động (thì hiện tại, mô tả hành động của người dùng và phản hồi của hệ thống hoặc ngược lại) và đặt tên rõ ràng cho các đối tượng miền tham gia (lấy từ sơ đồ miền). Mục tiêu của chúng ta là mô tả rõ ràng hành vi được yêu cầu của hệ thống và xác định đối tượng miền nào sẽ thực hiện hành vi được yêu cầu đó.

Với những lưu ý như trên, ta tinh chỉnh lại kịch bản use case như sau:

``
Khách hàng chọn sách. Hệ thống hiển thị trang chi tiết sách. Khách hàng bấm vào nút Viết đánh giá, hệ thống hiển thị màn hình Viết đánh giá. Người dùng nhập bài đánh giá về cuốn sách, xếp hạng cuốn sách đó trên 5 sao và nhấp vào nút Gửi. Hệ thống đảm bảo rằng bài đánh giá không quá dài hay quá ngắn và xếp hạng nằm trong khoảng từ một đến năm sao. Sau đó, hệ thống sẽ hiển thị màn hình xác nhận và bài đánh giá sẽ được gửi đến người kiểm duyệt
``

Cách dẫn dắt vấn đề để đến được phần viết đánh giá hơi xa. Có vấn đề đối với cách tiếp cận này đó là khi ta mô tả các sự kiện dẫn đến trang Viết đánh giá, chúng ta thực sự đang mô tả một phần của một use case khác. Do đó, ta tinh chỉnh lại lần 2 như sau:

``
Khách hàng nhấp vào nút Viết đánh giá cho cuốn sách hiện đang được xem và hệ thống hiển thị màn hình Viết đánh giá. Khách hàng nhập Đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi. Hệ thống đảm bảo rằng Đánh giá sách không quá dài hay quá ngắn và Xếp hạng sách nằm trong khoảng từ một đến năm sao. Sau đó, hệ thống hiển thị màn hình xác nhận và đánh giá sẽ được gửi đến Người kiểm duyệt
``

Đọc qua kịch bản trên, ta có thể thấy nó liên quan như thế nào đến mô hình miền. Các đối tượng như Đánh giá sách [29] và Xếp hạng sách [27], xuất hiện trên mô hình miền, được tham chiếu rõ ràng theo tên trong use case. Có một tác nhân con người tên là Khách hàng và chúng ta cũng đã xác định một tác nhân mới tên là Người kiểm duyệt (người chịu trách nhiệm kiểm tra các bài đánh giá trước khi chúng được hiển thị). Và cũng sẽ có một số loại màn hình (giao diện) để tương tác cho use case Viết đánh giá sách.

Use case được cập nhật cũng mô tả quá trình xác thực mà hệ thống thực hiện trên dữ liệu đã gửi (ví dụ: kiểm tra xem Xếp hạng Sách có phải là giá trị hợp pháp hay không, trong phạm vi một và năm sao). Khi ta chuyển sang phân tích độ bền/mạnh mẽ trong Chương 3, việc mô tả quyền xác thực trong kịch bản use case use case là một phương pháp quan trọng để xác định bộ điều khiển (Controllers).

## Viết kịch bản use case -  alternate course (ngày mưa)
Trong kịch bản Viết bài đánh giá của người đọc, tất cả nội dung chúng ta có tại thời điểm này đều dành cho basic course, chẳng hạn như “Khách hàng nhập Bài đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi”. Chúng ta cần phải viết kịch bản trong trường hợp basic course ở phía trên gặp vấn đề hoặc là tình huống khác ít gặp.

``` 
ALTERNATE COURSE:

- Người dùng chưa đăng nhập: Trước tiên, người dùng được đưa đến màn hình Đăng nhập, sau đó đến màn hình Viết đánh giá sau khi đăng nhập.

- Người dùng nhập đánh giá quá dài (văn bản > 1MB): Hệ thống từ chối đánh giá và phản hồi bằng thông báo giải thích lý do đánh giá bị từ chối.

- Đánh giá quá ngắn (< 10 ký tự): Hệ thống từ chối đánh giá
```

## Kịch bản đầy đủ của use case
Kết hợp 02 thông tin basic course và alternate course ta có kịch bản đầy đủ của use case Viết đánh giá của khách hàng

```
BASIC COURSE

Khách hàng nhấp vào nút Viết đánh giá cho cuốn sách hiện đang được xem và hệ thống hiển thị màn hình Viết đánh giá. 
Khách hàng nhập Đánh giá sách, xếp hạng Sách trên 5 sao và nhấp vào nút Gửi. 
Hệ thống đảm bảo rằng Đánh giá sách không quá dài hay quá ngắn và Xếp hạng sách nằm trong khoảng từ một đến năm sao. 
Sau đó, hệ thống hiển thị màn hình xác nhận và đánh giá sẽ được gửi đến Người kiểm duyệt


ALTERNATE COURSE:

- Người dùng chưa đăng nhập: Trước tiên, người dùng được đưa đến màn hình Đăng nhập, sau đó đến màn hình Viết đánh giá sau khi đăng nhập.

- Người dùng nhập đánh giá quá dài (văn bản > 1MB): Hệ thống từ chối đánh giá và phản hồi bằng thông báo giải thích lý do đánh giá bị từ chối.

- Đánh giá quá ngắn (< 10 ký tự): Hệ thống từ chối đánh giá
```

Các bạn làm tương tự cho tất cả các kịch bản use case còn lại. Khi có các kịch bản use case thì chúng ta đã sẵn sàng để sang chương tiếp theo 

## Tại sao không sử dụng use case template?
Theo lập luận của tác giả, các template viết kịch bản use case trước đây quá dài, ví dụ:

```
<the name should be the goal as a short active verb phrase>

Context of use: <a longer statement of the goal, if needed, its normal occurrence conditions>

Scope: <design scope, what system is being considered black-box under design> Level: <one of: summary, user-goal, subfunction>

Primary Actor: <a role name for the primary actor, or description> Stakeholders & Interests: <list of stakeholders and key interests in the use case> Precondition: <what we expect is already the state of the world>

Minimal Guarantees: <how the interests are protected under all exits> Success Guarantees: <the state of the world if goal succeeds>

Trigger: <what starts the use case, may be time event>

Main Success Scenario:

<put here the steps of the scenario from trigger to goal delivery and any cleanup after>

<step #> <action description>

Extensions:

<put here there [sic] extensions, one at a time, each referring to the step of the main scenario>

<step altered> <condition>: <action or sub use case>

<step altered> <condition>: <action or sub use case>

Technology & Data Variations List:

<put here the variations that will cause eventual bifurcation in the scenario>

<step or variation #> <list of variations>

<step or variation #> <list of variations>

Related Information:

<whatever your project needs for additional information>

```

Chúng ta coi mẫu này thật kinh khủng vì mặc dù về mặt lý thuyết nó tao nhã ở chỗ nó bao gồm toàn diện mọi thứ bạn có thể muốn thảo luận cùng với use case, nhưng trên thực tế, nếu bạn yêu cầu nhóm của mình “điền vào biểu mẫu dài” kịch bản mẫu, họ sẽ nhanh chóng phát hiện ra rằng
1. Họ đang lãng phí thời gian.
2. Lãng phí thời gian sẽ khiến họ mất hứng thú với toàn bộ quá trình lập mô hình..
3. Họ có thể điền vào biểu mẫu mà không cần tập trung vào các phần quan trọng (basic course và alternate course) của use case và sẽ không ai biết sự khác biệt