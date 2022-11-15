
# Ứng dụng dịch vụ Grab đơn giản

Chương trình ứng dụng các dịch vụ cơ bản của Grab. Chương trình sẽ thực hiện các dịch vụ cơ bản của Grab như đặt xe, thanh toán, thêm/xóa/chỉnh sửa nhân viên hoặc khách hàng. Để đơn giản hóa thì các nhân viên của Grab sẽ được phân công ở một vị trí cố định. Nếu nhân viên nhận được yêu cầu chở khách thì sau khi chở khách sẽ quay lại vị trí ban đầu sẽ được phân công. Bên cạnh đó, bản đồ sẽ được tọa độ hóa trên mặt phẳng $Oxy$ và khoảng cách giữa hai điểm sẽ được tính theo công thức tính khoảng cách thông dụng (làm tròn đến chữ số thứ 4 sau dấu phẩy thập phân). 

Chương trình sẽ quản lí nhân viên với các thông tin như sau:

- Mã nhân viên.
- Họ và tên nhân viên.
- Ngày, tháng, năm sinh.
- Số CCCD hoặc CMND.
- Bằng lái xe.
- Địa chỉ thường trú.
- Địa chỉ mail.
- Số điện thoại liên lạc.
- Thời gian bắt đầu chạy dịch vụ Grab.
- Vị trí được phân công.

Bên cạnh đó, chương trình sẽ quản lí khách hàng với các thông tin sau:

- Mã khách hàng.
- Họ và tên khách hàng.
- Ngày, tháng, năm sinh.
- Số CCCD hoặc CMND.
- Địa chỉ mail.
- Số điện thoại liên lạc.
- Tài khoản ngân hàng liên kết.

Với mỗi yêu cầu đặt xe, chương trình sẽ quản lí các thông tin gồm:

- Mã yêu cầu.
- Thông tin khách hàng.
- Thông tin tài xế.
- Thời gian yêu cầu:
- Vị trí yêu cầu và vị trí đích đến.
- Số tiền thanh toán.

Chương trình sẽ có các chức năng chính như sau:

- Chức năng **Đặt xe**: Người dùng (*khách hàng*) sẽ thực hiện yêu cầu đặt xe và gửi các thông tin như: tọa độ hiện tại, tọa độ điểm đến cùng với thông tin khách hàng đến hệ thông. Sau đó, hệ thông sẽ thực hiện tìm tài xế gần nhất và đưa ra thông tin của tài xế và giá tiền của dịch vụ.
- Chức năng **Thống kê các yêu cầu nhận được trong ngày của nhân viên bất kì**: Trả về một danh sách các yêu cầu mà tài xế nhận được theo ngày/tháng/năm. Danh sách gồm các thông tin của mỗi yêu cầu đặt xe.
- Chức năng **Thống kê khách hàng sử dụng dịch vụ nhiều nhất ngày/tháng/năm**: Trả về danh sách các khách hàng sử dụng dịch vụ nhiều nhất theo ngày/tháng/năm gòm các thông tin của các yêu cầu đặt xe đã thực hiện.
- Chức năng **Thông kê địa điểm được đến nhiều nhất**: Đưa ra danh sách $10$ địa điểm thường được ghé thăm nhất đi kèm với thông tin của khách hàng và thời gian ghé thăm.
- Các chức năng cơ bản **Thêm/Xóa/Sửa thông tin khách hàng và nhân viên tài xế**.

***Yêu cầu:*** Viết chương trình mô phỏng ứng dụng Grab với các dịch vụ cơ bản trên. Thực hiện đầy đủ các chức năng, thiết kế Menu và UI cho từng các chức năng hoặc các giao diện cần thiết.
