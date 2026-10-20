# LAB 7: XÂY DỰNG CHÍNH SÁCH WEB PROTECTION TRÊN MÔ HÌNH pfSense VÀ WEB PROXY

### Thông tin sinh viên
* Họ tên: Nguyễn Minh Khang
* Lớp: 11_TTMT
* MSSV: 1150070109
* Link Youtube: https://www.youtube.com/@NguyenMinhKhang-yg6st

### Tóm tắt nội dung thực hành
Bài lab hướng dẫn xây dựng kiến trúc bảo vệ web (Web Protection) bằng cách kết hợp tường lửa pfSense làm gateway kiểm soát luồng và một máy chủ Web Proxy độc lập đảm nhiệm việc lọc nội dung lớp 7. Cụ thể, nội dung thực hành bao gồm:

* Thiết lập mô hình phân tải bảo mật: Xây dựng máy chủ Web Proxy (chạy Ubuntu Server) sử dụng kết hợp các dịch vụ Squid, E2Guardian và ClamAV. Thay vì cài trực tiếp proxy lên tường lửa, pfSense được cấu hình bằng Firewall Rules để ép buộc toàn bộ lưu lượng web của người dùng phải đi qua Web Proxy (cổng 8080) và chặn các kết nối web trực tiếp (TCP/80, 443) nhằm chống bypass
* Thực thi các chính sách lọc nội dung web (Web Policies):
  * Hard block: Chặn triệt để và không cho phép bypass đối với các trang tìm việc làm (Job Search), chặn theo vị trí địa lý (Geo-Sim như Trung Quốc, Trung Đông) và các game cụ thể
  * Warning / Temporary bypass: Hiển thị trang cảnh báo đối với các nhóm nội dung như Vũ khí, Chính trị, Tôn giáo hoặc Streaming, cho phép người dùng xác nhận để vượt qua tạm thời (bypass trong 5 phút)
  * Exception / Whitelist: Cấp quyền truy cập tự do vào các trang web giáo dục (Education) mà không bị cảnh báo hay chặn
  * Chính sách theo thời gian: Kết hợp tính năng Schedule của pfSense để giới hạn truy cập vào nhóm Giải trí/Game chỉ được phép hoạt động trong khung giờ quy định (60 phút)
* Quét mã độc và kiểm soát lưu lượng tải xuống: Tích hợp engine ClamAV với E2Guardian để tự động quét virus các tệp tin tải từ Internet (thực hành kiểm thử chặn file mã độc EICAR), đồng thời giới hạn không cho phép tải các file có dung lượng lớn hơn 100MB
* HTTPS Inspection (Mở rộng): Cấu hình SSL MITM bằng cách khởi tạo CA nội bộ và import chứng chỉ vào máy trạm, cho phép hệ thống proxy giải mã, kiểm tra và lọc được các nội dung web mã hóa qua giao thức HTTPS
* Ghi nhật ký và xử lý sự cố: Thực hành kỹ năng đọc và đối chiếu các bản ghi nhật ký (log) từ ba nguồn: pfSense Firewall Log, E2Guardian Access Log và Squid Access Log để giám sát hệ thống và phân tích nguyên nhân khi người dùng không truy cập được web
