# LAB 4: SỬ DỤNG NMAP

### Thông tin sinh viên
* **Họ tên:** Nguyễn Minh Khang
* **Lớp:** 11_TTMT
* **MSSV:** 1150070019
### Tóm tắt nội dung thực hành
Bài lab này hướng dẫn chi tiết cách cấu hình mạng máy ảo và sử dụng công cụ Nmap trên hệ điều hành Kali Linux để quét các máy mục tiêu. Nội dung thực hành bao gồm các bước sau:
* Thiết lập mạng VMware ở chế độ Host-only và kiểm tra dải IP của các máy ảo
* Dò tìm các thiết bị đang hoạt động trong mạng (Host Discovery)
* Thực thi các kỹ thuật quét cổng khác nhau bao gồm: TCP Connect Scan (-sT), SYN Scan (-sS), FIN/Xmas/NULL Scan, ACK Scan và UDP Scan
* Quét để nhận diện phiên bản dịch vụ (-sV) và xác định hệ điều hành (OS Detection)
* Sử dụng chế độ quét tổng quát (Aggressive Scan -A).
* Ứng dụng Nmap Scripting Engine (NSE) để thu thập thông tin về giao thức SMB và kiểm tra lỗ hổng bảo mật MS17-010
* Xuất và lưu trữ kết quả quét thành các định dạng tệp tin: TXT, XML, Grepable và thao tác chuyển đổi file XML sang giao diện HTML
* So sánh sự khác biệt của hệ thống trước và sau khi được tăng cường bảo mật (Before/After Hardening)
