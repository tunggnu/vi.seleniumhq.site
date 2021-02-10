---
title: "Dự án Selenium và các công cụ"
weight: 1
---

### Selenium điều khiển trình duyệt web

_Selenium_ là nhiều thứ
nhưng cốt lõi của nó là một bộ công cụ để tự động hóa trình duyệt web
sử dụng các kỹ thuật tốt nhất hiện có
để điều khiển từ xa các phiên bản trình duyệt
và mô phỏng tương tác của người dùng với trình duyệt.

Nó cho phép lập trình viên mô phỏng
các hoạt động phổ biến được thực hiện bởi người dùng cuối;
nhập văn bản vào các trường, chọn giá trị thả xuống và hộp kiểm,
và nhấp vào liên kết trong tài liệu.
Nó cũng cung cấp nhiều điều khiển khác như di chuyển chuột,
thực thi JavaScript tùy ý và hơn thế nữa.

Mặc dù được sử dụng chủ yếu để kiểm tra bề ngoài (front-end) của các trang web,
cốt lõi của Selenium là một _thư viện_ phần mềm trình duyệt.
Các giao diện phổ biến đối với ứng dụng của chúng (?), điều này khuyến khích
việc kết hợp Selenium với các thư viện khác để phù hợp với mục đích của bạn.


### Một giao diện để quản lý tất cả

Một trong các nguyên tắc chỉ đạo của dự án
là hỗ trợ một giao diện chung cho tất cả các công nghệ trình duyệt (chính).
Các trình duyệt web là các ứng dụng được thiết kế cao độ, cực kỳ phức tạp,
thi hành các hoạt động của chúng theo các cách hoàn toàn khác nhau
nhưng lại thường trông giống nhau trong khi làm thế.
Mặc dù văn bản được hiển thị với cùng phông chữ,
hình ảnh được hiển thị tại cùng một chỗ
và các liên kết đưa bạn đến cùng một đích.
Những thứ đang diễn ra bên dưới là khác biệt như ngày với đêm.
Selenium lược bỏ những khác biệt đó,
che giấu những phức tạp và chi tiết của chúng khỏi người viết mã.
Điều này cho phép bạn viết vài dòng mã để thực hiện một quy trình công việc
phức tạp, nhưng cùng những dòng này sẽ thực thi được trên Firefox,
Internet Explorer, Chrome, và tất cả các trình duyệt được hỗ trợ khác.


### Công cụ và hỗ trợ

Cách tiếp cận thiết kế tối giản của Selenium đã cho nó tính đa dụng
để có thể được gộp vào làm một thành phần trong các ứng dụng lớn hơn.
Hạ tầng xung quanh được cung cấp bởi dự án Selenium
cho bạn các công cụ để ghép lại thành
[mạng lưới trình duyệt]({{< ref "/grid/_index.md" >}}) của bạn,
để cho các bài kiểm tra có thể được chạy trên nhiều trình duyệt và nhiều hệ
điều hành qua một loạt máy tính.

Hãy tưởng tượng một hàng máy tính trong phòng máy chủ hoặc trung tâm dữ liệu
của bạn, tất cả đều khởi động trình duyệt cùng một lúc,
tấn công vào các liên kết, biểu mẫu và bảng
của trang web—kiểm tra ứng dụng của bạn 24 giờ một ngày.
Thông qua giao diện lập trình đơn giản
được cung cấp cho các ngôn ngữ phổ biến nhất,
những bài kiểm tra này sẽ chạy song song không biết mệt,
thông báo lại cho bạn khi có lỗi xảy ra.

Mục đích là giúp bạn biến điều này thành hiện thực, bằng cách cung cấp cho
người dùng các công cụ và tài liệu để không chỉ kiểm soát các trình duyệt mà còn
giúp dễ dàng mở rộng và triển khai các mạng lưới như vậy.


### Ai sử dụng Selenium

Nhiều công ty quan trọng nhất trên thế giới đã ứng dụng Selenium vào công
việc kiểm tra dựa trên trình duyệt của họ, thường thay thế các nỗ lực
kéo dài nhiều năm liên quan đến các công cụ độc quyền khác. Khi nó ngày
càng phổ biến, các yêu cầu và thử thách của nó cũng tăng lên gấp bội.

Khi web trở nên phức tạp hơn
và các công nghệ mới được thêm vào các trang web,
nhiệm vụ của dự án này là theo kịp chúng khi có thể.
Là một dự án mã nguồn mở, sự hỗ trợ này được cung cấp thông qua
sự đóng góp thời gian hào phóng từ nhiều tình nguyện viên,
mỗi người trong số họ đều có một "công việc ban ngày".

Một nhiệm vụ khác của dự án là khuyến khích
nhiều tình nguyện viên hơn nữa tham gia vào nỗ lực này,
và xây dựng một cộng đồng vững mạnh
để cho dự án có thể tiếp tục theo kịp với các công nghệ mới mẻ
và tiếp tục là nền tảng chủ đạo cho việc tự động hóa kiểm tra chức năng.


### Lịch sử

Khi Selenium 1 được phát hành năm 2004,
nó đã ra đời từ sự cần thiết giảm bớt thời gian tiêu tốn
cho việc xác minh thủ công hành vi nhất quán của bề ngoài một ứng dụng web.
Nó đã sử dụng những công cụ có sẵn tại thời điểm đó
và dựa rất nhiều vào việc chèn JavaScript vào trang web đang kiểm tra
để mô phỏng tương tác của người dùng.

Trong khi JavaScript là một công cụ tốt cho phép bạn tìm hiểu các thuộc tính của
DOM và làm các quan sát nhất định phía máy khách mà bạn sẽ không thể làm nếu
không có nó, nó thiếu khả năng sao chép tự nhiên các tương tác của người dùng
như thể chuột và bàn phím đang được sử dụng.

Kể từ đó, Selenium đã phát triển và trưởng thành rất nhiều, trở thành
một công cụ được sử dụng rộng rãi bởi nhiều—nếu không phải là hầu hết—các
tổ chức lớn nhất trên thế giới.
Selenium đã đi từ một bộ công cụ tự động hóa kiểm tra "cây nhà lá vườn" được
phát triển tại Thoughtworks cho một đối tượng dành riêng và một trường hợp sử
dụng cụ thể, đến thư viện tự động hóa trình duyệt _trên thực tế_ của thế giới.

Cũng giống như Selenium RC đã sử dụng các công cụ thương mại có sẵn vào thời
điểm đó, [Selenium WebDriver]({{< ref "/webdriver/_index.md" >}}) tiếp tục
truyền thống đó bằng cách đưa phần tương tác của trình duyệt đến sân nhà của nhà
cung cấp trình duyệt và yêu cầu họ chịu trách nhiệm về phần cài đặt đằng sau
(backend), đối diện với trình duyệt. Gần đây, công việc này đã phát triển thành
quy trình chuẩn hóa W3C với mục tiêu là biến thành phần WebDriver trong Selenium
thành thư viện điều khiển từ xa cho các phần mềm trình duyệt.
