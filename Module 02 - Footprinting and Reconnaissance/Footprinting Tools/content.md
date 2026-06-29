# Footprinting Tools

> Module 02 | Trang 131–140

## Giới thiệu

Đây là phần thứ **3** trong luồng của Module 02 (Footprinting Tools), sau Footprinting Concepts và Footprinting Methodology, và trước Footprinting Countermeasures.

Nhiều công cụ hỗ trợ kẻ tấn công trong quá trình footprinting. Nhiều tổ chức cung cấp các công cụ giúp việc thu thập thông tin trở nên dễ dàng. Phần này mô tả các công cụ dùng để thu thập thông tin từ nhiều nguồn khác nhau.

**Footprinting tools** được dùng để thu thập thông tin cơ bản về hệ thống mục tiêu nhằm khai thác chúng. Thông tin thu thập được bao gồm:

- IP location, routing information (thông tin định tuyến)
- Business information, địa chỉ, số điện thoại, social security number
- Chi tiết về nguồn của email và tài liệu (file)
- DNS information, domain information, v.v.

---

## Bảng tổng hợp công cụ

| Công cụ | Nguồn | Mục đích chính |
|---------|-------|----------------|
| **Maltego** | paterva.com | Xác định mối quan hệ và liên kết thực tế giữa người, nhóm người, tổ chức, website, hạ tầng Internet, tài liệu… |
| **Recon-ng** | github.com | Web reconnaissance framework với các module độc lập tương tác cơ sở dữ liệu; trinh sát open-source dựa trên web |
| **FOCA** | elevenpaths.com | Tìm metadata và thông tin ẩn trong các tài liệu mà nó quét |
| **OSRFramework** | github.com | Kiểm tra username, DNS lookup, nghiên cứu rò rỉ thông tin, deep web search, trích xuất regular expression |
| **OSINT Framework** | osintframework.com | Framework thu thập open source intelligence từ các công cụ/tài nguyên miễn phí; giao diện web dạng cây OSINT |
| **Recon-Dog** | github.com | Công cụ all-in-one cho nhu cầu thu thập thông tin cơ bản; dùng API để thu thập thông tin về hệ thống mục tiêu |
| **BillCipher** | github.com | Thu thập thông tin cho website hoặc địa chỉ IP |
| **theHarvester** | edge-security.com | Công cụ footprinting bổ sung |
| **Th3inspector** | github.com | Công cụ footprinting bổ sung |
| **Raccoon** | github.com | Công cụ footprinting bổ sung |
| **Orb** | github.com | Công cụ footprinting bổ sung |
| **PENTMENU** | github.com | Công cụ footprinting bổ sung |

---

## Maltego

> Nguồn: https://www.paterva.com

Maltego là chương trình dùng để xác định **mối quan hệ và liên kết thực tế (relationships and real-world links)** giữa con người, nhóm người, tổ chức, website, hạ tầng Internet, tài liệu, v.v.

Kẻ tấn công có thể dùng các **entity** khác nhau có sẵn trong công cụ để thu thập thông tin như:

- Địa chỉ email
- Danh sách số điện thoại
- Hạ tầng Internet của mục tiêu (domains, DNS names, Netblocks, thông tin IP address)

Như trong ảnh chụp màn hình, kẻ tấn công thêm một **Person entity**, đổi tên thành tên của mục tiêu, và thu được các địa chỉ email liên kết với mục tiêu đó.

*Figure 2.73 — Screenshot of Maltego (Community Edition 4.1.6): thêm Person entity "John Doe" để nhắm vào một cá nhân, và thu được các địa chỉ email của mục tiêu.*

---

## Recon-ng

> Nguồn: https://github.com

Recon-ng là một **web reconnaissance framework** với các module độc lập để tương tác cơ sở dữ liệu, cung cấp một môi trường để thực hiện trinh sát open-source dựa trên web.

Như trong ảnh chụp màn hình, kẻ tấn công dùng module `recon/domains-hosts/hackertarget` để trích xuất danh sách **subdomains** và **IP addresses** liên kết với URL mục tiêu.

Các bước trong ví dụ:

```
[recon-ng][default] > modules load recon/domains-hosts/hackertarget
[recon-ng][default][hackertarget] > options set SOURCE certifiedhacker.com
SOURCE => certifiedhacker.com
[recon-ng][default][hackertarget] > run
```

- `modules load …` — nạp module
- `options set SOURCE …` — nhập URL mục tiêu
- `run` — thực thi truy vấn → thu được danh sách subdomains và IP của chúng (ví dụ: soc, itf, blog, webdisk, cpanel, mail, webmail, iam, pstn, sftp, trustcenter… của certifiedhacker.com, đều trỏ về 162.241.216.11)

*Figure 2.74 — Screenshot of recon-ng (Parrot Terminal).*

---

## FOCA

> Nguồn: https://www.elevenpaths.com

**FOCA (Fingerprinting Organizations with Collected Archives)** là công cụ dùng chủ yếu để tìm **metadata** và **thông tin ẩn** trong các tài liệu mà nó quét. FOCA có khả năng quét và phân tích nhiều loại tài liệu, phổ biến nhất là Microsoft Office, Open Office, hoặc file PDF.

### Features

- **Web Search** — Tìm hosts và domain names qua các URL liên kết với main domain. Mỗi link được phân tích để trích xuất thông tin từ host và domain name mới.
- **DNS Search** — Kiểm tra mỗi domain để xác định host name được cấu hình trong các máy chủ NS, MX và SPF nhằm phát hiện host/domain name mới.
- **IP Resolution** — Phân giải mỗi host name (bằng cách so sánh với DNS) để lấy IP address liên kết với server name đó. Để chính xác, công cụ phân tích dựa trên DNS nội bộ của tổ chức.
- **PTR Scanning** — Tìm thêm máy chủ trong cùng phân đoạn (segment) của một địa chỉ xác định; FOCA thực hiện PTR log scan.
- **Bing IP** — Khởi chạy FOCA tìm domain names mới liên kết với mỗi IP address được phát hiện.
- **Common Names** — Thực hiện tấn công từ điển (dictionary attack) nhắm vào DNS.

Như trong ảnh chụp màn hình, kẻ tấn công tìm kiếm domain mục tiêu và thu được thông tin file lưu trong đó. Các file trích xuất có thể xem trên trình duyệt web. Hơn nữa, kẻ tấn công có thể xem thêm thông tin như network domains, roles, vulnerabilities và metadata của domain mục tiêu.

*Figure 2.75 — Screenshot of FOCA (final version 3.4): cây thông tin Network, Domains, Roles, Vulnerabilities, Metadata của domain mục tiêu.*

---

## OSRFramework

> Nguồn: https://github.com

**OSRFramework** bao gồm các ứng dụng liên quan đến: kiểm tra username, DNS lookups, nghiên cứu rò rỉ thông tin (information leaks research), deep web search, và trích xuất regular expression.

Các công cụ trong gói OSRFramework mà kẻ tấn công có thể dùng để thu thập thông tin về mục tiêu:

- `usufy.py` — Kiểm tra user profile trên tối đa **290** nền tảng khác nhau
- `mailfy.py` — Kiểm tra sự tồn tại của một email cho trước
- `searchfy.py` — Thực hiện truy vấn trên các nền tảng trong OSRFramework
- `domainfy.py` — Kiểm tra sự tồn tại của domains
- `phonefy.py` — Kiểm tra sự tồn tại của một dãy số điện thoại cho trước
- `entify.py` — Dùng regular expression để trích xuất entities

Ví dụ lệnh tìm một user mục tiêu trên các nền tảng mạng xã hội:

```
usufy.py -n Mark Zuckerberg -p twitter facebook youtube
```

*Figure 2.76 — Screenshot of OSRFramework (Parrot Terminal): kết quả trả về profile trên Facebook, Youtube, Twitter cùng i3visio_uri, i3visio_alias, i3visio_platform.*

---

## OSINT Framework

> Nguồn: https://osintframework.com

**OSINT Framework** là một framework thu thập **open source intelligence** giúp các chuyên gia bảo mật thực hiện footprinting và reconnaissance tự động, nghiên cứu OSINT và thu thập intelligence. Nó tập trung vào việc thu thập thông tin từ các công cụ hoặc tài nguyên **miễn phí**.

Framework cung cấp một giao diện web đơn giản liệt kê nhiều công cụ OSINT được sắp xếp theo **category (danh mục)**, hiển thị dưới dạng **cây OSINT (OSINT tree structure)** trên giao diện web.

Các chỉ báo (indicators) trong danh sách công cụ:

- **(T)** — Cho biết link đến một công cụ phải được cài đặt và chạy cục bộ (locally)
- **(D)** — Google Dork
- **(R)** — Yêu cầu đăng ký (requires registration)
- **(M)** — Cho biết một URL chứa search term và URL đó phải được chỉnh sửa thủ công

*Figure 2.77 — Screenshot of OSINT Framework: cây phân loại theo Username, Email Address, Domain Name, IP Address, Images/Videos/Docs, Social Networks, Dark Web, Threat Intelligence, v.v.*

---

## Recon-Dog

> Nguồn: https://www.github.com

**Recon-Dog** là công cụ **all-in-one** cho mọi nhu cầu thu thập thông tin cơ bản. Nó dùng **API** để thu thập thông tin về hệ thống mục tiêu.

### Features

- **Censys** — Dùng censys.io để thu thập lượng lớn thông tin về một IP address
- **NS lookup** — Thực hiện name server lookup
- **Port scan** — Quét các cổng TCP phổ biến nhất
- **Detect CMS** — Có thể phát hiện hơn **400+** content management systems
- **Whois lookup** — Thực hiện Whois lookup
- **Detect honeypot** — Dùng shodan.io để kiểm tra mục tiêu có phải honeypot không
- **Find subdomains** — Dùng findsubdomains.com để tìm subdomains
- **Reverse IP lookup** — Thực hiện reverse IP lookup để tìm các domains liên kết với một IP address
- **Detect technologies** — Dùng wappalyzer.com để phát hiện hơn **1000+** technologies
- **All** — Chạy tất cả tiện ích trên mục tiêu

*Figure 2.78 — Screenshot of Recon-Dog (v2.0, Parrot Terminal): menu lựa chọn 1–0 và kết quả Whois lookup cho certifiedhacker.com.*

---

## BillCipher

> Nguồn: https://www.github.com

**BillCipher** là công cụ thu thập thông tin cho một **website hoặc địa chỉ IP**. Nó có thể chạy trên bất kỳ hệ điều hành nào hỗ trợ **Python 2, Python 3, và Ruby**.

Công cụ này bao gồm nhiều tùy chọn như: DNS lookup, Whois lookup, port scanning, zone transfer, host finder, và reverse IP lookup — giúp thu thập thông tin quan trọng.

Một số tùy chọn trong menu (1–22):

| | |
|---|---|
| DNS Lookup | Host DNS Finder |
| Whois Lookup | Reserve IP Lookup |
| GeoIP Lookup | Email Gathering (use Infoga) |
| Subnet Lookup | Subdomain listing (use Sublist3r) |
| Port Scanner | Find Admin login site (use Breacher) |
| Page Links | Check and Bypass CloudFlare (use HatCloud) |
| Zone Transfer | Website Copier (use httrack) |
| HTTP Header | Host Info Scanner (use WhatWeb) |
| Host Finder | About BillCipher |
| IP-Locator | Exit |
| Find Shared DNS Servers | |
| Get Robots.txt | |

*Figure 2.79 — Screenshot of BillCipher (v2.3, Parrot Terminal): "Information Gathering tool for a Website or IP address".*

---

## Các công cụ footprinting bổ sung

- **theHarvester** — http://www.edge-security.com
- **Th3inspector** — https://github.com
- **Raccoon** — https://github.com
- **Orb** — https://github.com
- **PENTMENU** — https://github.com
