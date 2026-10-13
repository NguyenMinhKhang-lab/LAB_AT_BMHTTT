 LAB 6: XÁC THỰC ACTIVE DIRECTORY VÀ CHÍNH SÁCH TRUY CẬP TRÊN pfSense[cite: 3]

 Thông tin sinh viên
* Họ tên: Nguyễn Minh Khang
* Lớp: 11_TTMT
* MSSV: 1150070109
* Link Youtube: https://www.youtube.com/@NguyenMinhKhang-yg6st

 Tóm tắt nội dung thực hành
Bài lab tập trung vào việc triển khai firewall pfSense nâng cao, tích hợp hệ thống xác thực tập trung và áp dụng các kịch bản kiểm soát truy cập thực tế. Cụ thể, nội dung thực hành bao gồm:

* Xây dựng môi trường mạng: Thiết lập pfSense với 4 vùng mạng riêng biệt bao gồm WAN, MGMT (Quản trị), LAN (Nội bộ) và DMZ (Vùng phi quân sự).
* Tích hợp Active Directory (AD): Cấu hình Domain Controller (DC01) và kết nối pfSense với hệ thống AD thông qua giao thức LDAP để đồng bộ thông tin tài khoản.
* Cấu hình Captive Portal:** Thiết lập cổng xác thực Captive Portal trên phân vùng LAN, yêu cầu người dùng (Client-A, Client-B) phải đăng nhập tài khoản Domain mới được cấp quyền truy cập mạng.
* Quản lý đối tượng (Alias & Schedule): Tạo các Alias để quản lý nhóm IP của người dùng và các trang web mô phỏng (General, Job, Social, Restricted). Đồng thời thiết lập các khung giờ (Schedule) như giờ hành chính và giờ nghỉ trưa[cite: 12].
* Thực thi chính sách truy cập (Firewall Rules):** Triển khai các kịch bản kiểm soát như:
  * Chặn hoặc cho phép truy cập các trang web cụ thể dựa trên máy người dùng.
  * Mở quyền truy cập mạng xã hội riêng cho Client-B vào giờ nghỉ trưa.
  * Chỉ cho phép dùng dịch vụ Web (HTTP/HTTPS) trong giờ hành chính.
  * Cô lập vùng DMZ không cho phép khởi tạo kết nối ngược vào LAN.
* Theo dõi và xử lý sự cố: So sánh sự khác biệt giữa hành động Block và Reject, đồng thời thực hành đọc Firewall Log và quản lý State Table để gỡ lỗi hệ thống.
