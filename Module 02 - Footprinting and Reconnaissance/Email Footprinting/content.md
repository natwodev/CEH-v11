# Email Footprinting

> Module 02 | Trang 101–105

## Giới thiệu

Sau khi đã tìm hiểu footprinting qua công cụ tìm kiếm, qua Google, qua mạng xã hội và qua website, phần này chuyển sang **email footprinting**. Nội dung gồm: cách theo dõi giao tiếp email, cách thu thập thông tin từ email header và các công cụ theo dõi email.

---

## Tracking Email Communications

**Email tracking** (theo dõi email) là việc giám sát các tin nhắn email của một người dùng cụ thể. Việc theo dõi này khả thi nhờ các bản ghi được **đóng dấu thời gian số (digitally time-stamped)**, cho biết thời gian và ngày mục tiêu **nhận** và **mở** một email nhất định.

Các công cụ theo dõi email cho phép kẻ tấn công thu thập thông tin như **địa chỉ IP, mail server và nhà cung cấp dịch vụ (service providers)** liên quan đến việc gửi email. Kẻ tấn công dùng thông tin này để xây dựng chiến lược tấn công (hacking strategy) và thực hiện social engineering cùng các đòn tấn công khác.

Ví dụ công cụ theo dõi email: **eMailTrackerPro, Infoga, Mailtrack**.

### Thông tin về nạn nhân thu thập được qua công cụ theo dõi email

- **Recipient's System IP address** — Cho phép theo dõi địa chỉ IP của người nhận.
- **Geolocation** — Ước tính và hiển thị vị trí của người nhận trên bản đồ, thậm chí có thể tính khoảng cách từ vị trí của kẻ tấn công.
- **Email Received and Read** — Thông báo cho kẻ tấn công khi email được người nhận **nhận** và **đọc**.
- **Read Duration** — Khoảng thời gian người nhận dành để đọc email do người gửi gửi.
- **Proxy Detection** — Cung cấp thông tin về loại server mà người nhận sử dụng.
- **Links** — Kiểm tra xem các liên kết gửi cho người nhận qua email đã được nhấp/kiểm tra hay chưa.
- **Operating System and Browser information** — Tiết lộ thông tin về hệ điều hành và trình duyệt người nhận dùng. Kẻ tấn công có thể dựa vào đó tìm lỗ hổng trong phiên bản hệ điều hành và trình duyệt để tung ra các đòn tấn công tiếp theo.
- **Forward Email** — Xác định email gửi cho người dùng có được chuyển tiếp (forward) cho người khác hay không.
- **Device Type** — Cung cấp thông tin về loại thiết bị dùng để mở và đọc email, ví dụ máy tính để bàn, thiết bị di động hoặc laptop.
- **Path Travelled** — Theo dõi đường đi mà email đã qua thông qua các email transfer agent từ hệ thống nguồn đến hệ thống đích.

---

## Collecting Information from Email Header

Một **email header** chứa các chi tiết về người gửi, thông tin định tuyến (routing information), cơ chế địa chỉ (addressing scheme), ngày, chủ đề và người nhận. Email header còn giúp kẻ tấn công truy vết đường định tuyến mà email đã đi qua trước khi đến tay người nhận.

Mỗi email header là một nguồn thông tin hữu ích để kẻ tấn công tung ra các cuộc tấn công nhắm vào mục tiêu. Quy trình xem email header khác nhau tùy theo từng chương trình email.

### Các chương trình email thường dùng

| | |
|---|---|
| eM Client | Spike |
| Mailbird Lite | Claws Mail |
| Hiri | SmarterMail Webmail |
| Mozilla Thunderbird | Outlook |

### Thông tin trong email header

Email header chứa các thông tin sau:

| Trường (Field) | Mô tả |
|---|---|
| Sender's mail server | Mail server của người gửi |
| Date and time of receipt | Ngày và giờ email được nhận bởi email server của bên gửi (originator) |
| Authentication system | Hệ thống xác thực được mail server của người gửi sử dụng |
| Date and time of sending | Ngày và giờ gửi tin nhắn |
| Unique number | Một số duy nhất do `mx.google.com` gán để định danh tin nhắn |
| Sender's full name | Họ tên đầy đủ của người gửi |
| Sender's IP address | Địa chỉ IP của người gửi và địa chỉ mà từ đó tin nhắn được gửi đi |

Kẻ tấn công có thể truy vết và thu thập tất cả thông tin trên bằng cách thực hiện **phân tích chi tiết toàn bộ email header**.

---

## Email Header Analysis

Khi phân tích chi tiết một email header (xem *Figure 2.56*), có thể ánh xạ các trường quan trọng như sau:

| Dòng trong header | Ý nghĩa |
|---|---|
| `Received: by ...` | Địa chỉ mà từ đó tin nhắn được gửi (the address from which the message was sent) |
| `Received: from mail-sor-f41.google.com ...` | Ngày và giờ email được nhận bởi email server của bên gửi |
| `client-ip=209.85.220.41` | Sender's IP address (địa chỉ IP người gửi) |
| `Authentication-Results: mx.google.com` | Sender's mail server (mail server người gửi) |
| `DKIM-Signature: a=rsa-sha256` | Authentication system được mail server của người gửi sử dụng |
| `From: ...@gmail.com` | Sender's full name (họ tên đầy đủ người gửi) |
| `Date: Mon, 10 Jun 2019 ...` | Ngày và giờ tin nhắn được gửi |

Các trường liên quan khác xuất hiện trong header mẫu: `Delivered-To`, `Return-Path`, `Received-SPF: pass`, `spf=pass`, `dmarc=pass`, `MIME-Version: 1.0`, `Message-ID`, `Subject`, `To`.

---

## Email Tracking Tools

Các công cụ theo dõi email — như **eMailTrackerPro, Infoga, Mailtrack và PoliteMail** — cho phép kẻ tấn công theo dõi một email và trích xuất thông tin như **danh tính người gửi (sender identity), mail server, địa chỉ IP người gửi, vị trí (location)**, v.v.

Các công cụ này tự động gửi thông báo khi người nhận mở email và cung cấp thông tin trạng thái về việc email đã được gửi thành công hay chưa. Kẻ tấn công dùng thông tin trích xuất được để tấn công hệ thống của tổ chức mục tiêu bằng cách gửi email độc hại.

### Infoga

- **Source:** `https://github.com`

Infoga là công cụ dùng để **thu thập thông tin tài khoản email** (IP, hostname, country, v.v.) từ nhiều nguồn công khai khác nhau (search engine, pgp key server và Shodan), đồng thời kiểm tra xem một email có bị rò rỉ hay không qua API của `haveibeenpwned.com`.

Ví dụ, lệnh:

```
python infoga.py --domain microsoft.com --source all --breach -v 2 --report ../microsoft.txt
```

sẽ truy xuất tất cả địa chỉ email công khai liên quan đến tên miền `microsoft.com` cùng thông tin tài khoản email.

```
python infoga.py --info m4ll0k@protonmail.com --breach -v 3 --report ../m4ll0k.txt
```

Lệnh trên sẽ truy xuất thông tin tài khoản email cho một địa chỉ email cụ thể.

#### Các tùy chọn của Infoga (Figure 2.57)

| Tùy chọn | Ý nghĩa |
|---|---|
| `-d`, `--domain` | Target URL/Name (tên/URL mục tiêu) |
| `-s`, `--source` | Nguồn dữ liệu, mặc định "all" |
| | `all` — dùng tất cả search engine |
| | `google` — dùng Google search engine |
| | `bing` — dùng Bing search engine |
| | `ask` — dùng Ask search engine |
| | `yahoo` — dùng Yahoo search engine |
| | `baidu` — dùng Baidu search engine |
| | `dogpile` — dùng Dogpile search engine |
| | `exalead` — dùng Exalead search engine |
| | `pgp` — dùng PGP search engine |
| `-b`, `--breach` | Kiểm tra email có bị rò rỉ (breached) hay không |
| `-i`, `--info` | Lấy thông tin email |
| `-r`, `--report` | Báo cáo file text đơn giản |
| `-v`, `--verbose` | Mức độ chi tiết (1, 2 hoặc 3) |
| `-H`, `--help` | Hiển thị trợ giúp và thoát |

### eMailTrackerPro

- **Source:** `http://www.emailtrackerpro.com`

Kẻ tấn công dùng **eMailTrackerPro** để phân tích email header và trích xuất thông tin như **vị trí địa lý (geographical location), địa chỉ IP** của người gửi, v.v. Công cụ cho phép kẻ tấn công xem lại các lần truy vết (traces) sau này bằng cách lưu lại các trace trước đó.

Như minh họa trong screenshot (*Figure 2.58*), giao diện eMailTrackerPro hiển thị:

- **Map** — Bản đồ định vị vị trí địa lý của email (ví dụ: West Chester, Pennsylvania, USA).
- **Email Summary** — Tóm tắt thông tin: From, To, Date, Subject, Location, Abuse Address, Abuse Reporting, From IP.
- **System Information** — Thông tin hệ thống (ví dụ: hệ thống đang chạy mail server, web server, secure web server).
- Bảng **Hop / Hop IP / Hop Name / Location** — Liệt kê các chặng (hops) mà email đã đi qua.
- Các mục mở rộng: **Network Whois, Domain Whois, Email Header**.
