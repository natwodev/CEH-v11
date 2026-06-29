# Footprinting Countermeasures

> Module 02 | Trang 141–144

## Giới thiệu

**Footprinting countermeasures** là các biện pháp hoặc hành động được thực hiện nhằm **ngăn chặn hoặc giảm thiểu việc tiết lộ thông tin** (information disclosure).

Sau khi đã tìm hiểu tầm quan trọng của footprinting, các cách thực hiện và các công cụ hỗ trợ, phần này tập trung vào cách phòng thủ trước hoạt động footprinting.

---

## Danh sách Countermeasures

| # | Biện pháp | Mô tả |
|---|-----------|-------|
| 1 | Restrict social networking access | Hạn chế nhân viên truy cập các trang mạng xã hội từ mạng của tổ chức |
| 2 | Configure web servers | Cấu hình web server để tránh rò rỉ thông tin (information leakage) |
| 3 | Use pseudonyms | Đào tạo nhân viên dùng bí danh (pseudonyms) trên blog, group và forum |
| 4 | Không tiết lộ thông tin trọng yếu | Không công bố thông tin quan trọng trong thông cáo báo chí (press releases), báo cáo thường niên (annual reports), catalog sản phẩm, v.v. |
| 5 | Limit published information | Giới hạn lượng thông tin công bố trên website/Internet |
| 6 | Dùng kỹ thuật footprinting để tự rà soát | Dùng chính kỹ thuật footprinting để phát hiện và gỡ bỏ thông tin nhạy cảm đang công khai |
| 7 | Prevent caching & anonymous registration | Ngăn search engine cache trang web và dùng dịch vụ đăng ký ẩn danh (anonymous registration services) |
| 8 | Develop and enforce security policies | Xây dựng và thực thi chính sách bảo mật (information security policy, password policy, v.v.) để kiểm soát thông tin nhân viên có thể tiết lộ cho bên thứ ba |
| 9 | Tách DNS / split DNS & giới hạn zone transfer | Tách biệt DNS nội bộ và bên ngoài hoặc dùng split DNS; giới hạn zone transfer chỉ cho các server được ủy quyền |
| 10 | Disable directory listings | Tắt liệt kê thư mục (directory listing) trên web server |
| 11 | Security awareness training | Đào tạo nâng cao nhận thức bảo mật định kỳ về các thủ thuật và rủi ro social engineering |
| 12 | Whois privacy | Chọn dịch vụ bảo mật riêng tư (privacy services) trên cơ sở dữ liệu Whois lookup |
| 13 | Avoid domain-level cross-linking | Tránh liên kết chéo ở cấp domain (domain-level cross-linking) cho các tài sản quan trọng |
| 14 | Encrypt & password-protect | Mã hóa và bảo vệ bằng mật khẩu thông tin nhạy cảm |
| 15 | Disable unused protocols | Không bật các giao thức không cần thiết |
| 16 | TCP/IP & IPSec filters | Luôn dùng bộ lọc TCP/IP và IPSec để phòng thủ theo chiều sâu (defense in depth) |
| 17 | Configure IIS | Cấu hình IIS để tránh lộ thông tin qua banner grabbing |
| 18 | Implement VPN / secure proxy | Ẩn địa chỉ IP và thông tin liên quan bằng VPN hoặc đặt server sau một secure proxy |
| 19 | Yêu cầu archive.org xóa lịch sử | Yêu cầu archive.org xóa lịch sử website khỏi cơ sở dữ liệu lưu trữ |
| 20 | Giữ domain name profile private | Giữ hồ sơ tên miền ở chế độ riêng tư |
| 21 | Đưa tài liệu trọng yếu offline | Đặt các tài liệu quan trọng (business plans, tài liệu độc quyền) ở chế độ offline để tránh bị khai thác |
| 22 | Train employees (social engineering) | Đào tạo nhân viên chống lại kỹ thuật và tấn công social engineering |
| 23 | Sanitize thông tin tới registrar | Lọc/giấu thông tin cung cấp cho Internet registrar để ẩn thông tin liên hệ trực tiếp của tổ chức |
| 24 | Disable geo-tagging | Tắt chức năng geo-tagging trên camera để tránh bị theo dõi vị trí (geolocation tracking) |
| 25 | Không tiết lộ vị trí / lịch trình | Tránh tiết lộ vị trí hoặc kế hoạch di chuyển trên mạng xã hội |
| 26 | Turn-off geolocation access | Tắt quyền truy cập định vị trên mọi thiết bị di động khi không cần thiết |
| 27 | Bảo vệ thông tin trên bảng tin/tường | Đảm bảo không có thông tin trọng yếu (kế hoạch chiến lược, thông tin sản phẩm, dự báo doanh số) hiển thị trên bảng tin (notice boards) hoặc tường |

---

## Module Summary

Trong module này, chúng ta đã tìm hiểu các nội dung sau:

- Khái niệm footprinting và các mục tiêu (objectives) của footprinting
- Các kỹ thuật footprinting khác nhau: footprinting qua search engine, qua web services, và qua mạng xã hội
- Website, email, Whois và DNS footprinting
- Network footprinting và footprinting qua social engineering (bao gồm phân tích traceroute)
- Một số công cụ footprinting quan trọng
- Cách tổ chức có thể phòng thủ trước các hoạt động footprinting và reconnaissance

Module này bắt đầu từ khái niệm và mục tiêu của footprinting, giải thích chi tiết các kỹ thuật footprinting qua search engine, web services và mạng xã hội, sau đó là website/email footprinting, Whois và DNS footprinting, network footprinting kèm phân tích traceroute, footprinting qua social engineering, tổng quan các công cụ quan trọng, và kết thúc bằng phần thảo luận chi tiết về các biện pháp phòng thủ.

> **Tiếp theo:** Module kế tiếp sẽ trình bày chi tiết cách attacker cũng như ethical hacker và pen tester thực hiện **network scanning** để thu thập thông tin về mục tiêu trước khi tấn công hoặc audit.
