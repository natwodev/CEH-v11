# Footprinting through Search Engines

> Module 02 | Trang 10–29

## Giới thiệu

**Search engines** (công cụ tìm kiếm) là nguồn thông tin chính để khai thác các chi tiết quan trọng về tổ chức mục tiêu từ Internet. Search engine sử dụng phần mềm tự động (gọi là **crawler**) để liên tục quét các website đang hoạt động và thêm kết quả thu được vào chỉ mục (index) được lưu trong một cơ sở dữ liệu khổng lồ. Khi người dùng truy vấn, search engine trả về danh sách **Search Engine Results Pages (SERPs)** gồm trang web, video, hình ảnh và nhiều loại tệp khác nhau, được xếp hạng theo mức độ liên quan.

Kẻ tấn công có thể trích xuất thông tin về tổ chức mục tiêu như:

- Nền tảng công nghệ (technology platforms)
- Thông tin nhân viên (employee details)
- Trang đăng nhập (login pages)
- Cổng intranet (intranet portals)
- Thông tin liên hệ (contact information)

Thông tin này giúp kẻ tấn công thực hiện **social engineering** và các kiểu tấn công nâng cao khác. Ví dụ, một tìm kiếm Google có thể tiết lộ các bài đăng trên diễn đàn của nhân viên bảo mật, để lộ thương hiệu firewall hoặc phần mềm antivirus mà mục tiêu đang dùng — từ đó xác định lỗ hổng trong các biện pháp kiểm soát bảo mật.

**Ví dụ:** Gõ "Microsoft" vào ô **Search** và nhấn **Enter** sẽ hiển thị kết quả về Microsoft. Duyệt kết quả thường cung cấp thông tin quan trọng như vị trí địa lý, địa chỉ liên hệ, dịch vụ cung cấp, số lượng nhân viên, v.v.

**Các search engine lớn:** Google, Bing, Yahoo, Ask, Aol, Baidu, WolframAlpha, DuckDuckGo.

Search engine cũng được dùng để tìm các nguồn thông tin công khai khác. Ví dụ, gõ "top job portals" để tìm các cổng việc làm lớn cung cấp thông tin quan trọng về tổ chức mục tiêu.

> **Lưu ý (góc độ ethical hacker):** Nếu phát hiện trang/thông tin đã bị xóa về công ty của mình vẫn còn trong SERPs hoặc trong cache của search engine, bạn có thể yêu cầu search engine gỡ bỏ trang/thông tin đó khỏi cache đã lập chỉ mục.

---

## Footprinting bằng Advanced Google Hacking Techniques

**Google hacking** là việc sử dụng các toán tử tìm kiếm nâng cao (advanced search operators) của Google để tạo các truy vấn phức tạp nhằm trích xuất thông tin nhạy cảm hoặc ẩn, giúp kẻ tấn công **tìm các mục tiêu dễ bị khai thác (vulnerable targets)**.

Qua Google hacking, kẻ tấn công tìm các website có thể bị khai thác. Có thể dùng **Google Hacking Database (GHDB)** — một cơ sở dữ liệu các truy vấn — để xác định dữ liệu nhạy cảm. Các toán tử Google giúp tìm văn bản cần thiết và tránh dữ liệu không liên quan, định vị các chuỗi văn bản cụ thể như phiên bản ứng dụng web dễ bị tấn công.

Cú pháp dùng một advanced search operator:

```
operator: search_term
```

> **Note:** Không để khoảng trắng giữa toán tử và truy vấn.

> **Nguồn:** http://www.googleguide.com

### Các toán tử tìm kiếm nâng cao phổ biến của Google

| Toán tử | Mô tả |
|---|---|
| `[cache:]` | Hiển thị các trang web được lưu trong cache của Google |
| `[link:]` | Liệt kê các trang web có liên kết tới trang web được chỉ định |
| `[related:]` | Liệt kê các trang web tương tự với trang web được chỉ định |
| `[info:]` | Trình bày một số thông tin mà Google có về một trang web cụ thể |
| `[site:]` | Giới hạn kết quả về các website trong domain được chỉ định |
| `[allintitle:]` | Giới hạn kết quả về các trang chứa tất cả từ khóa tìm kiếm trong tiêu đề (title) |
| `[intitle:]` | Giới hạn kết quả về các tài liệu chứa từ khóa trong tiêu đề |
| `[allinurl:]` | Giới hạn kết quả về các trang chứa tất cả từ khóa trong URL |
| `[inurl:]` | Giới hạn kết quả về các tài liệu chứa từ khóa trong URL |
| `[location:]` | Tìm thông tin cho một vị trí cụ thể |

### Giải thích chi tiết từng toán tử

- **site**: Giới hạn kết quả tìm kiếm về site hoặc domain được chỉ định.
  - Ví dụ: `[games site: www.certifiedhacker.com]` cho thông tin về games từ site certifiedhacker.
- **allinurl**: Giới hạn kết quả về các trang chứa tất cả các từ trong URL.
  - Ví dụ: `[allinurl: google career]` trả về các trang chứa cả "google" và "career" trong URL.
- **inurl**: Giới hạn kết quả về các trang chứa từ được chỉ định trong URL.
  - Ví dụ: `[inurl: copy site:www.google.com]` trả về các trang Google mà URL có chứa từ "copy".
- **allintitle**: Giới hạn kết quả về các trang chứa tất cả các từ trong tiêu đề.
  - Ví dụ: `[allintitle: detect malware]` trả về các trang chứa cả "detect" và "malware" trong tiêu đề.
- **intitle**: Giới hạn kết quả về các trang chứa từ được chỉ định trong tiêu đề.
  - Ví dụ: `[malware detection intitle:help]` trả về các trang có "help" trong tiêu đề và "malware", "detection" ở bất kỳ đâu trong trang.
- **inanchor**: Giới hạn kết quả về các trang chứa từ tìm kiếm trong anchor text của liên kết tới trang.
  - Ví dụ: `[Anti-virus inanchor:Norton]` trả về các trang có anchor text chứa "Norton" và trang chứa từ "Anti-virus".
- **allinanchor**: Giới hạn kết quả về các trang chứa tất cả từ tìm kiếm trong anchor text của liên kết.
  - Ví dụ: `[allinanchor: best cloud service provider]` trả về các trang mà anchor text chứa các từ "best", "cloud", "service", "provider".
- **cache**: Hiển thị phiên bản cache của Google cho một trang thay vì phiên bản hiện tại.
  - Ví dụ: `[cache:www.eff.org]` hiển thị bản cache của trang chủ Electronic Frontier Foundation.
- **link**: Tìm các website/trang chứa liên kết tới website/trang được chỉ định.
  - Ví dụ: `[link:www.googleguide.com]` tìm các trang trỏ tới trang chủ Google Guide.
  - **Note:** Theo tài liệu của Google, "không thể kết hợp `link:` với tìm kiếm từ khóa thông thường." Ngoài ra, khi kết hợp `link:` với toán tử nâng cao khác, Google có thể không trả về tất cả các trang khớp.
- **related**: Hiển thị các website tương tự hoặc liên quan đến URL được chỉ định.
  - Ví dụ: `[related:www.microsoft.com]` cho các website tương tự microsoft.com.
- **info**: Tìm thông tin cho trang web được chỉ định.
  - Ví dụ: `[info:gothotel.com]` cung cấp thông tin về trang chủ danh bạ khách sạn GotHotel.com.
- **location**: Tìm thông tin cho một vị trí cụ thể.
  - Ví dụ: `[location: 4 seasons restaurant]` cho kết quả dựa trên cụm "4 seasons restaurant".
- **Filetype**: Cho phép tìm kết quả dựa trên phần mở rộng tệp.
  - Ví dụ: `[jasmine:jpg]` cung cấp các tệp jpg dựa trên jasmine.

---

## Kẻ tấn công có thể làm gì với Google Hacking?

Kẻ tấn công có thể tạo các truy vấn phức tạp để lọc lượng lớn kết quả và lấy thông tin liên quan đến bảo mật máy tính. Không chỉ phát hiện website/web server dễ bị tấn công, kẻ tấn công còn định vị thông tin nhạy cảm riêng tư như số thẻ tín dụng, số an sinh xã hội, mật khẩu, v.v. Khi xác định được site dễ bị tấn công, kẻ tấn công thử các tấn công như buffer overflow và SQL injection.

**Thông tin nhạy cảm trên public server mà kẻ tấn công có thể trích xuất bằng GHDB:**

- Thông báo lỗi (error messages) chứa thông tin nhạy cảm
- Tệp chứa mật khẩu
- Thư mục nhạy cảm (sensitive directories)
- Trang chứa cổng đăng nhập (logon portals)
- Trang chứa dữ liệu mạng hoặc lỗ hổng như log và cấu hình của IDS, firewall
- Cảnh báo (advisories) và lỗ hổng server
- Thông tin phiên bản phần mềm
- Mã nguồn ứng dụng web
- Thiết bị IoT kết nối và bảng điều khiển của chúng, nếu không được bảo vệ
- Trang web ẩn như dịch vụ intranet và VPN

**Ví dụ:** Dùng cú pháp toán tử nâng cao `[intitle:intranet inurl:intranet +intext:"human resources"]` để tìm thông tin nhạy cảm về tổ chức mục tiêu và nhân viên. Kẻ tấn công dùng thông tin thu được để thực hiện social engineering.

---

## Google Hacking Database (GHDB)

> **Nguồn:** https://www.exploit-db.com

**GHDB** là nguồn tham khảo có thẩm quyền để truy vấn phạm vi ngày càng mở rộng của Google search engine. Trong GHDB có các từ khóa tìm kiếm cho tệp chứa username, vulnerable server, và cả tệp chứa mật khẩu. **Exploit Database** là một kho lưu trữ tuân thủ CVE (Common Vulnerabilities and Exposures) các exploit công khai và phần mềm dễ bị tấn công tương ứng, dành cho penetration tester và nhà nghiên cứu lỗ hổng.

Dùng GHDB dorks, kẻ tấn công có thể nhanh chóng xác định mọi exploit và lỗ hổng công khai trong hạ tầng IT của mục tiêu. Kẻ tấn công dùng **Google dorks** trong các toán tử nâng cao để trích xuất thông tin nhạy cảm như vulnerable server, error messages, sensitive files, login pages và websites.

### Các danh mục trong GHDB

| | |
|---|---|
| Footholds | Files Containing Juicy Info |
| Files Containing Usernames | Files Containing Passwords |
| Sensitive Directories | Sensitive Online Shopping Info |
| Web Server Detection | Network or Vulnerability Data |
| Vulnerable Files | Pages Containing Login Portals |
| Vulnerable Servers | Various Online Devices |
| Error Messages | Advisories and Vulnerabilities |

---

## VoIP và VPN Footprinting qua GHDB

Google hacking dùng các toán tử nâng cao để khớp các chuỗi văn bản cụ thể trong kết quả tìm kiếm. Các toán tử này (Google dorks) giúp tinh chỉnh tìm kiếm để lộ thông tin nhạy cảm, lỗ hổng và mật khẩu. Có thể dùng để footprint mạng VoIP và VPN, trích xuất thông tin như trang chứa login portal, VoIP login portal, thư mục chứa key của VPN server, v.v.

### Bảng 2.1: Google search queries cho VoIP footprinting

| Google Dork | Mô tả |
|---|---|
| `intitle:"Login Page" intext:"Phone Adapter Configuration Utility"` | Trang chứa login portal |
| `inurl:/voice/advanced/ intitle:Linksys SPA configuration` | Tìm trang cấu hình router VoIP Linksys |
| `intitle:"D-Link VoIP Router" "Welcome"` | Trang chứa login portal D-Link |
| `intitle:asterisk.management.portal web-access` | Tìm Asterisk management portal |
| `intitle:"SPA504G Configuration"` | Tìm Cisco SPA504G Configuration Utility cho IP phone |
| `intitle:"Sipura.SPA.Configuration" -.pdf` | Tìm trang cấu hình cho thiết bị VoIP online |
| `intitle:asterisk.management.portal web-access` | Tìm Asterisk web management portal |
| `inurl:8080 intitle:"login" intext:"UserLogin" "English"` | VoIP login portals |

### Bảng 2.2: Google search queries cho VPN footprinting

| Google Dork | Mô tả |
|---|---|
| `filetype:pcf "cisco" "GroupPwd"` | Tệp Cisco VPN với Group Password cho remote access |
| `"[main]" "enc_GroupPwd=" ext:txt` | Tìm mật khẩu Cisco VPN client (mã hóa nhưng dễ bẻ khóa) |
| `"Config" intitle:"Index of" intext:vpn` | Thư mục chứa key của VPN server |
| `inurl:/remote/login?lang=en` | Tìm SSL-VPN login portal của FortiGate Firewall |
| `!Host=*.* intext:enc_UserPassword=* ext:pcf` | Tìm tệp cấu hình profile (.pcf) chứa user VPN profile |
| `filetype:rcf inurl:vpn` | Tìm tệp Sonicwall Global VPN Client chứa thông tin nhạy cảm và login |
| `filetype:pcf vpn OR Group` | Tìm các tệp .pcf công khai dùng bởi VPN client |
| `vpnssl` | Lấy login portal chứa quyền truy cập của các công ty dùng vpnssl |
| `intitle:"SSL VPN Service" + intext:"Your system administrator provided the following information to help understand and remedy the security conditions:"` | Tìm trang đăng nhập Cisco asa |

---

## Các kỹ thuật khác để Footprinting qua Search Engines

Kẻ tấn công không phải lúc nào cũng dễ dàng thu thập thông tin từ một site giàu thông tin chỉ bằng ô tìm kiếm thông thường. Một tìm kiếm phức tạp liên quan đến nhiều điều kiện ràng buộc lẫn nhau.

### 1. Google Advanced Search và Advanced Image Search

Tính năng Advanced Search của Google giúp thực hiện tìm kiếm web phức tạp. Với **Google Advanced Search** và **Advanced Image Search**, có thể tìm kiếm chính xác như khi dùng advanced operators nhưng **không cần gõ hoặc nhớ các toán tử**.

- Dùng Advanced Search để tìm các site có thể liên kết ngược về website của tổ chức mục tiêu → trích xuất thông tin về partner, vendor, client và các liên kết khác.
- Dùng Advanced Image Search để lấy hình ảnh về mục tiêu, vị trí, nhân viên, v.v.

**Cách thực hiện:** Nhấn **Settings** ở góc dưới-phải trang chủ Google rồi chọn **Advanced search**, hoặc gõ trực tiếp `https://www.google.com/advanced_search` vào thanh địa chỉ. Mặc định, các giá trị được nối với "and" (tất cả phải khớp), trừ các tập (sets), khối (blocks) và định dạng (formats) được nối với "or" (bất kỳ giá trị nào khớp).

Để tìm advanced image search: gõ `https://www.google.com/advanced_image_search`. Có thể tìm theo màu ảnh, domain, file type, kích thước, từ khóa, v.v.

### 2. Reverse Image Search

Để thực hiện reverse image search trong Google, gõ `https://www.google.com/imghp` vào thanh địa chỉ. Reverse image search cho phép dùng một hình ảnh làm truy vấn — có thể upload ảnh hoặc dán URL ảnh. Search engine kiểm tra chỉ mục và hiển thị mọi vị trí online của ảnh đó.

Reverse image search giúp kẻ tấn công truy tìm **nguồn gốc và chi tiết của ảnh** như ảnh chụp, ảnh đại diện và meme.

**Công cụ:** Google Image Search, TinEye Reverse Image Search, Yahoo Image Search, Bing Image Search.

### 3. Video Search Engines

Video search engine là search engine dựa trên Internet, crawl web để tìm nội dung video. Chúng hoặc cung cấp chức năng upload/host video trên server riêng, hoặc phân tích video được host bên ngoài. Nội dung video có giá trị cao để thu thập thông tin về mục tiêu.

**Công cụ:** YouTube, Google videos, Yahoo videos, Bing videos — cho phép tìm video theo định dạng và thời lượng.

Sau khi tìm video liên quan đến mục tiêu, kẻ tấn công có thể phân tích nội dung video để thu thập **thông tin ẩn** như thời gian/ngày (time/date) và thumbnail của video.

**Công cụ phân tích video:** YouTube DataViewer, EZGif, và VideoReverser.com — có thể đảo ngược video hoặc chuyển video thành văn bản và các định dạng khác để trích xuất thông tin quan trọng.

### 4. Meta Search Engines

Meta search engine sử dụng các search engine khác (Google, Bing, Ask.com, v.v.) để tạo kết quả riêng từ Internet trong thời gian rất ngắn. Chúng **không có chỉ mục riêng**; thay vào đó lấy truy vấn từ người dùng và đồng thời gửi tới các search engine bên thứ ba để lấy kết quả, sau đó xếp hạng theo độ liên quan và trình bày qua giao diện web. Meta search engine còn lọc bỏ kết quả trùng lặp (không hiển thị cùng kết quả hai lần) và cung cấp quyền riêng tư bằng cách **ẩn địa chỉ IP của người dùng**.

**Công cụ:** Startpage, MetaGer, eTools.ch — gửi nhiều truy vấn tới nhiều search engine cùng lúc và thu thập thông tin chi tiết như thông tin từ site mua sắm (Amazon, eBay, v.v.), images, videos, blogs, news và articles từ nhiều nguồn.

### 5. FTP Search Engines

FTP search engine được dùng để tìm các tệp nằm trên FTP server chứa thông tin có giá trị về tổ chức mục tiêu. Nhiều ngành, tổ chức, công ty và đại học dùng FTP server để lưu trữ kho file lớn và phần mềm chia sẻ giữa nhân viên. Client như **FileZilla** (`https://filezilla-project.org`) có thể truy cập tài khoản FTP, hỗ trợ upload, download và đổi tên tệp. Mặc dù FTP server thường được bảo vệ bằng mật khẩu, nhiều server bị bỏ ngỏ và có thể truy cập trực tiếp qua trình duyệt web.

**Công cụ:** NAPALM FTP Indexer, Global FTP Search Engine, FreewareWeb FTP File Search — tìm tệp/thư mục quan trọng chứa chiến lược kinh doanh, tài liệu thuế, hồ sơ cá nhân nhân viên, hồ sơ tài chính, phần mềm bản quyền và thông tin bí mật khác.

#### Bảng 2.3: Google search queries để tìm FTP server

| Google Dork | Mô tả |
|---|---|
| `inurl:github.com intext:.ftpconfig -issues` | Trả về thông tin đăng nhập SFTP/FTP server trên Github |
| `type:mil inurl:ftp ext:pdf \| ps` | Trả về thư mục nhạy cảm trên FTP |
| `intext:pure-ftpd.conf intitle:index of` | Trả về server để lộ tệp cấu hình pure-ftpd |
| `intitle:"Index Of" intext:sftp-config.json` | Trích xuất danh sách mật khẩu FTP/SFTP từ sublime text |
| `inurl:"ftp://www." "Index of /"` | Hiển thị các FTP server online khác nhau |
| `inurl:~/ftp://193 filetype:(php \| txt \| html \| asp \| xml \| cnf \| sh) ~'/html'` | Trả về danh sách FTP server theo IP, chủ yếu là server Windows NT có khả năng đăng nhập guest |

### 6. IoT Search Engines

IoT search engine crawl Internet để tìm các thiết bị IoT công khai. Qua tìm kiếm cơ bản, kẻ tấn công có thể giành quyền kiểm soát các hệ thống **SCADA (Supervisory Control and Data Acquisition)**, hệ thống điều khiển giao thông, thiết bị gia dụng kết nối Internet, thiết bị công nghiệp, camera CCTV, v.v. Nhiều thiết bị IoT không được bảo mật (không mật khẩu hoặc dùng credential mặc định) nên dễ bị khai thác.

**Công cụ:** Shodan, Censys, Thingful — lấy thông tin như chi tiết nhà sản xuất, vị trí địa lý, địa chỉ IP, hostname và open ports của thiết bị IoT mục tiêu. Từ đó kẻ tấn công có thể tạo back door vào thiết bị IoT và truy cập để tiến hành các tấn công tiếp theo.

Như minh họa trong tài liệu, kẻ tấn công dùng **Shodan** để tìm mọi thiết bị IoT của tổ chức mục tiêu đang có open ports và services. Trang chi tiết host của Shodan hiển thị Country, Organization, ISP, Last Update, ASN cùng danh sách **Ports** và **Services** đang mở của hệ thống SCADA.

---

## Tóm tắt nhanh

- Search engine là nguồn chính để trích xuất thông tin mục tiêu (công nghệ, nhân viên, login, intranet, liên hệ).
- Advanced Google operators (`site`, `inurl`, `intitle`, `cache`, `link`, `related`, `info`, `filetype`, v.v.) tạo truy vấn phức tạp để tìm dữ liệu nhạy cảm và mục tiêu dễ bị tấn công.
- **GHDB** (exploit-db.com) cung cấp Google dorks sẵn theo danh mục — kể cả dork chuyên cho **VoIP** và **VPN** footprinting.
- Các kỹ thuật khác: Google Advanced/Image Search, Reverse Image Search (TinEye), Video Search + công cụ phân tích (YouTube DataViewer, EZGif), Meta Search (Startpage, MetaGer), FTP Search (NAPALM), IoT Search (**Shodan**, Censys, Thingful) để lộ SCADA và open ports.
