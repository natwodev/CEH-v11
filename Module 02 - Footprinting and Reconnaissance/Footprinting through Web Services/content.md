# Footprinting through Web Services

> Module 02 | Trang 30–70

## Giới thiệu

Các **dịch vụ web** (web services) như people search, internet archive, mạng xã hội, dịch vụ cảnh báo (alerting), dịch vụ tài chính và trang tuyển dụng có thể cung cấp nhiều thông tin nhạy cảm về mục tiêu: chi tiết hạ tầng, vị trí địa lý, thông tin nhân viên… Các group, forum và blog cũng giúp kẻ tấn công thu thập thông tin mạng công khai, thông tin hệ thống và thông tin cá nhân.

Phần này hướng đến việc tìm hiểu:

- Tìm **top-level domain (TLD)** và **sub-domain** của công ty mục tiêu
- Tìm **vị trí địa lý** của mục tiêu
- **People search** trên mạng xã hội và dịch vụ tra cứu người
- Thu thập thông tin từ **trang tuyển dụng**, **dịch vụ tài chính**, kho dữ liệu bên thứ ba
- Footprinting trên **deep web / dark web**
- Xác định **hệ điều hành**
- Footprinting **VoIP / VPN** qua Shodan
- Thu thập **competitive intelligence** (tình báo cạnh tranh)

---

## Finding a Company's TLDs and Sub-domains

TLD và sub-domain của công ty cung cấp lượng lớn thông tin hữu ích cho kẻ tấn công. Một website công khai được thiết kế để giới thiệu sự hiện diện của tổ chức trên Internet, thu hút khách hàng và đối tác, thường chứa lịch sử tổ chức, dịch vụ/sản phẩm và thông tin liên hệ. URL bên ngoài của tổ chức có thể tìm bằng các search engine như **Google** và **Bing**.

**Sub-domain** chỉ dành cho một số ít người (nhân viên hoặc thành viên một bộ phận). Quản trị viên thường tạo sub-domain để **thử nghiệm công nghệ mới** trước khi triển khai chính thức; do đó các sub-domain này thường còn ở giai đoạn test, kém an toàn và dễ bị khai thác. Sub-domain cung cấp insight về các phòng ban, đơn vị kinh doanh và có thể lộ thông tin quan trọng như mã nguồn website hoặc tài liệu trên webserver.

Phần lớn tổ chức dùng định dạng phổ biến cho sub-domain, nên hacker biết URL bên ngoài thường có thể tìm ra sub-domain bằng **thử-và-sai (trial and error)** hoặc dịch vụ như **Netcraft**, hoặc script Python **Sublist3r**.

### Google Advanced Search Operator

Có thể dùng toán tử tìm kiếm nâng cao của Google để liệt kê sub-domain của mục tiêu:

| Mục đích | Cú pháp |
|---|---|
| Tìm các domain do một công ty sở hữu | `domains owned by microsoft` |
| Liệt kê tất cả sub-domain (loại trừ www) | `site:microsoft.com -inurl:www` |

### Tools to Search Company's Sub-domains

| Công cụ | Nguồn | Mô tả |
|---|---|---|
| **Netcraft** | https://www.netcraft.com | Dịch vụ bảo mật Internet: chống lừa đảo/phishing, kiểm thử ứng dụng, PCI scanning. Phân tích thị phần web server, OS, hosting provider, SSL CA. Lấy toàn bộ sub-domain liên quan domain mục tiêu. |
| **Sublist3r** | https://github.com | Script Python liệt kê sub-domain bằng OSINT từ nhiều nguồn cùng lúc. |
| **Pentest-Tools Find Subdomains** | https://pentest-tools.com | Công cụ online tìm sub-domain và IP, thông tin mạng và HTTP server. |

#### Netcraft

Như ảnh minh họa (Hostnames matching `*.microsoft.com`), Netcraft hiển thị danh sách sub-domain kèm thông tin: **Site, First seen, Netblock, OS, Site Report**. Ví dụ: `social.technet.microsoft.com` (Akamai Technologies, Linux), `examregistration.microsoft.com` (Microsoft Corporation, Windows Server 2016)…

#### Sublist3r

Sublist3r liệt kê sub-domain bằng nhiều search engine như **Google, Yahoo, Bing, Baidu, Ask**, đồng thời dùng **Netcraft, VirusTotal, ThreatCrowd, DNSdumpster và ReverseDNS**.

**Cú pháp:**

```
sublist3r [-d DOMAIN] [-b BRUTEFORCE] [-p PORTS] [-v VERBOSE][-t THREADS] [-e ENGINES] [-o OUTPUT]
```

| Short Form | Long Form | Mô tả |
|---|---|---|
| -d | --domain | Tên domain cần liệt kê sub-domain |
| -b | --bruteforce | Bật module subbrute bruteforce |
| -p | --ports | Quét các sub-domain tìm được trên cổng TCP cụ thể |
| -v | --verbose | Bật chế độ verbose, hiển thị kết quả real-time |
| -t | --threads | Số thread dùng cho subbrute bruteforce |
| -e | --engines | Chỉ định danh sách search engine (phân tách bằng dấu phẩy) |
| -o | --output | Lưu kết quả ra file text |
| -h | --help | Hiển thị trợ giúp và thoát |

**Ví dụ 1** – liệt kê sub-domain từ nhiều nguồn:

```
sublist3r -d google.com
```

**Ví dụ 2** – liệt kê sub-domain có cổng cụ thể đang mở (cổng 80 qua Bing):

```
sublist3r -d google.com -p 80 -e Bing
```

#### Pentest-Tools Find Subdomains

Tìm sub-domain liên quan domain mục tiêu (vd `microsoft.com`) để lấy thông tin quan trọng: **sub-domain, IP address, OS, server, technology, web platform, page title**. Ví dụ ảnh minh họa tìm được 117 sub-domain của microsoft.com.

---

## Finding the Geographical Location of the Target

Vị trí vật lý của tổ chức đóng vai trò quan trọng trong quá trình hacking. Ngoài vị trí, hacker còn có thể thu thập thông tin về các điểm Wi-Fi công cộng xung quanh — có thể mở đường xâm nhập mạng mục tiêu.

Biết vị trí, kẻ tấn công có thể thực hiện **dumpster diving, surveillance (giám sát), social engineering** và các tấn công phi kỹ thuật khác. Khi đã xác định vị trí, chúng có thể lấy ảnh vệ tinh từ Google Earth, Google Maps để truy cập trái phép vào tòa nhà, mạng có dây/không dây và hệ thống.

### Tools for Finding the Geographical Location

Các công cụ này cung cấp hình ảnh tòa nhà và khu vực xung quanh (gồm mạng Wi-Fi), lối vào tòa nhà, camera an ninh, cổng. Chúng cung cấp bản đồ tương tác, ảnh vệ tinh, chỉ đường lái xe, tình trạng giao thông, địa danh, địa chỉ và liên hệ chi tiết.

| Công cụ | Nguồn | Mô tả |
|---|---|---|
| **Google Earth** | https://earth.google.com | Tìm vị trí chính xác; truy cập ảnh 3D độ phân giải cao của bề mặt Trái Đất, cho phép xem street view, độ cao và tọa độ. |
| **Google Maps** | — | Chỉ đường, tình trạng giao thông, địa danh, định vị lối vào tòa nhà/camera/cổng. |
| **Wikimapia** | — | Tìm/định vị lối vào tòa nhà, camera, cổng, chỗ ẩn náu, điểm yếu hàng rào, nguồn điện… |

Kẻ tấn công dùng các công cụ này để tìm lối vào tòa nhà, camera an ninh, cổng, chỗ ẩn náu, điểm yếu hàng rào chu vi, nguồn điện và đo khoảng cách giữa các đối tượng.

---

## People Search on Social Networking Sites and People Search Services

### People Search trên mạng xã hội

Các mạng xã hội như **Facebook, Twitter, LinkedIn, Instagram** chứa thông tin người dùng tự cung cấp trong hồ sơ. Có thể tìm người theo **tên, từ khóa, công ty, trường học, bạn bè, đồng nghiệp** và những người sống quanh họ. Nhiều site cho phép tìm người **không cần đăng ký**, khiến việc tra cứu trở nên dễ dàng và ẩn danh; một số site còn cho biết tài khoản có đang active hay không.

Thông tin thu được gồm: tên, vị trí (position), tên tổ chức, vị trí hiện tại, trình độ học vấn, công ty/doanh nghiệp, số điện thoại, email, ảnh, video… Qua đó kẻ tấn công thu thập thông tin quan trọng phục vụ **social engineering** hoặc các kiểu tấn công khác.

### People Search Services

Có thể dùng các trang **public record** để tìm email, số điện thoại, địa chỉ nhà… Các dịch vụ online cung cấp tên, địa chỉ, liên hệ, ngày sinh, ảnh, video, nghề nghiệp, thông tin gia đình/bạn bè, hồ sơ mạng xã hội, thông tin tài sản, và đôi khi cả background về lý lịch tư pháp.

Thông tin còn có thể lộ: nghề nghiệp, doanh nghiệp do người đó sở hữu, dự án sắp tới, môi trường vận hành, website/blog, số điện thoại, email công ty, số fax, email cá nhân. Từ đó kẻ tấn công có thể cố lấy thông tin ngân hàng, thẻ tín dụng, lịch sử…

| Dịch vụ People Search |
|---|
| Intelius (https://www.intelius.com) |
| pipl |
| BeenVerified |
| Whitepages |
| PeekYou |
| AnyWho |

**Intelius** (https://www.intelius.com): tìm người thuộc tổ chức mục tiêu, lấy số điện thoại, lịch sử địa chỉ, tuổi, ngày sinh, người thân, lịch sử công việc, học vấn… (ví dụ kết quả tìm "Nicolas Cage in United States").

---

## Gathering Information from LinkedIn

LinkedIn là mạng xã hội cho giới chuyên nghiệp, chứa thông tin cá nhân: tên, vị trí (position), tên tổ chức, vị trí hiện tại, trình độ học vấn… Thông tin này hỗ trợ social engineering hoặc các kiểu tấn công khác.

### theHarvester

- **Nguồn:** http://www.edge-security.com
- Công cụ dùng ở giai đoạn đầu của pentest, phục vụ thu thập **OSINT** và xác định bề mặt đe dọa bên ngoài của công ty trên Internet. Kẻ tấn công dùng nó để liệt kê nhân viên của công ty mục tiêu trên LinkedIn kèm chức danh.

**Cú pháp liệt kê người dùng trên LinkedIn:**

```
theHarvester -d microsoft -l 200 -b linkedin
```

- `-d`: domain/tên công ty cần tìm
- `-l`: số kết quả cần lấy
- `-b`: nguồn dữ liệu (ở đây là `linkedin`)

Kết quả trả về danh sách nhân viên kèm chức danh, ví dụ: *Software Engineer II, Chief Digital Officer, Director of Product Management, Group Development Manager, President, Corporate Vice President, Senior Program Manager…* (Users found: 80).

---

## Harvesting Email Lists

Thu thập **email** liên quan tổ chức mục tiêu là vector tấn công quan trọng ở các giai đoạn sau của hacking. Kẻ tấn công dùng công cụ tự động như **theHarvester** và **Email Spider** để gom email công khai của nhân viên. Các công cụ này harvest email theo domain bằng search engine như **Google, Bing, Baidu**. Danh sách email và username này dùng cho **social engineering** và **brute-force**.

### theHarvester (trích xuất email)

- **Nguồn:** http://www.edge-security.com

**Ví dụ trích xuất email của microsoft.com qua Baidu:**

```
theharvester -d microsoft.com -l 200 -b baidu
```

- `-d`: domain dùng để harvest email
- `-l`: giới hạn kết quả (200)
- `-b`: nguồn search engine (baidu; có thể dùng Google, Bing…)

Kết quả là danh sách email như `msdnmg@microsoft.com`, `support@microsoft.com`, `postmaster@ul.onmicrosoft.com`…

---

## Gathering Information from Financial Services

Kẻ tấn công nhắm thông tin tài chính như **stock quotes, biểu đồ, tin tài chính, portfolio**. Các dịch vụ tài chính cung cấp: giá trị thị trường cổ phiếu công ty, company profile, thông tin đối thủ, tỷ giá sàn chứng khoán, thông cáo báo chí doanh nghiệp, báo cáo tài chính, tin tức và bài blog về doanh nghiệp.

Các công ty tài chính dựa vào web service để giao dịch và cấp quyền truy cập tài khoản. Kẻ tấn công có thể lấy thông tin nhạy cảm bằng malware, khai thác lỗi thiết kế phần mềm, phá cơ chế xác thực, **service flooding**, brute-force và phishing.

| Dịch vụ tài chính | Nguồn |
|---|---|
| **Google Finance** | https://www.google.com/finance |
| MSN Money | — |
| Yahoo! Finance | — |
| Investing.com | — |

**Google Finance** cung cấp headline doanh nghiệp/kinh doanh, quyết định tài chính, sự kiện tin tức lớn, biểu đồ giá cổ phiếu (đánh dấu sự kiện tin tức và corporate actions), tổng hợp tin Google News và bài Google blog về từng doanh nghiệp.

---

## Footprinting through Job Sites

Kẻ tấn công có thể thu thập thông tin quý giá về **hệ điều hành, phiên bản phần mềm, chi tiết hạ tầng và schema CSDL** của tổ chức qua trang tuyển dụng. Trang đăng tuyển thường lộ thông tin phần cứng/phần mềm, thông tin mạng và công nghệ sử dụng (firewall, loại server nội bộ, OS, network appliance…). Trang có thể kèm danh sách nhân viên chủ chốt với email.

Kẻ tấn công cũng xem **resume** của nhân viên đăng trên trang tuyển dụng để trích xuất chuyên môn, học vấn và lịch sử công việc — lịch sử công việc có thể lộ thông tin kỹ thuật về tổ chức. Thông tin kỹ thuật từ các trang như **Dice, LinkedIn, Simply Hired** giúp phát hiện lỗ hổng tiềm ẩn trong hạ tầng IT mục tiêu.

**Những thứ cần chú ý trong tin tuyển dụng:** Job requirements, Employees' profiles, Hardware information, Software information.

Ví dụ tin tuyển *Enterprise Applications Engineer* trên dice.com lộ yêu cầu: kinh nghiệm Windows 2008+/Linux 6+, Active Directory, DNS, IAM, Windows 10, VMware/HyperV, NetApp, AWS, VDI/Citrix, Splunk, ServiceNow, Exchange, Skype, DevOps, Jira, PowerShell…

---

## Deep and Dark Web Footprinting

- **Surface web:** lớp ngoài cùng, người dùng tìm trang/nội dung bằng trình duyệt thông thường (Google Chrome, Mozilla Firefox, Opera). Search engine dùng crawler (bot) để truy cập và tải trang.
- **Deep web:** lớp chứa trang và nội dung **bị ẩn và không được index**, không tìm được bằng trình duyệt/search engine truyền thống. Kích thước khổng lồ, gồm CSDL chính phủ/liên bang và thông tin liên kết các tổ chức. Truy cập qua search engine như **Tor Browser** và **The WWW Virtual Library**. Dùng cho cả mục đích hợp pháp lẫn bất hợp pháp.
- **Dark web / Darknet:** lớp sâu hơn, là tập con của deep web, cho phép **duyệt ẩn danh không bị truy vết**. Chỉ truy cập được qua công cụ chuyên dụng/trình duyệt darknet như **Tor Browser, Freenet, GNUnet, I2P, Retroshare**.

Kẻ tấn công dùng công cụ deep/dark web như **Tor Browser, ExoneraTor, OnionLand Search engine** để lấy thông tin bí mật về mục tiêu: chi tiết thẻ tín dụng, thông tin hộ chiếu, CMND/CCCD, hồ sơ y tế, tài khoản mạng xã hội, **Social Security Number (SSN)**.

### Tor Browser

- **Nguồn:** https://www.torproject.org
- Dùng để truy cập deep và dark web; hoạt động như **VPN mặc định**, bật/nảy địa chỉ IP qua nhiều server trước khi tương tác với web. Kẻ tấn công dùng để truy cập nội dung ẩn, website không index và CSDL mã hóa trong deep web (ví dụ tìm "microsoft" qua DuckDuckGo).

---

## Determining the Operating System

Kẻ tấn công dùng các công cụ online như **Netcraft, Shodan, Censys** để phát hiện hệ điều hành của tổ chức mục tiêu. Các công cụ này quét Internet tìm thiết bị kết nối (router, server, IoT) và lấy: city, country, latitude/longitude, hostname, OS, IP address. Thông tin này giúp xác định lỗ hổng và tìm exploit hiệu quả.

| Công cụ | Nguồn | Mô tả |
|---|---|---|
| **Netcraft** | https://www.netcraft.com | Kỹ thuật lấy thông tin OS mạng gọi là **OS fingerprinting**. Nhập domain vào ô "What's that site running?" để xác định tất cả site liên kết domain kèm OS của mỗi site. |
| **Shodan** | https://www.shodan.io | Search engine cho thiết bị kết nối Internet (router, server, IoT). |
| **Censys** | https://censys.io | Giám sát hạ tầng, phát hiện tài sản chưa biết, cung cấp toàn cảnh mọi server/thiết bị phơi ra Internet. |

#### Netcraft

Mở https://www.netcraft.com → "Search Web by Domain" → nhập domain (vd `microsoft.com`). Kết quả hiển thị các site kèm **Site Report, First seen, Netblock, OS** (ví dụ 292 sites; `go.microsoft.com` – Linux, `technet.microsoft.com` – Windows Server 2012…).

#### Shodan

Theo dõi mọi thiết bị trên mạng mục tiêu truy cập trực tiếp được từ Internet, tìm thiết bị theo city, country, latitude/longitude, hostname, OS, IP. Tìm lỗ hổng và exploit đã biết qua **Exploit DB, Metasploit, CVE, OSVDB, Packetstorm** trong một giao diện. Kết quả gồm TOP COUNTRIES, TOP SERVICES, TOP ORGANIZATIONS, TOP OPERATING SYSTEMS…

#### Censys

Phát hiện thiết bị kết nối Internet kèm chi tiết: OS, IP, protocol sử dụng, vị trí địa lý. Ví dụ host `192.99.7.58`: OS CentOS, Network OVH (FR), Protocols 80/HTTP, 22/SSH, 3306/MySQL; Apache httpd 2.4.6; OpenSSH 7.4; vị trí Montreal, Quebec, Canada.

---

## VoIP and VPN Footprinting through SHODAN

- **Nguồn:** https://www.shodan.io
- Shodan cho phép footprinting nhiều cấp độ, phát hiện thiết bị và mạng có lỗ hổng. Tìm kiếm VoIP và VPN trên Shodan trả về nhiều kết quả giúp thu thập thông tin liên quan VoIP và VPN.

Ảnh minh họa: kết quả VoIP (TOP PRODUCTS: VoIP) và kết quả VPN (thông tin Initiator SPI, Responder SPI, Next Payload, Exchange Type, Encryption/Domain/Authentication flags, "Welcome to VPN Router Configuration Tool"…).

---

## Competitive Intelligence Gathering

**Competitive intelligence** (tình báo cạnh tranh) là quá trình **xác định, thu thập, phân tích, kiểm chứng và sử dụng** thông tin về đối thủ từ các nguồn như Internet. Đây là hoạt động **không can thiệp (non-interfering) và tinh vi (subtle)**, tập trung vào môi trường kinh doanh bên ngoài, thu thập thông tin một cách **hợp pháp và có đạo đức** — khác với trộm cắp sở hữu trí tuệ qua hacking hay gián điệp công nghiệp.

Competitive intelligence giúp xác định:

- Đối thủ đang làm gì?
- Đối thủ định vị sản phẩm/dịch vụ thế nào?
- Khách hàng nói gì về điểm mạnh/yếu của đối thủ?

### Sources of Competitive Intelligence

Có thể thực hiện bằng **direct approach** hoặc **indirect approach**.

- **Direct Approach:** nguồn chính; gồm thu thập tại triển lãm thương mại (trade show), social engineering nhân viên và khách hàng…
- **Indirect Approach:** thu thập qua nguồn online.

| Nguồn Competitive Intelligence |
|---|
| Website công ty và quảng cáo tuyển dụng |
| Support threads và reviews |
| Search engine, Internet và CSDL online |
| Social media postings |
| Press release và báo cáo thường niên |
| Tạp chí thương mại, hội nghị, báo |
| Patent và trademark |
| Catalog sản phẩm và cửa hàng bán lẻ |
| Báo cáo phân tích và quản lý (analyst/regulatory) |
| Phỏng vấn khách hàng và nhà cung cấp |
| Đại lý, nhà phân phối và nhà cung cấp |
| Blog/ấn phẩm chuyên ngành |
| CSDL pháp lý (vd LexisNexis) |
| CSDL thông tin doanh nghiệp (vd Hoover's) |
| Đăng tuyển dụng online |

### When Did this Company Begin? How Did it Develop?

Thu thập tài liệu/hồ sơ đối thủ giúp trả lời: **When did it begin?** (lịch sử, ngày thành lập), **How did it develop?** (chiến lược quảng cáo, CRM…), **Who leads it?** (người ra quyết định), **Where is it located?** (vị trí, chi nhánh).

| Site tài nguyên | Nguồn | Mô tả |
|---|---|---|
| **EDGAR Database** | https://www.sec.gov/edgar.shtml | Hệ thống Electronic Data Gathering, Analysis, and Retrieval của SEC; thu thập/validate/index hồ sơ doanh nghiệp phải nộp theo luật cho SEC. |
| **D&B Hoovers** | http://www.hoovers.com | CSDL thương mại 120 triệu hồ sơ doanh nghiệp + analytics, giải pháp sales intelligence. |
| **LexisNexis** | https://www.lexisnexis.com | CSDL điện tử về hồ sơ pháp lý/công khai, tin tức, nguồn kinh doanh; phục vụ compliance, chống gian lận, điều tra. |
| **Business Wire** | https://www.businesswire.com | Phân phối press release và regulatory disclosure; phát tin qua mạng điện tử có bản quyền riêng. |
| **Factiva** | https://www.dowjones.com | CSDL tin tức toàn cầu, hơn 33.000 nguồn (ấn phẩm, website, blog, ảnh, video), 28 ngôn ngữ, hơn 600 newswire. |

### What Are the Company's Plans?

| Site tài nguyên | Nguồn | Mô tả |
|---|---|---|
| **MarketWatch** | https://www.marketwatch.com | Theo dõi thị trường cho nhà đầu tư; tin kinh doanh, tài chính cá nhân, bình luận real-time, công cụ đầu tư. |
| **The Wall Street Transcript** | https://www.twst.com | Ấn phẩm trả phí đăng báo cáo ngành; quan điểm của money manager và analyst, phỏng vấn CEO. |
| **Alexa** | https://www.alexa.com | Đào sâu analytics đối thủ; Competitor Backlink Checker, Competitive Intelligence Tools. |
| **Euromonitor** | https://www.euromonitor.com | Nghiên cứu chiến lược thị trường tiêu dùng; báo cáo ngành, người tiêu dùng, nhân khẩu học. |
| **Experian** | https://www.experian.com | Insight về search, affiliate, display, social marketing của đối thủ; dự báo xu hướng từ dữ liệu lịch sử. |
| **SEC Info** | http://www.secinfo.com | Cung cấp dịch vụ CSDL EDGAR của SEC; tìm theo name, industry, SIC code, area code, accession/file number, CIK, topic, ZIP. |
| **The Search Monitor** | https://www.thesearchmonitor.com | Giám sát brand/trademark, affiliate compliance, đối thủ quảng cáo trên paid/organic/local search, social, mobile, shopping. |
| **USPTO** | https://www.uspto.gov | Văn phòng Patent & Trademark Hoa Kỳ; thông tin và tìm kiếm patent/trademark. |

### What Expert Opinions Say About the Company?

| Site tài nguyên | Nguồn | Mô tả |
|---|---|---|
| **SEMRush** | https://www.semrush.com | Công cụ nghiên cứu từ khóa cạnh tranh; danh sách Google keyword/AdWords, danh sách đối thủ trong kết quả organic/paid. |
| **AttentionMeter** | http://www.attentionmeter.com | So sánh traffic website dùng Alexa, Compete, Technorati; cho snapshot và biểu đồ. |
| **ABI/INFORM Global** | https://www.proquest.com | CSDL doanh nghiệp; thông tin kinh doanh/tài chính, xu hướng, chiến lược, bối cảnh cạnh tranh. |
| **SimilarWeb** | https://www.similarweb.com | Tổng hợp dữ liệu ước tính traffic, geography, referral cho website và app; panel qua browser extension. |

---

## Other Techniques for Footprinting through Web Services

### Information Gathering Using Business Profile Sites

Các **business profile site** chứa thông tin doanh nghiệp ở một khu vực kèm thông tin liên hệ, ai cũng xem được. Kẻ tấn công dùng các site như **opencorporates, Crunchbase, corporationwiki** để lấy: vị trí, địa chỉ, thông tin liên hệ (số điện thoại, email), CSDL nhân viên, tên phòng ban, loại dịch vụ, loại ngành. (Ví dụ opencorporates tìm "Microsoft" → 728 companies.)

### Monitoring Targets Using Alerts

**Alert** là dịch vụ giám sát nội dung, tự động cung cấp thông tin **cập nhật** theo tùy chọn người dùng, thường qua **email hoặc SMS**. Người dùng đăng ký và cung cấp email/số điện thoại; dịch vụ tự thông báo khi có nội dung mới (tin tức, blog, discussion group) khớp từ khóa đã chọn.

| Công cụ Alert | Nguồn |
|---|---|
| **Google Alerts** | https://www.google.com/alerts |
| Twitter Alerts | — |
| Giga Alerts | — |

**Google Alerts** tự thông báo khi nội dung mới từ news, website, blog, video, discussion group khớp từ khóa người dùng đặt (ví dụ alert cho `microsoft.com`, tùy chọn How often / Sources / Language / Region / How many).

### Tracking Online Reputation of the Target

**Online Reputation Management (ORM)** là quá trình **giám sát uy tín của công ty trên Internet** và thực hiện biện pháp giảm thiểu kết quả/đánh giá tiêu cực, qua đó cải thiện uy tín thương hiệu. Khi tổ chức minh bạch trên Internet, tính minh bạch này lại giúp kẻ tấn công thu thập thông tin xác thực về mục tiêu.

Kẻ tấn công dùng công cụ ORM để:

- Theo dõi uy tín online của công ty
- Thu thập thông tin xếp hạng search engine
- Nhận email thông báo khi công ty được nhắc đến online
- Theo dõi các cuộc hội thoại (conversations)
- Lấy social news về tổ chức mục tiêu

| Công cụ ORM | Nguồn |
|---|---|
| **Mention** | https://mention.com |
| Trackur | — |
| Brand24 | — |

**Mention**: giám sát web, mạng xã hội, forum, blog để hiểu hơn về brand và ngành mục tiêu; theo dõi hội thoại online real-time và gửi báo cáo trực tiếp tới email.

### Information Gathering Using Groups, Forums, and Blogs

Nhiều người dùng dùng blog, group, forum để chia sẻ kiến thức. Tổ chức thường **không giám sát** việc nhân viên tiết lộ thông tin trong các thảo luận này. Kẻ tấn công coi đây là lợi thế, thu thập thông tin nhạy cảm: thông tin mạng công khai, thông tin hệ thống, thông tin cá nhân nhân viên. Chúng có thể **đăng ký profile giả** trong Google groups, Yahoo groups… và cố gia nhập group nhân viên của tổ chức để lấy thông tin cá nhân/công ty. Cũng có thể tìm theo **FQDN, IP address, username**.

Thông tin nhân viên kẻ tấn công có thể thu thập:

- Họ tên đầy đủ
- Nơi làm việc và nơi cư trú
- Điện thoại nhà, di động, văn phòng
- Email cá nhân và email tổ chức
- Ảnh nơi ở/nơi làm việc kèm thông tin nhận dạng
- Ảnh giải thưởng nhân viên hoặc mục tiêu sắp tới

(Ví dụ **Google Groups** – https://groups.google.com)

### Information Gathering Using NNTP Usenet Newsgroups

**Usenet newsgroup** là kho chứa các ghi chú/tin nhắn về nhiều chủ đề do người dùng gửi qua Internet. **Network News Transfer Protocol (NNTP)** dùng để chuyển tiếp bài viết Usenet. Người dùng thường đăng câu hỏi nhờ giải quyết vấn đề kỹ thuật; nhiều chuyên gia tiết lộ thông tin chi tiết hơn mức cần thiết về mục tiêu. Kẻ tấn công có thể tìm trên Usenet newsgroup hoặc mailing list như **Newshosting, Eweka, Supernews** để biết OS, phần mềm, web server… mà tổ chức sử dụng.

**Ví dụ** một bài đăng newsgroup mẫu:

```
From: adams@certifiedhacker.com
Subject: Apache Problem
Newsgroups: comp.infosystems.www.servers.unix, comp.os.linux, alt.apache.configuration, comp.lang.java.programmer
Date: 2018-02-27 09:19:28 PST

I am having a problem with Apache reverse proxy not communicating with web
applications using HTTP 1.1 keepalive. I am using Apache 1.3.23 on Red Hat Linux 6.2.
It is compiled with mod_proxy and mod_ssl.
...
adams@certifiedhacker.com
Sr. Systems Administrator
certifiedhacker.com
```

Từ bài đăng có thể suy ra tổ chức mục tiêu dùng máy **Red Hat Linux 6.2** chạy **Apache web server 1.3.23** — thông tin hỗ trợ tấn công web server và web application.
