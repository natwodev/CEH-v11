# Hacking Concepts

> Module 01 | Trang 27–37

## Giới thiệu

Phần này trình bày các khái niệm cơ bản về hacking: **hacking là gì**, **ai là hacker**, và các **phân lớp hacker (hacker classes)** — cùng với **năm giai đoạn (phase) tấn công** mà người học cần nắm vững trước khi đi vào phương pháp luận ethical hacking.

---

## What is Hacking? (Hacking là gì?)

**Hacking** trong lĩnh vực an ninh máy tính (computer security) là việc **khai thác lỗ hổng hệ thống (exploiting system vulnerabilities)** và **phá vỡ các biện pháp kiểm soát bảo mật (compromising security controls)** để giành quyền truy cập trái phép hoặc không phù hợp vào tài nguyên của hệ thống.

Ba ý chính:

- Khai thác lỗ hổng và phá vỡ kiểm soát bảo mật để truy cập trái phép tài nguyên hệ thống.
- Bao gồm việc **sửa đổi các tính năng của hệ thống hoặc ứng dụng (modifying system or application features)** nhằm đạt một mục đích nằm ngoài ý định ban đầu của người tạo ra.
- Có thể được dùng để đánh cắp và phát tán lại tài sản trí tuệ (intellectual property), dẫn đến **thiệt hại kinh doanh (business loss)**.

Hacking trên mạng máy tính thường được thực hiện bằng các script hoặc kỹ thuật lập trình mạng (network programming). Các kỹ thuật hack mạng bao gồm:

- Tạo virus và worm.
- Thực hiện tấn công từ chối dịch vụ (**denial-of-service / DoS**).
- Thiết lập kết nối truy cập từ xa trái phép tới thiết bị bằng **trojan** hoặc **backdoor**.
- Tạo **botnet**, **packet sniffing**, **phishing**, và **password cracking**.

> **Động cơ (motive)** đằng sau hacking có thể là: đánh cắp thông tin/dịch vụ quan trọng, vì cảm giác mạnh (thrill), thử thách trí tuệ, tò mò, thử nghiệm, kiến thức, lợi ích tài chính, danh tiếng, quyền lực, được đồng nghiệp công nhận, trả thù và thù hằn.

---

## Who is a Hacker? (Ai là hacker?)

**Hacker** là người đột nhập vào một hệ thống hoặc mạng mà không có sự cho phép để phá hủy, đánh cắp dữ liệu nhạy cảm, hoặc thực hiện các tấn công độc hại. Hacker là cá nhân thông minh, có **kỹ năng máy tính xuất sắc (excellent computer skills)**, cùng khả năng tạo ra và khám phá phần mềm lẫn phần cứng của máy tính.

Thông thường, hacker là một kỹ sư hoặc lập trình viên lành nghề, đủ kiến thức để phát hiện lỗ hổng trong hệ thống mục tiêu; họ có chuyên môn sâu và thích tìm hiểu chi tiết của nhiều ngôn ngữ lập trình và hệ thống máy tính khác nhau.

Bốn nhóm đặc điểm/động cơ:

| # | Đặc điểm |
|---|----------|
| 01 | Cá nhân thông minh với **kỹ năng máy tính xuất sắc**, có thể tạo ra và khám phá phần mềm/phần cứng máy tính |
| 02 | Với một số hacker, hacking là một **sở thích (hobby)** để xem họ có thể xâm nhập được bao nhiêu máy tính hay mạng |
| 03 | Ý định có thể là để **thu thập kiến thức** hoặc để **dò xét và làm điều phi pháp (probe and do illegal things)** |
| 04 | Một số hack với **ý đồ xấu (malicious intent)**: đánh cắp dữ liệu doanh nghiệp, thông tin thẻ tín dụng, số an sinh xã hội, mật khẩu email và dữ liệu nhạy cảm khác |

---

## Hacker Classes (Phân lớp hacker)

Hacker thường được xếp vào một trong các nhóm sau, dựa trên hoạt động của họ:

| # | Lớp | Mô tả |
|---|-----|--------|
| 01 | **Black Hats** (mũ đen) | Cá nhân dùng kỹ năng máy tính phi thường vào mục đích bất hợp pháp hoặc độc hại; thường dính líu hoạt động tội phạm. Còn gọi là **crackers**. |
| 02 | **White Hats** (mũ trắng) | Còn gọi là **penetration testers**, dùng kỹ năng hacking vào mục đích phòng thủ. Là các **security analyst** am hiểu biện pháp đối phó (countermeasures), bảo vệ mạng và hệ thống. **Có sự cho phép của chủ hệ thống (permission from the system owner)**. |
| 03 | **Gray Hats** (mũ xám) | Hoạt động cả tấn công lẫn phòng thủ ở các thời điểm khác nhau; có thể giúp tìm lỗ hổng đồng thời giúp nhà cung cấp cải thiện sản phẩm. |
| 04 | **Suicide Hackers** | Nhằm đánh sập hạ tầng trọng yếu vì một "lý tưởng (cause)", không lo sợ bị tù tội hay trừng phạt — tương tự "kẻ đánh bom liều chết", không quan tâm hậu quả. |
| 05 | **Script Kiddies** | Hacker thiếu kỹ năng, xâm nhập hệ thống bằng cách chạy script, công cụ và phần mềm do hacker thực thụ phát triển; chú trọng số lượng hơn chất lượng tấn công. |
| 06 | **Cyber Terrorists** | Cá nhân với dải kỹ năng rộng, có động cơ tín ngưỡng/chính trị, tạo ra nỗi sợ qua việc phá vỡ quy mô lớn các mạng máy tính. |
| 07 | **State-Sponsored Hackers** | Được chính phủ thuê để xâm nhập, lấy thông tin tối mật và phá hoại hệ thống thông tin của chính phủ khác. |
| 08 | **Hacktivist** | Đột nhập hệ thống chính phủ/doanh nghiệp như một hành động phản kháng (protest), nhằm thúc đẩy một chương trình nghị sự chính trị, đặc biệt bằng cách **defacing** hoặc vô hiệu hóa website. |

> **Hacktivism:** Hacktivist dùng hacking để nâng cao nhận thức về chương trình nghị sự xã hội/chính trị của họ, đồng thời đánh bóng tên tuổi ở cả không gian trực tuyến lẫn ngoài đời. Mục tiêu thường gặp gồm cơ quan chính phủ, tập đoàn đa quốc gia và bất kỳ thực thể nào họ xem là mối đe dọa.
>
> **Lưu ý:** Bất kể ý định của hacktivist là gì, việc giành quyền truy cập trái phép vẫn là **tội phạm (crime)**.

---

## Hacking Phases (Các giai đoạn hacking)

Nhìn chung, có **năm giai đoạn** của một cuộc tấn công:

```
1. Reconnaissance   (Trinh sát)
2. Scanning         (Quét)
3. Gaining Access   (Giành quyền truy cập)
4. Maintaining Access (Duy trì truy cập)
5. Clearing Tracks  (Xóa dấu vết)
```

---

### Phase 1 — Reconnaissance (Trinh sát)

**Reconnaissance** là giai đoạn **chuẩn bị (preparatory phase)** trong đó kẻ tấn công tìm cách **thu thập càng nhiều thông tin** về mục tiêu càng tốt trước khi khởi động cuộc tấn công.

- Kẻ tấn công khai thác **competitive intelligence** để tìm hiểu về mục tiêu; thông tin có thể là "điểm quay lại trong tương lai", được ghi chú để dễ dàng xâm nhập khi đã hiểu mục tiêu trên diện rộng (**broad scale**).
- **Phạm vi mục tiêu (target range)** có thể gồm: khách hàng, nhân viên, hoạt động vận hành, mạng và hệ thống của tổ chức.
- Giai đoạn này có thể tốn thời gian. Một phần của trinh sát có thể liên quan đến **social engineering** — ví dụ kẻ tấn công gọi cho nhà cung cấp dịch vụ Internet (ISP) của mục tiêu, dùng thông tin cá nhân đã thu được để thuyết phục nhân viên chăm sóc khách hàng rằng hắn chính là mục tiêu, từ đó lấy thêm thông tin.

#### Reconnaissance Types (Các loại trinh sát)

Kỹ thuật trinh sát được chia thành hai loại: **passive** và **active**.

| Passive Reconnaissance (Thụ động) | Active Reconnaissance (Chủ động) |
|-----------------------------------|----------------------------------|
| **Không tương tác trực tiếp với mục tiêu** | **Tương tác trực tiếp với mục tiêu** bằng bất kỳ phương tiện nào |
| Dựa vào thông tin công khai, news releases, hoặc các phương thức không tiếp xúc | Dùng công cụ để dò cổng mở (open ports), host truy cập được, vị trí router, lập bản đồ mạng (network mapping), chi tiết OS và ứng dụng |
| Ví dụ: tra cứu hồ sơ công khai (public records), bản tin báo chí | Ví dụ: gọi điện cho help desk hoặc phòng kỹ thuật của mục tiêu |

> Kẻ tấn công dùng active reconnaissance khi xác suất bị phát hiện thấp.

#### Kỹ thuật trinh sát khác

- **Dumpster diving:** lục thùng rác của tổ chức để tìm thông tin nhạy cảm bị vứt bỏ — có thể lộ username, password, sao kê thẻ tín dụng/ngân hàng, biên lai ATM, số an sinh xã hội, số điện thoại riêng, số tài khoản...
- **Whois database:** tra cứu website công ty mục tiêu trong cơ sở dữ liệu Whois trên Internet để dễ dàng có được địa chỉ IP, tên miền và thông tin liên hệ.

> **Góc nhìn ethical hacker:** Cần phân biệt được các phương pháp trinh sát khác nhau và khuyến nghị biện pháp phòng ngừa. Doanh nghiệp phải coi an ninh là phần không thể tách rời trong chiến lược kinh doanh/vận hành, trang bị chính sách và quy trình phù hợp để kiểm tra lỗ hổng tiềm ẩn.

---

### Phase 2 — Scanning (Quét)

**Scanning** là giai đoạn **ngay trước cuộc tấn công (pre-attack phase)**, trong đó kẻ tấn công dùng các chi tiết thu thập trong reconnaissance để quét mạng tìm thông tin cụ thể. Đây là phần mở rộng logic của active reconnaissance, nhưng đi sâu thăm dò (probing) hơn — hai giai đoạn này thường chồng lấn và khó tách bạch.

| Thành phần | Mô tả |
|------------|--------|
| **Pre-attack Phase** | Quét mạng để lấy thông tin cụ thể dựa trên dữ liệu thu được trong reconnaissance |
| **Port Scanner** | Có thể dùng dialers, **port scanners**, network mappers, ping tools, vulnerability scanners |
| **Extract Information** | Trích xuất: máy đang hoạt động (**live machines**), cổng, trạng thái cổng, chi tiết OS, loại thiết bị, **system uptime** để chuẩn bị tấn công |

- Kẻ tấn công có thể thu thập thông tin mạng quan trọng (bản đồ hệ thống, router, firewall) bằng công cụ đơn giản như tiện ích Windows **Traceroute**, hoặc dùng **Cheops** để bổ sung thông tin cho kết quả Traceroute.
- **Port scanners** phát hiện cổng đang lắng nghe (listening ports) để tìm thông tin về các dịch vụ chạy trên máy mục tiêu. Biện pháp phòng thủ chính: tắt các dịch vụ không cần thiết và áp dụng **port filtering** phù hợp.
- **Vulnerability scanners** là công cụ được dùng phổ biến nhất, có thể dò hàng nghìn lỗ hổng đã biết. Kẻ tấn công chỉ cần tìm một lối vào duy nhất, trong khi chuyên gia phải vá càng nhiều lỗ hổng càng tốt.

> Tổ chức dùng **IDS (intrusion detection systems)** vẫn phải cảnh giác vì kẻ tấn công sẽ dùng kỹ thuật né tránh (**evasion techniques**) bất cứ khi nào có thể.

---

### Phase 3 — Gaining Access (Giành quyền truy cập)

Đây là giai đoạn **hacking thực sự diễn ra**. Kẻ tấn công dùng các lỗ hổng đã xác định trong giai đoạn reconnaissance và scanning để giành quyền truy cập vào hệ thống và mạng mục tiêu.

| # | Nội dung |
|---|----------|
| 1 | Gaining access là điểm mà kẻ tấn công có được quyền truy cập vào **operating system hoặc applications** trên máy/mạng mục tiêu |
| 2 | Có thể giành truy cập ở mức **operating system, application, hoặc network** |
| 3 | Có thể **leo thang đặc quyền (escalate privileges)** để kiểm soát hoàn toàn hệ thống; trong quá trình đó, các hệ thống trung gian (intermediate systems) kết nối với mục tiêu cũng bị xâm phạm |
| 4 | Ví dụ: **password cracking**, buffer overflows, denial of service, **session hijacking** |

- Truy cập có thể đạt được cục bộ (offline), qua LAN, hoặc qua Internet. Ví dụ: password cracking, stack-based buffer overflows, DoS, session hijacking.
- Kỹ thuật **spoofing**: kẻ tấn công giả mạo là người dùng hợp lệ hoặc hệ thống khác để gửi gói dữ liệu chứa lỗi nhằm khai thác lỗ hổng.
- **Packet flooding** phá vỡ tính sẵn sàng của dịch vụ thiết yếu. **Smurf attacks** khiến người dùng trong mạng "tấn công lẫn nhau" bằng dữ liệu, làm hacker ẩn danh.

> Khả năng giành được truy cập phụ thuộc vào kiến trúc và cấu hình hệ thống mục tiêu, trình độ của kẻ tấn công, và mức truy cập ban đầu đạt được. Sau khi vào được, kẻ tấn công sẽ leo thang đặc quyền để chiếm toàn quyền kiểm soát.

---

### Phase 4 — Maintaining Access (Duy trì truy cập)

**Maintaining access** là giai đoạn kẻ tấn công cố gắng **giữ quyền sở hữu hệ thống (ownership of the system)**. Khi đã có quyền admin/root (tức "sở hữu" hệ thống), kẻ tấn công có thể dùng hệ thống và tài nguyên của nó tùy ý.

| # | Nội dung |
|---|----------|
| 1 | Cố gắng giữ **quyền sở hữu hệ thống** |
| 2 | Ngăn hacker khác chiếm hệ thống bằng cách bảo vệ quyền truy cập độc quyền với **backdoors, rootkits, hoặc trojans** |
| 3 | Có thể upload, download, hoặc **thao túng dữ liệu (manipulate data)**, ứng dụng và cấu hình trên **hệ thống đã sở hữu (owned system)** |
| 4 | Dùng hệ thống bị xâm phạm để **khởi động các tấn công tiếp theo (launch further attacks)** |

- Hệ thống có thể được dùng làm bàn đạp (**launchpad**) để quét và khai thác các hệ thống khác, hoặc duy trì hồ sơ ẩn (low profile) để tiếp tục khai thác.
- Để không bị phát hiện, kẻ tấn công xóa bằng chứng xâm nhập và cài backdoor/trojan để truy cập lại. Có thể cài **rootkit** ở mức kernel để có toàn quyền quản trị.
  - **Rootkits** giành truy cập ở mức **operating system**.
  - **Trojans** giành truy cập ở mức **application**.
  - Trên Windows, hầu hết trojan tự cài như một **service** và chạy như một phần của hệ thống cục bộ với quyền quản trị.
- Có thể dùng trojan chuyển username, password và thông tin khác. Kẻ tấn công đôi khi **vá lỗ hổng** để ngăn hacker khác chiếm hệ thống — vô tình bảo vệ một phần hệ thống.

---

### Phase 5 — Clearing Tracks (Xóa dấu vết)

**Clearing tracks** là các hoạt động kẻ tấn công thực hiện để **che giấu hành vi độc hại (hide malicious acts)**, nhằm tránh rắc rối pháp lý và duy trì truy cập.

| # | Nội dung |
|---|----------|
| 1 | Clearing tracks là hoạt động kẻ tấn công thực hiện để **che giấu hành vi độc hại** |
| 2 | Ý định gồm: giữ **truy cập liên tục (continuing access)** vào hệ thống nạn nhân, không bị chú ý và không bị bắt (**unnoticed and uncaught**), và xóa bằng chứng có thể dẫn đến bị truy tố |
| 3 | **Ghi đè (overwrite)** các log của server, hệ thống và ứng dụng để **tránh bị nghi ngờ (avoid suspicion)** |

> **Kẻ tấn công luôn che giấu dấu vết để giấu danh tính.**

- Công cụ thường dùng: **PsTools** (https://docs.microsoft.com), **Netcat**, hoặc trojan để xóa footprint khỏi file log. Khi trojan đã được cài, kẻ tấn công có thể chạy script trong trojan/rootkit để thay thế các file hệ thống và log quan trọng.
- Kỹ thuật khác:
  - **Steganography:** giấu dữ liệu trong dữ liệu khác, ví dụ file ảnh và âm thanh.
  - **Tunneling:** lợi dụng giao thức truyền tải bằng cách "chở" giao thức này trong giao thức khác; kẻ tấn công có thể dùng khoảng trống nhỏ trong header TCP/IP của gói dữ liệu để giấu thông tin.

> Hệ thống bị xâm phạm có thể được dùng để khởi động tấn công mới hoặc làm bàn đạp tiếp cận hệ thống khác mà không bị phát hiện — biến giai đoạn này thành giai đoạn reconnaissance của một cuộc tấn công kế tiếp. Quản trị viên có thể triển khai **host-based IDS** và phần mềm antivirus để phát hiện trojan và các file/thư mục đáng ngờ. Ethical hacker cần hiểu rõ các công cụ và kỹ thuật này để khuyến nghị và triển khai biện pháp đối phó (sẽ trình bày ở các module sau).
