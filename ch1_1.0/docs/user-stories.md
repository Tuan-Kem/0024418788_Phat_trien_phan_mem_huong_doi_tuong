# User Stories — EduHub

Viết ít nhất 5 User Story, đủ 3 vai trò (Sinh viên, Ban CLB, Admin).
Mỗi story có ít nhất 2 tiêu chí nghiệm thu (Given/When/Then hoặc gạch đầu dòng).

# US-01 • Sinh viên: làm thẻ xe
1. Chưa có thẻ -> yêu cầu làm thẻ -> tạo thẻ mới ở trạng thái chờ duyệt.
2. Đã có thẻ đang hoạt động -> yêu cầu làm thẻ mới -> bị từ chối (không được cấp trùng).

# US-02 • Sinh viên: đăng ký gói cước
1. Chọn đúng gói cước (ngày/tháng/năm) và thanh toán -> đăng ký -> thẻ được cập nhật thời hạn sử dụng.
2. Gói cước hiện tại vẫn còn hạn -> đăng ký gia hạn -> cộng dồn thời gian sử dụng vào thẻ.

# US-03 • Sinh viên: check-in vào nhà xe
1. Thẻ hợp lệ và gói cước còn hạn -> check-in -> mở barie và tạo record CheckIn.
2. Thẻ hết hạn -> check-in -> Thông báo ghi nợ (tối đa 2 lần/tháng) -> mở barie và tạo record CheckIn.
3. Bị khóa hoặc không hợp lệ -> check-in -> báo lỗi, từ chối mở barie.

# US-04 • Sinh viên: check-out ra nhà xe
1. Có lịch sử CheckIn khớp với thông tin thẻ/biển số -> check-out -> mở barie và ghi nhận CheckOut.
2. Không có lịch sử CheckIn hoặc sai biển số -> check-out -> báo lỗi, yêu cầu nhân viên xử lý.

# US-05 • Nhân viên: tạo thẻ xe
1. Nhập đầy đủ thông tin sinh viên hợp lệ -> tạo -> cấp thành công mã thẻ (gắn đúng StudentId).
2. Thông tin sinh viên trống hoặc không hợp lệ -> tạo -> báo lỗi.

# US-06 • Nhân viên: làm gói cước cho sinh viên (kích hoạt gói)
1. Thẻ hợp lệ -> chọn gói cước và xác nhận -> cập nhật thành công hạn sử dụng của thẻ.
2. Thẻ đang bị khóa (false) -> làm gói cước -> báo lỗi từ chối.

# US-07 • Nhân viên: quản lý ra vào nhà xe của sinh viên
1. Xem thống kê -> thấy tổng số xe đang có trong bãi và số lượng xe đã check-out trong ngày.
2. Tìm kiếm thẻ/biển số -> liệt kê chi tiết lịch sử: thời gian check-in / check-out của sinh viên đó.

# US-08 • Admin: khóa thẻ xe
1. Thẻ đang hoạt động -> khóa -> false.
2. Lịch sử ra vào và lịch sử đăng ký gói cước của thẻ đó vẫn được giữ nguyên.
3. Thẻ không hoạt động -> khóa -> true.



