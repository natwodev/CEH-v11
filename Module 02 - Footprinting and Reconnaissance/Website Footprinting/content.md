# Website Footprinting

> Module 02 | Trang 81–100

## Giới thiệu

**Website footprinting** là việc **giám sát và phân tích website** của tổ chức mục tiêu để thu thập thông tin. Kẻ tấn công có thể xây dựng bản đồ chi tiết về cấu trúc và kiến trúc của một website mà **không kích hoạt IDS** hay gây nghi ngờ cho người quản trị hệ thống.

Website của tổ chức là nơi đầu tiên để lấy các thông tin nhạy cảm như tên và thông tin liên hệ của lãnh đạo, chi tiết các dự án sắp tới, v.v.

Phần này bao gồm:

- Khái niệm website footprinting
- Mirroring (sao chép) website
- Trích xuất thông tin và liên kết của website
- Thu thập wordlist
- Trích xuất metadata của tài liệu công khai
- Giám sát cập nhật web và lưu lượng truy cập website

Kẻ tấn công sử dụng các công cụ footprinting tinh vi hoặc các công cụ cơ bản đi kèm hệ điều hành như **Telnet** hay trình duyệt.

> Công cụ **Netcraft** có thể thu thập thông tin website như địa chỉ IP, tên/địa chỉ đăng ký của chủ sở hữu domain, tên domain, host của site và chi tiết hệ điều hành. Tuy nhiên công cụ này không cung cấp đủ tất cả thông tin cho mọi site; khi đó kẻ tấn công sẽ duyệt trực tiếp website.

---

## Thông tin thu thập được khi duyệt website

Duyệt website mục tiêu thường cung cấp các thông tin sau:

- **Software used and its version** (phần mềm và phiên bản đang dùng): dễ tìm thấy trên website dùng phần mềm thương mại có sẵn.
- **Operating system used** (hệ điều hành): thường cũng có thể xác định được.
- **Sub-directories and parameters** (thư mục con và tham số): lộ ra qua việc ghi lại các URL khi duyệt.
- **Filename, path, database field name, or query**: phân tích kỹ phần sau một query để tìm cơ hội **SQL injection**.
- **Scripting platform** (nền tảng kịch bản): qua phần mở rộng tên file như `.php`, `.asp`, `.jsp`.
- **Technologies Used**: kiểm tra URL để xác định công nghệ (.NET, J2EE, PHP, v.v.).
- **Contact details and CMS details**: trang liên hệ thường có tên, số điện thoại, email, vị trí của nhân sự admin/support — phục vụ **social engineering**. Phần mềm CMS cho phép URL rewriting để che giấu phần mở rộng tên script.

### Công cụ xem HTTP headers

Kẻ tấn công dùng **Burp Suite, Zaproxy, WhatWeb, BuiltWith, Wappalyzer, Website Informer** để xem header cung cấp:

- Connection status và content-type
- Accept-Ranges và Last-Modified
- X-Powered-By
- Web server đang dùng và phiên bản

---

## Burp Suite

Nguồn: *https://portswigger.net*

Burp Suite là nền tảng tích hợp để kiểm thử bảo mật ứng dụng web. Các công cụ của nó phối hợp hỗ trợ toàn bộ quá trình kiểm thử, từ mapping ban đầu và phân tích bề mặt tấn công cho đến tìm và khai thác lỗ hổng.

**Burp Proxy** cho phép kẻ tấn công chặn (intercept) toàn bộ request và response giữa trình duyệt và ứng dụng web mục tiêu, thu thập các thông tin như web server đang dùng, phiên bản và các lỗ hổng liên quan ứng dụng web.

---

## Kiểm tra mã nguồn HTML và Cookies

Website footprinting có thể thực hiện bằng cách kiểm tra mã nguồn HTML và cookies.

### Examining the HTML source code (kiểm tra mã nguồn HTML)

Kẻ tấn công thu thập thông tin nhạy cảm bằng cách kiểm tra mã nguồn HTML và theo dõi các **comment** chèn thủ công hoặc do CMS tạo ra. Các comment có thể cho biết phần mềm chạy nền, thậm chí cả thông tin liên hệ của web developer/admin.

Kiểm tra mã nguồn HTML có thể cung cấp:

- Các comment trong mã nguồn
- Thông tin liên hệ của web developer hoặc admin
- Cấu trúc hệ thống file và loại script

> Quan sát toàn bộ link và thẻ image để vẽ bản đồ cấu trúc file, lộ ra các thư mục/file ẩn. Nhập dữ liệu giả để xem cách script hoạt động. Đôi khi có thể chỉnh sửa được mã nguồn.

### Examining Cookies (kiểm tra cookies)

Để xác định phần mềm đang chạy và hành vi của nó, có thể kiểm tra cookies do server đặt. Nhận diện nền tảng kịch bản bằng cách quan sát session và các cookie hỗ trợ. Cũng có thể trích xuất thông tin về tên cookie, giá trị và kích thước domain.

Kiểm tra cookies có thể cung cấp:

- Phần mềm đang dùng và hành vi của nó
- Nền tảng kịch bản (scripting platforms) đang dùng

---

## Website Footprinting bằng Web Spiders

Một **web spider** (còn gọi là **web crawler** hay **web robot**) là chương trình hoặc script tự động duyệt website một cách có hệ thống để thu thập thông tin cụ thể như tên nhân viên và địa chỉ email. Kẻ tấn công dùng thông tin này cho footprinting và social engineering.

> Web spidering **thất bại** nếu website mục tiêu có file **robots.txt** ở thư mục gốc liệt kê các thư mục cần chặn crawling.

Kẻ tấn công có thể phát hiện toàn bộ file và trang web bằng cách cấp cho spider một URL. Spider gửi hàng trăm request, phân tích mã HTML của các response để tìm link bổ sung; nếu có link mới, spider thêm vào danh sách mục tiêu và tiếp tục. Cách này giúp phát hiện bề mặt tấn công web có thể khai thác cũng như tìm tất cả thư mục, trang và file của website.

### User-Directed Spidering

Trong một số trường hợp, kẻ tấn công dùng kỹ thuật tinh vi hơn: dùng **trình duyệt chuẩn** để đi qua tất cả chức năng của ứng dụng web. Trong khi đó, lưu lượng vào/ra được giám sát và phân tích bởi các công cụ tích hợp tính năng của cả web spider và **intercepting proxy**. Công cụ tạo bản đồ ứng dụng gồm tất cả URL đã duyệt, phân tích response và cập nhật bản đồ. Công cụ dùng: **Burp Suite** và **WebScarab**.

### Công cụ web spider

| Công cụ | Ghi chú |
|---|---|
| Web Data Extractor | Thu thập thông tin nhạy cảm từ website mục tiêu |
| ParseHub | Tìm kiếm tự động, thu thập tên/email |
| SpiderFoot | Thu thập thông tin nhạy cảm |

---

## Web Data Extractor

Nguồn: *http://www.webextractor.com*

Web Data Extractor tự động trích xuất thông tin cụ thể từ các trang web. Nó trích xuất:

- Dữ liệu liên hệ mục tiêu (email, điện thoại, fax) từ website
- URL và **meta tags** (title, description, keyword) phục vụ quảng bá website
- Tìm kiếm/tạo directory, thực hiện nghiên cứu web, v.v.

Như trong screenshot, kẻ tấn công dùng Web Data Extractor để tự động thu thập thông tin quan trọng như danh sách meta tags, địa chỉ email, số điện thoại và fax từ website mục tiêu.

---

## Mirroring (Sao chép) toàn bộ Website

Website mirroring là quá trình tạo bản sao (replica/clone) của website gốc. Các công cụ tải website về thư mục cục bộ và đệ quy xây dựng lại tất cả thư mục gồm HTML, hình ảnh, flash, video và các file khác từ webserver sang máy tính khác.

Mirroring website cho phép kẻ tấn công duyệt website **offline**; cũng hỗ trợ tìm cấu trúc thư mục và thông tin giá trị khác từ bản sao mà không cần gửi nhiều request đến web server.

**Lợi ích của website mirroring:**

- Hữu ích cho việc duyệt site offline
- Cho kẻ tấn công thêm thời gian xem và phân tích website để tìm lỗ hổng và sơ hở
- Giúp tìm cấu trúc thư mục và thông tin giá trị từ bản sao mà không cần nhiều request đến webserver

Kẻ tấn công dùng thông tin này để thực hiện nhiều cuộc tấn công ứng dụng web vào website mục tiêu.

### Công cụ mirroring website

| Công cụ | Nguồn / Ghi chú |
|---|---|
| HTTrack Web Site Copier | *http://www.httrack.com* — tiện ích duyệt offline, tải website về thư mục cục bộ và đệ quy xây dựng lại toàn bộ thư mục, HTML, hình ảnh và file khác |
| NCollector Studio | Tải website về thư mục cục bộ |

Như trong screenshot, kẻ tấn công dùng HTTrack để mirror toàn bộ website của tổ chức mục tiêu, lưu vào ổ đĩa cục bộ và duyệt website cục bộ để xác định các lỗ hổng và exploit có thể có.

---

## Trích xuất thông tin Website từ archive.org

Nguồn: *https://archive.org*

**Internet Archive Wayback Machine** cho phép truy cập **các phiên bản đã lưu trữ (archived)** của website. Việc khám phá này giúp kẻ tấn công thu thập thông tin về các trang web của tổ chức từ thời điểm tạo ra chúng.

Vì archive.org lưu lại các trang web từ lúc chúng được tạo, kẻ tấn công có thể truy xuất cả những thông tin **đã bị gỡ bỏ** khỏi website mục tiêu, như trang web, file audio, video, hình ảnh, văn bản và chương trình phần mềm. Kẻ tấn công dùng thông tin này để thực hiện phishing và các tấn công ứng dụng web khác.

---

## Trích xuất Links (liên kết) của Website

Trích xuất link là phần quan trọng của website footprinting: kẻ tấn công phân tích website để xác định **link nội bộ và link bên ngoài**. Từ đó có thể tìm ra ứng dụng, công nghệ web, và các website liên quan được liên kết tới mục tiêu. Việc dump các link còn lộ ra các kết nối quan trọng và trích xuất URL của tài nguyên khác như file JavaScript, CSS — giúp xác định lỗ hổng và cách khai thác ứng dụng web.

Kẻ tấn công dùng công cụ/dịch vụ trực tuyến để trích xuất hình ảnh, script, iframe, URL được liên kết, và cả **backlink** đến website mục tiêu.

### Công cụ trích xuất links

| Công cụ | Nguồn / Ghi chú |
|---|---|
| Octoparse | *https://www.octoparse.com* — trích xuất dữ liệu tự động, scrape nhanh dữ liệu web không cần code, biến trang web thành dữ liệu có cấu trúc |
| Netpeak Spider | Trích xuất link của website mục tiêu |
| Link Extractor | Trích xuất link của website mục tiêu |

Như trong screenshot, kẻ tấn công dùng Octoparse để thu thập thông tin từ trang web như text, link, URL hình ảnh hoặc mã HTML.

---

## Thu thập Wordlist từ Website mục tiêu

Các từ ngữ có trên website mục tiêu có thể lộ ra thông tin quan trọng giúp khai thác sâu hơn. Kẻ tấn công thu thập danh sách email liên quan tổ chức (qua search engine, mạng xã hội, công cụ web spidering), sau đó thu thập danh sách từ trên website để thực hiện **brute-force** vào các email đó.

Kẻ tấn công dùng công cụ **CeWL** để thu thập danh sách từ từ website mục tiêu.

### Các lệnh chạy CeWL

| Lệnh | Chức năng |
|---|---|
| `ruby cewl.rb --help` | Hiển thị các tùy chọn để lấy danh sách từ |
| `cewl www.certifiedhacker.com` | Trả về danh sách các từ duy nhất (unique) có trên URL mục tiêu |
| `cewl --email www.certifiedhacker.com` | Lấy danh sách từ **và** địa chỉ email từ website mục tiêu |

---

## Trích xuất Metadata của tài liệu công khai

Thông tin hữu ích có thể nằm trên website mục tiêu dưới dạng tài liệu **PDF**, file **Microsoft Word** và các định dạng khác. Kẻ tấn công trích xuất dữ liệu giá trị gồm metadata và thông tin ẩn từ các tài liệu này.

Dữ liệu này chủ yếu chứa thông tin ẩn về tài liệu công khai, có thể phân tích để lấy: title trang, description, keyword, ngày/giờ tạo hoặc chỉnh sửa nội dung, và username/email của nhân viên tổ chức.

> Kẻ tấn công có thể lạm dụng thông tin này để brute-force xác thực bằng username và email của nhân viên, hoặc social engineering để gửi malware lây nhiễm hệ thống mục tiêu.

### Công cụ trích xuất metadata

Các công cụ này tự động trích xuất thông tin quan trọng gồm: username của khách hàng, hệ điều hành (exploit phụ thuộc OS), địa chỉ email (cho social engineering), danh sách phần mềm (phiên bản và loại), danh sách server, ngày tạo/sửa tài liệu và tác giả website.

| Công cụ | Nguồn / Ghi chú |
|---|---|
| Metagoofil | *https://code.google.com* — trích xuất metadata của tài liệu công khai (pdf, doc, xls, ppt, docx, pptx, xlsx) thuộc công ty mục tiêu |
| Exiftool | Trích xuất metadata và thông tin ẩn |
| Web Data Extractor | Trích xuất metadata và thông tin ẩn |

**Metagoofil** thực hiện tìm kiếm Google để xác định và tải tài liệu về đĩa cục bộ, rồi trích xuất metadata bằng các thư viện khác nhau như **Hachoir**, **PdfMiner**, v.v. Nó tạo báo cáo gồm username, phiên bản phần mềm và tên server/máy — hỗ trợ giai đoạn thu thập thông tin.

---

## Các kỹ thuật Website Footprinting khác

### Monitoring Web Pages for Updates and Changes (giám sát cập nhật và thay đổi)

Kẻ tấn công giám sát website mục tiêu để phát hiện cập nhật và thay đổi: nhận diện thay đổi trang đăng nhập, trích xuất trang bảo vệ bằng mật khẩu, theo dõi thay đổi phiên bản phần mềm và cập nhật driver, trích xuất và lưu hình ảnh trên trang đã sửa, v.v. Phân tích thông tin này để phát hiện lỗ hổng và khai thác.

**Công cụ giám sát cập nhật web** có khả năng phát hiện mọi thay đổi/cập nhật trên một website cụ thể và gửi thông báo/cảnh báo qua email hoặc SMS.

| Công cụ | Nguồn / Ghi chú |
|---|---|
| WebSite-Watcher | *https://www.aignes.com* — theo dõi website để phát hiện cập nhật và thay đổi tự động; khi có thay đổi, tự động lưu **hai phiên bản gần nhất** vào đĩa |
| VisualPing | Giám sát thay đổi trên website |

Như trong screenshot, kẻ tấn công dùng WebSite-Watcher để trích xuất phiên bản cũ và mới của các trang web liên quan website mục tiêu.

### Searching for Contact Information, Email Addresses, and Telephone Numbers (tìm thông tin liên hệ)

Kẻ tấn công tìm kiếm website công ty mục tiêu để thu thập thông tin quan trọng. Tổ chức thường dùng website để thông báo cho công chúng về hoạt động, sản phẩm/dịch vụ, cách liên hệ, v.v. — kẻ tấn công khai thác để tiến hành tấn công sâu hơn.

Ví dụ, có thể tìm kiếm:

- Tên liên hệ công ty, số điện thoại, email
- Vị trí và chi nhánh công ty
- Thông tin đối tác (Partner Information)
- Tin tức (News)
- Link đến các site khác
- Dữ liệu sản phẩm, dự án hoặc dịch vụ

### Searching for Web Pages Posting Patterns and Revision Numbers (tìm copyright và revision number)

**Copyright** là cơ chế bảo vệ do luật pháp cấp, trao cho người tạo tác phẩm gốc quyền độc quyền sử dụng và phân phối. Hầu hết tổ chức đảm bảo có thông báo bản quyền trên mọi tác phẩm công bố.

Một thông báo bản quyền điển hình chứa:

- Ký hiệu bản quyền (Copyright Symbol)
- Năm tạo (Year of Creation)
- Tên tác giả (Name of the Author)
- Tuyên bố quyền (Rights Statement)

Kẻ tấn công tìm các thông báo bản quyền để phân tích sâu tổ chức mục tiêu. Ngoài ra có thể tìm và ghi lại **revision number** — chuỗi định danh cho phiên bản của tài liệu, nằm trong các tài liệu của công ty — cũng như các document number được gán sau khi sửa đổi, để tiến hành tấn công sâu hơn.

### Monitoring Website Traffic of Target Company (giám sát lưu lượng website)

Kẻ tấn công giám sát lưu lượng website công ty mục tiêu để thu thập thông tin giá trị về tệp khách hàng, giúp giả dạng làm khách hàng và thực hiện social engineering.

Thông tin thu thập gồm:

| Loại thông tin | Công cụ ví dụ |
|---|---|
| **Total visitors** (tổng lượt truy cập) | Clicky — *https://clicky.com* |
| **Page views** (lượt xem trang) | Opentracker — *https://www.opentracker.net* (kèm timestamp và trạng thái user) |
| **Bounce rate** (tỷ lệ thoát) | Google Analytics — *https://analytics.google.com* |
| **Live visitors map** (bản đồ khách trực tuyến) | Web-Stat — *https://www.web-stat.com* (theo dõi vị trí địa lý người dùng) |
| **Site ranking** (xếp hạng site) | Alexa — *https://www.alexa.com* |
| **Audience geography** (địa lý đối tượng) | Alexa (theo dõi vị trí khách hàng trên toàn cầu) |

> Các công cụ giám sát lưu lượng tiêu biểu: **Web-Stat, Alexa, Monitis**.
