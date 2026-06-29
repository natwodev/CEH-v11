# DNS Footprinting

> Module 02 | Trang 112–116

## Giới thiệu

Sau khi thu thập **Whois records** về mục tiêu, giai đoạn tiếp theo trong quy trình footprinting là **DNS footprinting**. Kẻ tấn công thực hiện DNS footprinting để thu thập thông tin về **DNS servers**, **DNS records** và **các loại server** mà tổ chức mục tiêu sử dụng. Thông tin này giúp xác định các host quan trọng kết nối trong mạng và phục vụ khai thác sâu hơn.

Phần này mô tả:

- Cách trích xuất thông tin DNS
- Reverse DNS lookup
- Thu thập thông tin từ DNS zone transfer
- Các công cụ DNS interrogation

---

## Extracting DNS Information

DNS footprinting tiết lộ thông tin về **DNS zone data**. DNS zone data bao gồm tên miền DNS, tên máy tính, địa chỉ IP và nhiều thông tin khác về một mạng.

- Kẻ tấn công dùng thông tin DNS để **xác định các host chủ chốt** trong mạng, sau đó thực hiện tấn công **social engineering** để thu thập thêm thông tin.
- DNS records cung cấp thông tin quan trọng về **vị trí và loại server**.

DNS footprinting giúp xác định các loại bản ghi (record) sau về DNS mục tiêu:

| Record Type | Mô tả |
|-------------|-------|
| **A** | Trỏ đến địa chỉ IP của một host |
| **MX** | Trỏ đến mail server của domain |
| **NS** | Trỏ đến name server của host |
| **CNAME** | Đặt bí danh (alias) cho một host (canonical naming) |
| **SOA** | Chỉ định authority (thẩm quyền) cho một domain |
| **SRV** | Service records (bản ghi dịch vụ) |
| **PTR** | Ánh xạ địa chỉ IP về một hostname |
| **RP** | Responsible person (người chịu trách nhiệm) |
| **HINFO** | Host information record — bao gồm loại CPU và OS |
| **TXT** | Bản ghi văn bản phi cấu trúc (unstructured text records) |

*Table 2.7: DNS records and their description*

---

## DNS Interrogation Tools

Các công cụ DNS interrogation như **Professional Toolset** (`https://tools.dnsstuff.com`) và **DNS Records** (`https://network-tools.com`) cho phép người dùng thực hiện DNS footprinting.

- **DNSstuff (Professional Toolset)** trích xuất thông tin DNS về địa chỉ IP, mail server extensions, DNS lookups, Whois lookups, v.v. Có thể trích xuất một dải địa chỉ IP bằng IP routing lookup.
- Nếu mạng mục tiêu cho phép người dùng **không xác định, không được ủy quyền** thực hiện DNS zone transfer, kẻ tấn công dễ dàng lấy được thông tin DNS qua công cụ interrogation.

Khi kẻ tấn công truy vấn DNS server bằng công cụ interrogation, server trả về một **record structure** chứa thông tin về DNS mục tiêu. DNS records cung cấp thông tin quan trọng về vị trí và loại server.

Kẻ tấn công cũng dùng các công cụ DNS lookup như **DNSdumpster.com**, **Bluto** và **Domain Dossier** để truy xuất DNS records cho một domain hoặc hostname cụ thể. Các công cụ này lấy về thông tin như domain và địa chỉ IP, domain Whois records, DNS records và network Whois records.

*Figure 2.62: Screenshot of Professional Toolset — DNSreport Results for certifiedhacker.com (FAIL: 2, WARNING: 0, PASS: 17, INFO: 4).*

---

## Reverse DNS Lookup

**DNS lookup** dùng để tìm địa chỉ IP cho một tên miền cho trước, còn **reverse DNS** được thực hiện để lấy tên miền của một địa chỉ IP cho trước.

- Khi tìm một domain và gõ tên miền vào trình duyệt, DNS chuyển tên miền đó thành địa chỉ IP và chuyển tiếp yêu cầu để xử lý. Việc chuyển đổi tên miền thành IP được thực hiện bởi một record.
- Kẻ tấn công thực hiện reverse DNS lookup trên một **dải IP** để định vị **DNS PTR record** cho các địa chỉ IP đó.
- Các công cụ thường dùng: **DNSRecon** và **Reverse IP Domain Check**. Khi có một địa chỉ IP hoặc một dải IP, có thể dùng các công cụ này để lấy tên miền.

### DNSRecon

Nguồn: `https://github.com`

Kẻ tấn công dùng lệnh sau để thực hiện reverse DNS lookup trên host mục tiêu:

```
dnsrecon -r 162.241.216.0-162.241.216.255
```

Trong lệnh trên, tùy chọn `-r` chỉ định **dải địa chỉ IP** (first-last) để reverse lookup bằng phương pháp **brute force**.

*Figure 2.63: Screenshot of DNSRecon showing reverse DNS lookup information — kết quả trả về các PTR record ánh xạ IP về hostname, ví dụ `162-241-216-5.unifiedlayer.com → 162.241.216.5`, `box5331.bluehost.com → 162.241.216.11`.*

---

## Reverse IP Domain Check

Kẻ tấn công cũng tìm các domain khác **dùng chung một web server** bằng công cụ như **Reverse IP Domain Check**. Công cụ này liệt kê các domain có khả năng đang được host trên cùng một web server.

### Reverse IP Domain Check

Nguồn: `https://www.yougetsignal.com`

Một reverse IP domain check nhận vào một tên miền hoặc địa chỉ IP trỏ đến web server và tìm kiếm các site khác được biết là host trên cùng web server đó.

- Dữ liệu được thu thập từ kết quả của search engine, **không đảm bảo đầy đủ**.
- Hữu ích từ cả góc độ **SEO** lẫn **web filtering**, đặc biệt với các plan **shared web hosting**.

*Figure 2.64: Screenshot of Reverse IP Domain Check — ví dụ với `www.certifiedhacker.com` tìm thấy 7 domain host trên cùng web server (162.241.216.11): bongekile.com, certifiedhacker.com, oakoffer.com, www.lststl.org, box5331.bluehost.com, humancarehealth.com, www.certifiedhacker.com.*
