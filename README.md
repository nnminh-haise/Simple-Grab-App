
# Ứng dụng dịch vụ Grab đơn giản

Đây là một chương trình mô phỏng lại một số dịch vụ cơ bản của Grab. Để đơn giản hóa việc xác định tọa độ cho các đối tượng thì ở đây thống nhất sử dụng hệ tọa độ $Oxy$ với $|x|, |y| \le 10^6$ và các tọa độ phải là các số nguyên. Để đơn giản việc tìm đường đi thì sẽ luôn tồn tại một đường thẳng đi qua hai tọa độ của khách hàng và tài xế. Nghĩa là việc tìm tài xế cho khách hàng chỉ là tìm tài xế có khoảng cách ngắn nhất so với tọa độ hiện tại của khách hàng. Khoảng cách được tính bằng công thức:

$$s = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}$$

### Nhân viên

Chương trình sẽ quản lí nhân viên với các thông tin như sau:

- Mã nhân viên (*số nguyên duy nhất được tăng tự động*).
- Họ và tên nhân viên (không quá $256$ kí tự).
- Ngày, tháng, năm sinh (DD/MM/YYYY).
- Số CCCD (có đúng $12$ chữ số).
- Bằng lái xe ($12$ chữ số).
- Địa chỉ thường trú (không quá $256$ kí tự).
- Địa chỉ mail (không quá $256$ kí tự).
- Số điện thoại liên lạc ($10$ chữ số).
- Thời gian bắt đầu chạy Grab (định dạng ngày/tháng/năm: DD/MM/YYYY).
- Tọa độ ban đầu (có dạng `(x, y)` và luôn luôn cố định).

### Khách hàng

Chương trình sẽ quản lí khách hàng với các thông tin sau:

- Mã khách hàng (*số nguyên duy nhất được tăng tự động*).
- Họ và tên khách hàng (không quá $256$ kí tự).
- Ngày, tháng, năm sinh (định dạng DD/MM/YYYY).
- Số CCCD (có đúng $12$ chữ số).
- Địa chỉ mail (không quá $256$ kí tự).
- Số điện thoại liên lạc ($10$ chữ số).

Với mỗi yêu cầu đặt xe, chương trình sẽ quản lí các thông tin gồm:

- Mã yêu cầu (*số nguyên duy nhất được tăng tự động*).
- Thông tin khách hàng (mã khách hàng).
- Thông tin tài xế (mã nhân viên).
- Thời gian yêu cầu (gồm ngày theo định dạng DD/MM/YYYY và thời gian theo định dạng giờ/phút/giây).
- Vị trí yêu cầu và vị trí đích đến (tọa độ `(x, y)` bắt đầu và `(u, v)` đích đến).
- Số tiền thanh toán (không quá $10^9$ VND).

### Các chức năng chính của dịch vụ

- Chức năng **Đăng kí khách hàng mới**: Chương trình tạo form và yêu cầu khách hàng điền các thông tin dưới đây và thực hiện thêm khách hàng mới vào cơ sở dữ liệu.

    - Họ và tên khách hàng (không quá $256$ kí tự).
    - Ngày, tháng, năm sinh (định dạng DD/MM/YYYY).
    - Số CCCD (có đúng $12$ chữ số và đóng vai trò là **mã khách hàng** xác định các khách hàng với nhau).
    - Địa chỉ mail (không quá $256$ kí tự).
    - Số điện thoại liên lạc ($10$ chữ số).

- Chức năng **Đăng kí nhân viên mới**: Chương trình tạo form và yêu cầu nhân viên điền các thông tin dưới đây và thực hiện thêm nhân viên mới vào cơ sở dữ liệu.

    - Họ và tên nhân viên (không quá $256$ kí tự).
    - Ngày, tháng, năm sinh (DD/MM/YYYY).
    - Số CCCD (có đúng $12$ chữ số và đóng vai trò là **mã nhân viên** xác định các nhân viên với nhau).
    - Bằng lái xe ($12$ chữ số).
    - Địa chỉ thường trú (không quá $256$ kí tự).
    - Địa chỉ mail (không quá $256$ kí tự).
    - Số điện thoại liên lạc ($10$ chữ số).
    - Thời gian bắt đầu chạy Grab (định dạng ngày/tháng/năm: DD/MM/YYYY).
    - Tọa độ ban đầu (có dạng `(x, y)` và luôn luôn cố định).

- Chức năng **Đặt xe**: Người dùng (*khách hàng*) sẽ thực hiện yêu cầu đặt xe đến chương trình. Khách hàng sẽ gửi các thông tin dưới đây đến chương trình, sau đó chương trình sẽ thực hiện tìm kiếm tài xế (*nhân viên*) gần nhất với khách hàng đưa thông tin cho khách. Nếu có nhiều tài xế có cùng khoảng cách gần giống nhau sẽ được sắp xếp theo tên và họ. Sau khi tài xế đi đón khách sẽ quay lại vị trí ban đầu quy định sẵn.

    - Địa chỉ (tọa độ hiện tại của khách hàng).
    - Đích đến (tọa độ đích đến mong muốn của khách hàng).
    - Mã khách hàng.

- Chức năng **Thống kê các yêu cầu nhận được trong ngày của nhân viên bất kì**: Trả về một danh sách các yêu cầu mà tài xế nhận được sắp xếp theo ngày đến tháng và năm. Danh sách bao gồm các thông tin sau:

    - Mã yêu cầu.
    - Thời gian diễn ra yêu cầu.
    - Mã khách hàng.

- Chức năng **Thống kê khách hàng sử dụng dịch vụ nhiều nhất theo ngày/tháng/năm**: Trả về danh sách các khách hàng sử dụng dịch vụ nhiều nhất theo ngày/tháng/năm gồm các thông tin sau (danh sách được sắp xếp giảm dần theo số lần sử dụng dịch vụ trong ngày/tháng/năm):

    - Họ và tên khách hàng.
    - Số lần sử dụng dịch vụ trong ngày/tháng/năm.

- Chức năng **Thông kê địa điểm được đến nhiều nhất**: Đưa ra danh sách $10$ địa điểm thường được ghé thăm nhất, mỗi địa điểm đưa ra số lượt khách hàng đã ghé thăm và mã khách hàng của khách hàng ghé thăm gần đây nhất.

- Chức năng **Xóa/Sửa thông tin của khách hàng và nhân viên**. Thực hiện xóa khách hàng hoặc nhân viên ra khỏi cơ sở dữ liệu. Thực hiện sửa thông tin của khách hàng hoặc nhân viên ra khỏi cơ sở dữ liệu.

### Yêu cầu

- Thực hiện đầy đủ các chức năng đã được yêu cầu ở trên.
- Tạo giao diện người dùng (*User interface*) cho các chức năng nêu trên và các chức năng phụ khác nếu cần thiết.
- Cơ sở dữ liệu (thông tin sinh viên và thông tin các buổi sinh hoạt) sẽ được lưu dưới dạng file `*.txt`. Nếu có thể thì áp dụng cơ sở dữ liệu (database) vào để lưu trữ dữ liệu.
