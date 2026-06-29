# Whois Footprinting

> Module 02 | Trang 106–111

## Giới thiệu

Thu thập thông tin liên quan đến mạng (network-related) như thông tin **Whois** về tổ chức mục tiêu là việc quan trọng khi lập kế hoạch tấn công. Whois footprinting giúp thu thập thông tin tên miền như chủ sở hữu của tổ chức, nhà đăng ký (registrar), chi tiết đăng ký, name server và thông tin liên hệ.

Phần này tập trung vào cách:

- Thực hiện một Whois lookup
- Phân tích kết quả Whois lookup
- Tìm thông tin IP geolocation
- Các công cụ dùng để thu thập thông tin Whois

---

## Whois Lookup

**Whois** là một giao thức truy vấn và phản hồi (query and response protocol) dùng để truy vấn các cơ sở dữ liệu lưu trữ thông tin về người dùng đã đăng ký hoặc người được cấp (assignees) một tài nguyên Internet — như tên miền, một khối địa chỉ IP, hoặc một autonomous system. Giao thức này lắng nghe các yêu cầu trên **port 43 (TCP)**.

Các **Regional Internet Registries (RIRs)** duy trì các cơ sở dữ liệu Whois, chứa **thông tin cá nhân của chủ sở hữu tên miền**. Với mỗi tài nguyên, cơ sở dữ liệu Whois cung cấp các bản ghi văn bản (text records) chứa thông tin về chính tài nguyên đó cùng các thông tin liên quan về assignees, registrants và thông tin quản trị (ngày tạo và ngày hết hạn).

### Hai mô hình dữ liệu Whois

Tồn tại hai loại mô hình dữ liệu để lưu trữ và tra cứu thông tin Whois:

- **Thick Whois** — Lưu trữ **toàn bộ** thông tin Whois từ tất cả các registrar cho một tập dữ liệu cụ thể.
- **Thin Whois** — Chỉ lưu trữ **tên của Whois server** của registrar quản lý một tên miền; server này sau đó nắm giữ thông tin đầy đủ về dữ liệu được tra cứu.

### Thông tin Whois query trả về

Một truy vấn Whois trả về các thông tin sau:

- Domain name details (chi tiết tên miền)
- Contact details of the domain owner (thông tin liên hệ của chủ sở hữu tên miền)
- Domain name servers
- NetRange
- When a domain has been created (thời điểm tên miền được tạo)
- Expiry records (bản ghi hết hạn)
- Records last updated (bản ghi cập nhật gần nhất)

Kẻ tấn công truy vấn một Whois database server để lấy thông tin về tên miền mục tiêu, thông tin liên hệ của chủ sở hữu, ngày hết hạn, ngày tạo, v.v. Whois server phản hồi truy vấn với thông tin được yêu cầu. Dùng thông tin này, kẻ tấn công có thể:

- Tạo bản đồ (map) mạng của tổ chức
- Đánh lừa chủ sở hữu tên miền bằng social engineering
- Thu thập thông tin nội bộ chi tiết của mạng

---

## Regional Internet Registries (RIRs)

Có 5 Regional Internet Registries quản lý việc phân bổ tài nguyên Internet theo từng khu vực địa lý:

| RIR | Tên đầy đủ | Khu vực | Website |
|-----|-----------|---------|---------|
| **ARIN** | American Registry for Internet Numbers | Bắc Mỹ | https://www.arin.net |
| **AFRINIC** | African Network Information Center | Châu Phi | https://www.afrinic.net |
| **APNIC** | Asia Pacific Network Information Center | Châu Á – Thái Bình Dương | https://www.apnic.net |
| **RIPE** | Réseaux IP Européens Network Coordination Centre | Châu Âu | https://www.ripe.net |
| **LACNIC** | Latin American and Caribbean Network Information Center | Mỹ Latinh và vùng Caribbean | https://www.lacnic.net |

---

## Whois Lookup Result

Các dịch vụ Whois như **http://whois.domaintools.com** hoặc **https://www.tamos.com** có thể giúp thực hiện Whois lookup. Các dịch vụ này thực hiện Whois lookup bằng cách nhập tên miền hoặc địa chỉ IP của mục tiêu.

- Dịch vụ **domaintools.com** cung cấp thông tin Whois như thông tin registrant, email, thông tin liên hệ quản trị, ngày tạo và ngày hết hạn, cùng danh sách domain server.
- **SmartWhois** (tại http://www.tamos.com) cung cấp thông tin về một địa chỉ IP, hostname hoặc tên miền, bao gồm thông tin về country, state hoặc province, city, số điện thoại, số fax, tên nhà cung cấp mạng (network provider), thông tin liên hệ quản trị (administrator) và hỗ trợ kỹ thuật (technical support). Nó còn giúp tìm chủ sở hữu tên miền, thông tin liên hệ của chủ sở hữu, chủ sở hữu khối địa chỉ IP, ngày đăng ký tên miền, v.v. SmartWhois hỗ trợ **Internationalized Domain Names (IDNs)** — cho phép truy vấn các tên miền dùng ký tự không phải tiếng Anh — và hỗ trợ cả địa chỉ **IPv6**.

### Ví dụ Whois Record cho CertifiedHacker.com

Theo screenshot (Figure 2.59), một Whois record bao gồm các trường tiêu biểu:

| Trường | Giá trị mẫu |
|--------|-------------|
| Registrant | PERFECT PRIVACY, LLC |
| Registrant Country | us |
| Registrar | NETWORK SOLUTIONS, LLC (IANA ID: 2 — whois.networksolutions.com) |
| Registrar Status | clientTransferProhibited |
| Dates | Created on 2002-07-29 / Expires on 2021-07-29 / Updated on 2018-08-22 |
| Name Servers | NS1.BLUEHOST.COM, NS2.BLUEHOST.COM |
| Tech Contact | PERFECT PRIVACY, LLC — Jacksonville, FL, 32258, us |
| IP Address | 162.241.216.11 |
| IP Location | Utah – Provo – Unified Layer |
| ASN | AS46606 UNIFIEDLAYER-AS-1 (US, registered Oct 24, 2008) |
| Domain Status | Registered And Active Website |
| IP History | 13 changes on 13 unique IP addresses over 13 years |
| Registrar History | 3 registrars with 2 drops |
| Hosting History | 6 changes on 4 unique name servers over 16 years |

> Các giá trị trên là dữ liệu minh họa từ tài liệu, không phản ánh trạng thái hiện tại của tên miền.

---

## Whois Lookup Tools

Kẻ tấn công sử dụng các công cụ Whois lookup để trích xuất thông tin như địa chỉ IP, hostname hoặc tên miền, thông tin registrant và DNS records — bao gồm country, city, state, số điện thoại và fax, network service provider, administrator và technical support — cho bất kỳ địa chỉ IP hay tên miền nào.

Các công cụ tiêu biểu:

- **DomainTools** (http://whois.domaintools.com)
- **SmartWhois** (http://www.tamos.com)
- **Batch IP Converter**
- **WhoIs Analyzer Pro**
- **ActiveWhois**

---

## Finding IP Geolocation Information

**IP geolocation** giúp thu thập thông tin về mục tiêu như: country, region/state, city, latitude và longitude của thành phố, ZIP/postal code, time zone, **connection speed**, **ISP (hosting company)**, domain name, IDD country code, area code, weather station code và name, mobile carrier, và elevation.

Dùng thông tin từ IP geolocation, kẻ tấn công có thể thu thập thêm thông tin về mục tiêu nhờ social engineering, surveillance, và các tấn công phi kỹ thuật như dumpster diving, hoaxing, hoặc đóng vai chuyên gia kỹ thuật. Kẻ tấn công cũng có thể:

- Dựng một web server bị xâm nhập gần vị trí của nạn nhân
- Khi xác định được vị trí chính xác của nạn nhân, thực hiện hành vi độc hại và lây nhiễm malware được thiết kế cho khu vực cụ thể đó
- Truy cập trái phép thiết bị mục tiêu hoặc dùng thiết bị mục tiêu để phát động tấn công

Các công cụ IP geolocation lookup như **IP2Location**, **IP Location Finder**, và **IP Address Geographical Location Finder** giúp thu thập thông tin IP geolocation về mục tiêu, từ đó hỗ trợ kẻ tấn công **phát động các tấn công social engineering** như spamming và phishing.

### IP Geolocation Lookup Tools

#### IP2Location

Source: https://www.ip2location.com

Như minh họa trong screenshot, kẻ tấn công dùng công cụ IP2Location để xác định vị trí địa lý của một visitor — gồm country, region, city, latitude và longitude của city, ZIP code, time zone, connection speed, ISP, domain name, IDD country code, area code, weather station code và name, mobile carrier, elevation, và usage type — bằng cơ sở dữ liệu tra cứu địa chỉ IP và công nghệ độc quyền (proprietary).

Ví dụ kết quả IP2Location (Figure 2.61):

| Trường | Giá trị mẫu |
|--------|-------------|
| IP Address | 207.46.232.182 |
| Country | Singapore [SG] |
| Region | Singapore |
| City | Singapore |
| Coordinates of City | 1.289670, 103.850070 (1°17'23"N 103°51'0"E) |
| ISP | Microsoft Corporation |
| Local Time | 10 Jun, 2019 07:10 PM (UTC +08:00) |
| Domain | microsoft.com |
| Net Speed | (COMP) Company/T1 |
| IDD & Area Code | (65) 06 |
| ZIP Code | 179431 |
| Weather Station | Singapore (SNXX0006) |

---

## Tóm tắt

- **Whois** là giao thức truy vấn/phản hồi trên **port 43 (TCP)**, dùng để tra cứu thông tin người đăng ký tài nguyên Internet.
- Có hai mô hình dữ liệu: **Thick Whois** (lưu toàn bộ thông tin) và **Thin Whois** (chỉ lưu tên Whois server của registrar).
- **5 RIRs**: ARIN, AFRINIC, APNIC, RIPE, LACNIC — mỗi RIR quản lý một khu vực địa lý.
- Công cụ Whois: **DomainTools**, **SmartWhois**, Batch IP Converter, WhoIs Analyzer Pro, ActiveWhois.
- **IP geolocation** (qua **IP2Location**, IP Location Finder, …) bổ sung dữ liệu vị trí địa lý, hỗ trợ tấn công social engineering như spamming và phishing.
