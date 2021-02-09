---
title: "Tham quan nhanh"
weight: 1
---

Selenium không chỉ là một công cụ hoặc API
mà nó hợp thành từ nhiều công cụ.

## WebDriver

Nếu bạn đang bắt đầu với tự động hóa việc kiểm tra trang web trên máy tính để
bàn hoặc thiết bị di động, thì bạn sẽ sử dụng API WebDriver.
_[WebDriver]({{< ref "/webdriver/_index.md" >}})_ sử dụng các API tự động hóa
do nhà cung cấp trình duyệt cung cấp để kiểm soát trình duyệt và chạy các bài
kiểm tra. Nó giống như thể một người dùng thực đang điều khiển trình duyệt. Vì
WebDriver không yêu cầu API của nó phải biên dịch cùng mã ứng dụng, nên nó không
xâm phạm mã. Do đó bạn đang kiểm tra cùng một ứng dụng mà bạn sẽ phát hành.


## IDE

_[IDE](https://selenium.dev/selenium-ide)_ (Integrated Development Environment - 
môi trường phát triển tích hợp) là công cụ bạn dùng để phát triển các trường hợp
kiểm tra của Selenium. Nó là một tiện ích mở rộng dễ dùng cho Chrome và Firefox,
và nói chung là cách hiệu quả nhất để phát triển các trường hợp kiểm tra. Nó ghi
lại các hành động của người dùng trên trình duyệt, dùng các lệnh Selenium hiện
có, với các tham số được định nghĩa theo ngữ cảnh. Điều này không chỉ tiết kiệm
thời gian mà còn là một cách tuyệt vời để học cú pháp tập lệnh Selenium.

## Grid

Selenium Grid cho phép bạn chạy các trường hợp kiểm tra trong
các máy khác nhau qua các nền tảng khác nhau. Việc kiểm soát
sự kích hoạt các trường hợp kiểm tra là ở phía cục bộ, và khi
các trường hợp kiểm tra được kích hoạt, chúng sẽ tự động được
thực thi ở phía từ xa.

Sau khi phát triển các bài kiểm tra WebDriver, bạn có thể đối
diện với nhu cầu chạy các bài kiểm tra của mình trên nhiều tổ
hợp trình duyệt và hệ điều hành.
Đó chính là lúc _[Grid]({{< ref "/grid/_index.md" >}})_ xuất hiện.