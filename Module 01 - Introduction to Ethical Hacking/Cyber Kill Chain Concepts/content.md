# Cyber Kill Chain Concepts

> Module 01 | Trang 12–26

## Giới thiệu

**Cyber kill chain** (chuỗi tiêu diệt mạng) là một cách hiệu quả để minh họa cách một kẻ tấn công (**adversary**) có thể tấn công tổ chức mục tiêu. Mô hình này giúp tổ chức hiểu các mối đe dọa khả dĩ tại **từng giai đoạn** của cuộc tấn công và các biện pháp đối phó (**countermeasures**) cần thiết để phòng thủ.

Mô hình cũng cung cấp cho chuyên gia an ninh cái nhìn rõ ràng về **chiến lược tấn công** mà kẻ tấn công sử dụng, để triển khai các mức độ kiểm soát bảo mật (**security controls**) khác nhau nhằm bảo vệ hạ tầng IT.

Phần này thảo luận:

- Phương pháp luận cyber kill chain (**cyber kill chain methodology**)
- Các **TTPs** phổ biến mà kẻ tấn công sử dụng
- Nhận diện hành vi của kẻ tấn công (**adversary behavioral identification**)
- Các dấu hiệu xâm phạm (**Indicators of Compromise – IoCs**)

---

## Cyber Kill Chain Methodology

**Cyber kill chain methodology** (phương pháp luận chuỗi tiêu diệt mạng) là một thành phần của phòng thủ dựa trên tình báo (**intelligence-driven defense**) nhằm **nhận diện và ngăn chặn** các hoạt động xâm nhập độc hại. Phương pháp này giúp chuyên gia an ninh xác định các bước mà kẻ tấn công tuân theo để đạt được mục tiêu của chúng.

Cyber kill chain là một framework được phát triển để bảo vệ không gian mạng dựa trên khái niệm **military kill chains** (chuỗi tiêu diệt quân sự). Phương pháp này nhằm tăng cường chủ động khả năng phát hiện và phản ứng xâm nhập, được trang bị cơ chế bảo vệ **7 giai đoạn** để giảm thiểu các mối đe dọa mạng.

Theo **Lockheed Martin**, một cuộc tấn công mạng có thể diễn ra qua **7 giai đoạn khác nhau**, từ reconnaissance (do thám) đến khi hoàn thành mục tiêu cuối cùng. Hiểu được phương pháp này giúp chuyên gia an ninh tận dụng các kiểm soát bảo mật ở từng giai đoạn, ngăn chặn tấn công trước khi nó thành công, đồng thời hiểu trước (**beforehand**) về TTPs của kẻ tấn công.

```
                Weaponization        Exploitation        Command and Control
                     🕷                   🕷                     🎩
                      \                  /  \                    /
                       \                /    \                  /
   Reconnaissance ──── Delivery ──── Installation ──── Actions on Objectives
        🔍              ✉ 🕷              ⬆                    💻
```

*Hình 1.2 — Cyber kill chain methodology (Module 01, trang 13–14)*

| Giai đoạn | Mô tả ngắn |
|-----------|-----------|
| **Reconnaissance** | Thu thập dữ liệu về mục tiêu để dò tìm điểm yếu |
| **Weaponization** | Tạo payload độc hại có thể phân phối bằng exploit và backdoor |
| **Delivery** | Gửi gói vũ khí hóa tới nạn nhân qua email, USB, v.v. |
| **Exploitation** | Khai thác lỗ hổng bằng cách thực thi mã trên hệ thống nạn nhân |
| **Installation** | Cài đặt malware lên hệ thống mục tiêu |
| **Command and Control (C2)** | Tạo kênh chỉ huy & điều khiển để liên lạc và truyền dữ liệu qua lại |
| **Actions on Objectives** | Thực hiện hành động để đạt mục tiêu/mục đích đã định |

---

### 1. Reconnaissance (Do thám)

Kẻ tấn công thực hiện reconnaissance để thu thập **càng nhiều thông tin càng tốt** về mục tiêu nhằm dò tìm điểm yếu trước khi thực sự tấn công. Chúng tìm các thông tin công khai trên Internet, thông tin mạng, thông tin hệ thống và thông tin tổ chức của mục tiêu.

Bằng cách do thám trên nhiều cấp độ mạng, kẻ tấn công có thể thu được **network blocks**, địa chỉ IP cụ thể và thông tin nhân viên. Chúng có thể dùng công cụ tự động để tìm cổng/dịch vụ mở, lỗ hổng ứng dụng và thông tin đăng nhập, hỗ trợ giành quyền truy cập backdoor vào mạng mục tiêu.

**Hoạt động của kẻ tấn công:**

- Thu thập thông tin về tổ chức mục tiêu qua Internet hoặc social engineering
- Phân tích các hoạt động trực tuyến và thông tin công khai
- Thu thập thông tin từ mạng xã hội và web services
- Lấy thông tin về các website đã truy cập
- Giám sát và phân tích website của tổ chức mục tiêu
- Thực hiện Whois, DNS và network footprinting
- Quét (scanning) để xác định cổng và dịch vụ mở

### 2. Weaponization (Vũ khí hóa)

Kẻ tấn công phân tích dữ liệu thu thập ở giai đoạn trước để xác định lỗ hổng và kỹ thuật có thể khai thác nhằm giành quyền truy cập trái phép. Dựa trên lỗ hổng đã xác định, chúng chọn hoặc tạo một **payload độc hại được tùy chỉnh** (remote-access malware weapon) bằng exploit và backdoor để gửi tới nạn nhân.

Kẻ tấn công có thể nhắm vào thiết bị mạng, hệ điều hành, thiết bị đầu cuối cụ thể hoặc cá nhân trong tổ chức. Ví dụ, gửi email phishing chứa tệp đính kèm độc hại như virus/worm; khi tải về sẽ cài backdoor cho phép truy cập từ xa.

**Hoạt động của kẻ tấn công:**

- Xác định payload malware phù hợp dựa trên phân tích
- Tạo payload mới hoặc chọn/tái sử dụng/sửa đổi payload có sẵn dựa trên lỗ hổng
- Tạo chiến dịch email phishing
- Tận dụng **exploit kits** và **botnets**

---

### 3. Delivery (Phân phối)

Payload vũ khí hóa được truyền tới nạn nhân — dưới dạng tệp đính kèm email, qua liên kết độc hại trên website, hoặc qua ứng dụng web/USB drive dễ bị tấn công. Delivery là giai đoạn then chốt đo lường **hiệu quả của chiến lược phòng thủ** của tổ chức, dựa trên việc nỗ lực xâm nhập có bị chặn hay không.

**Hoạt động của kẻ tấn công:**

- Gửi email phishing tới nhân viên tổ chức mục tiêu
- Phân phối USB chứa payload độc hại cho nhân viên
- Thực hiện tấn công như **watering hole** trên website đã bị xâm nhập
- Triển khai công cụ hacking nhắm vào OS, ứng dụng và server

### 4. Exploitation (Khai thác)

Sau khi vũ khí được truyền tới nạn nhân, exploitation **kích hoạt mã độc** của kẻ tấn công để khai thác lỗ hổng trong OS, ứng dụng hoặc server trên hệ thống mục tiêu. Ở giai đoạn này tổ chức có thể đối mặt các mối đe dọa như tấn công authentication/authorization, arbitrary code execution, đe dọa an ninh vật lý và cấu hình sai bảo mật (**security misconfiguration**).

**Hoạt động của kẻ tấn công:**

- Khai thác lỗ hổng phần mềm hoặc phần cứng để giành quyền truy cập từ xa vào hệ thống mục tiêu

---

### 5. Installation (Cài đặt)

Kẻ tấn công tải về và cài đặt thêm phần mềm độc hại lên hệ thống mục tiêu để **duy trì truy cập** trong thời gian dài. Chúng có thể dùng vũ khí để cài backdoor giành quyền truy cập từ xa. Sau khi tiêm mã độc vào một hệ thống, kẻ tấn công có khả năng lây lan sang các hệ thống khác trong mạng, đồng thời tìm cách **ẩn giấu** hoạt động độc hại khỏi các kiểm soát bảo mật như firewall bằng kỹ thuật như mã hóa.

**Hoạt động của kẻ tấn công:**

- Tải về và cài đặt phần mềm độc hại như backdoor
- Giành quyền truy cập từ xa vào hệ thống mục tiêu
- Tận dụng nhiều phương pháp để giữ backdoor ẩn và chạy ngầm
- Duy trì truy cập vào hệ thống mục tiêu

### 6. Command and Control (C2 – Chỉ huy và Điều khiển)

Kẻ tấn công tạo một **kênh command and control** thiết lập giao tiếp hai chiều giữa hệ thống nạn nhân và server do kẻ tấn công kiểm soát để truyền dữ liệu qua lại. Chúng dùng kỹ thuật như mã hóa để ẩn sự tồn tại của kênh này. Qua kênh này, kẻ tấn công thực hiện khai thác từ xa trên hệ thống/mạng.

**Hoạt động của kẻ tấn công:**

- Thiết lập kênh giao tiếp hai chiều giữa hệ thống nạn nhân và server do kẻ tấn công kiểm soát
- Tận dụng các kênh như web traffic, email và DNS messages
- Áp dụng kỹ thuật privilege escalation (leo thang đặc quyền)
- Che giấu bằng chứng xâm phạm bằng kỹ thuật như mã hóa

### 7. Actions on Objectives (Hành động trên mục tiêu)

Kẻ tấn công điều khiển hệ thống nạn nhân từ xa và cuối cùng hoàn thành mục tiêu đã định. Chúng truy cập dữ liệu mật, làm gián đoạn dịch vụ/mạng, hoặc phá hủy năng lực vận hành của mục tiêu bằng cách xâm nhập mạng và chiếm thêm hệ thống. Kẻ tấn công cũng có thể dùng đây làm **bàn đạp** (launching point) để thực hiện các tấn công khác.

---

## Tactics, Techniques, and Procedures (TTPs)

Thuật ngữ **Tactics, Techniques, and Procedures (TTPs)** chỉ các **mẫu hoạt động và phương pháp** (patterns of activities and methods) gắn với các threat actor (tác nhân đe dọa) cụ thể hoặc nhóm threat actor. TTPs hữu ích trong việc phân tích mối đe dọa và lập hồ sơ (**profiling**) threat actor, từ đó tăng cường hạ tầng bảo mật của tổ chức.

| Thành phần | Định nghĩa |
|-----------|-----------|
| **Tactics** (Chiến thuật) | Hướng dẫn mô tả **cách** kẻ tấn công thực hiện tấn công từ đầu đến cuối; gồm các chiến thuật thu thập thông tin cho khai thác ban đầu, leo thang đặc quyền, di chuyển ngang (lateral movement) và duy trì truy cập |
| **Techniques** (Kỹ thuật) | Các **phương pháp kỹ thuật** kẻ tấn công dùng để đạt kết quả trung gian trong cuộc tấn công; gồm khai thác ban đầu, thiết lập/duy trì kênh C2, truy cập hạ tầng, xóa dấu vết exfiltration dữ liệu |
| **Procedures** (Quy trình) | **Cách tiếp cận có tổ chức** mà threat actor tuân theo để phát động tấn công; số lượng hành động thường khác nhau tùy mục tiêu của quy trình và nhóm threat actor |

*Hình — Tactics, Techniques, and Procedures (TTPs) (Module 01, trang 17)*

Hiểu **tactics** giúp dự đoán và phát hiện mối đe dọa đang tiến hóa ở giai đoạn sớm. Hiểu **techniques** giúp xác định lỗ hổng và triển khai biện pháp phòng thủ trước. Phân tích **procedures** giúp hiểu kẻ tấn công đang tìm gì trong hạ tầng tổ chức. TTPs cho phép tổ chức **chặn tấn công ở giai đoạn đầu**, bảo vệ mạng khỏi thiệt hại lớn.

---

### Tactics

Tactics mô tả cách threat actor hoạt động qua các giai đoạn khác nhau của tấn công. Thông thường, các nhóm **APT** (Advanced Persistent Threat) dựa vào một bộ tactics **không đổi**, nhưng đôi khi chúng thích nghi với hoàn cảnh và thay đổi cách tấn công. Do đó, độ khó của việc phát hiện và quy kết (**attribution**) chiến dịch phụ thuộc vào tactics được dùng.

Tổ chức có thể profiling threat actor dựa trên tactics: cách chúng thu thập thông tin, phương pháp thỏa hiệp ban đầu, số điểm xâm nhập (entry points) khi cố vào mạng mục tiêu.

- **Ví dụ thu thập thông tin:** một số threat actor chỉ dựa vào thông tin công khai trên Internet, số khác dùng social engineering hoặc kết nối qua tổ chức trung gian.
- **Phân tích nhóm APT** còn dựa vào kiểm tra hạ tầng và công cụ. Ví dụ, server C2 có thể nằm tại vị trí địa lý cụ thể hoặc trải rộng trên Internet, tĩnh hoặc thay đổi động.
- Threat actor tinh vi có thể khai thác nhiều lỗ hổng **zero-day** bằng công cụ tùy chỉnh và phương pháp obfuscation; trong khi threat actor kém tinh vi dựa vào lỗ hổng đã biết công khai và công cụ mã nguồn mở.
- Một attacker có thể **liên tục thay đổi TTPs**, nên cần thường xuyên rà soát và cập nhật tactics của nhóm APT.

### Techniques

Để tấn công thành công, threat actor dùng nhiều techniques trong quá trình thực thi, gồm khai thác ban đầu, thiết lập/duy trì kênh C2, truy cập hạ tầng và xóa dấu vết exfiltration dữ liệu. Techniques có thể được phân tích ở **mỗi giai đoạn** của vòng đời mối đe dọa (threat life cycle).

- **Giai đoạn đầu:** techniques mô tả công cụ thu thập thông tin và khai thác ban đầu — không nhất thiết mang tính kỹ thuật (ví dụ social engineering qua điện thoại lừa nạn nhân tiết lộ thông tin đăng nhập).
- **Giai đoạn giữa:** chủ yếu dựa vào công cụ kỹ thuật để leo thang đặc quyền hoặc di chuyển ngang; khai thác lỗ hổng cấu hình hoặc lỗi thiết kế mạng.
- **Giai đoạn cuối:** mang cả khía cạnh kỹ thuật và phi kỹ thuật; data-stealing thường dựa vào công nghệ mạng và mã hóa (mã hóa tệp đánh cắp, truyền qua kênh C2). Sau đó dùng công cụ tự động xóa log để né phát hiện.

Sau khi tổng hợp techniques ở tất cả giai đoạn, tổ chức có thể profiling threat actor. Để quy kết chính xác (**attribution**), tổ chức phải quan sát **toàn bộ** techniques mà kẻ tấn công dùng.

### Procedures

**Procedures** bao gồm một chuỗi hành động mà threat actor thực hiện để thực thi các bước của vòng đời tấn công. Số lượng hành động thường khác nhau tùy mục tiêu của quy trình và nhóm APT. Threat actor cao cấp dùng quy trình nâng cao gồm **nhiều hành động hơn** so với quy trình thông thường để đạt cùng kết quả trung gian — nhằm tăng tỷ lệ thành công và giảm xác suất bị phát hiện.

**Ví dụ — quy trình thu thập thông tin:** kẻ tấn công thu thập thông tin về tổ chức; xác định mục tiêu chính, nhân viên và thông tin liên hệ; xác định hệ thống dễ bị tấn công và điểm xâm nhập tiềm năng; ghi lại toàn bộ thông tin thu thập.

Quy trình chi tiết hơn: lúc thực thi, mã độc tự giải mã, né kiểm soát giám sát bảo mật, triển khai persistence và thiết lập kênh C2 để liên lạc với hệ thống nạn nhân. Loại quy trình này phổ biến với malware, hữu ích cho **điều tra số (forensic investigations)**.

Trong giai đoạn đầu của tấn công (như thu thập thông tin), quan sát procedure của nhóm APT rất khó. Tuy nhiên, các giai đoạn sau có thể để lại **dấu vết (trails)** giúp hiểu procedure mà kẻ tấn công đã theo.

---

## Adversary Behavioral Identification

**Adversary behavioral identification** (nhận diện hành vi kẻ tấn công) bao gồm việc xác định các **phương pháp hoặc kỹ thuật phổ biến** mà kẻ tấn công dùng để phát động tấn công và xâm nhập mạng tổ chức. Nó cho chuyên gia an ninh cái nhìn về các **mối đe dọa và exploit sắp tới (upcoming threats and exploits)**, giúp lập kế hoạch hạ tầng bảo mật và thích nghi các quy trình phòng ngừa.

*Hình — Adversary Behaviors (Module 01, trang 21)*

| # | Hành vi | # | Hành vi | # | Hành vi |
|---|---------|---|---------|---|---------|
| 1 | Internal Reconnaissance | 4 | Use of Command-Line Interface | 7 | Use of DNS Tunneling |
| 2 | Use of PowerShell | 5 | HTTP User Agent | 8 | Use of Web Shell |
| 3 | Unspecified Proxy Activities | 6 | Command and Control Server | 9 | Data Staging |

### Internal Reconnaissance

Khi đã ở bên trong mạng mục tiêu, kẻ tấn công thực hiện do thám nội bộ: liệt kê (enumeration) hệ thống, host, process; thực thi các lệnh để tìm local user context, cấu hình hệ thống, hostname, địa chỉ IP, hệ thống từ xa đang hoạt động và chương trình đang chạy. Chuyên gia an ninh có thể giám sát bằng cách kiểm tra các **lệnh bất thường** trong Batch scripts và PowerShell, dùng công cụ packet capturing.

### Use of PowerShell

PowerShell có thể bị dùng làm công cụ tự động hóa **data exfiltration** và phát động tấn công tiếp theo. Để phát hiện lạm dụng PowerShell, chuyên gia an ninh kiểm tra **PowerShell transcript logs** hoặc **Windows Event logs**. User agent string và địa chỉ IP cũng giúp xác định host độc hại đang cố exfiltrate dữ liệu.

### Unspecified Proxy Activities

Kẻ tấn công có thể tạo và cấu hình nhiều **domain** trỏ về cùng một host, cho phép chuyển đổi nhanh giữa các domain để né phát hiện. Chuyên gia an ninh tìm các domain không xác định bằng cách kiểm tra **data feeds** do các domain đó tạo ra; qua đó cũng phát hiện tệp độc hại đã tải về và giao tiếp không mong muốn với mạng bên ngoài.

### Use of Command-Line Interface

Khi giành được truy cập, kẻ tấn công dùng **command-line interface** để tương tác với hệ thống: duyệt/đọc/sửa tệp, tạo tài khoản mới, kết nối hệ thống từ xa, tải và cài mã độc. Chuyên gia an ninh nhận diện bằng cách kiểm tra log tìm process ID, các process có **chữ và số tùy tiện (arbitrary letters and numbers)**, và tệp độc hại tải từ Internet.

### HTTP User Agent

Trong giao tiếp HTTP, server nhận diện client qua **user agent field**. Kẻ tấn công sửa nội dung trường này để giao tiếp với hệ thống đã bị xâm phạm và thực hiện tấn công tiếp. Chuyên gia an ninh có thể phát hiện sớm bằng cách kiểm tra nội dung của user agent field.

### Command and Control Server

Kẻ tấn công dùng **C2 server** để liên lạc từ xa với hệ thống bị xâm phạm qua phiên mã hóa, nhằm đánh cắp/xóa dữ liệu và phát động tấn công. Chuyên gia an ninh phát hiện host/mạng bị xâm phạm bằng cách theo dõi network traffic tìm các **nỗ lực kết nối ra ngoài (outbound connection attempts)**, cổng mở không mong muốn và các bất thường khác.

### Use of DNS Tunneling

Kẻ tấn công dùng **DNS tunneling** để ngụy trang traffic độc hại trong traffic hợp lệ của các giao thức phổ biến. DNS tunneling cho phép giao tiếp với C2 server, bypass kiểm soát bảo mật và exfiltrate dữ liệu. Chuyên gia an ninh nhận diện bằng cách phân tích **DNS request độc hại, DNS payload, domain không xác định và đích đến của DNS request**.

### Use of Web Shell

Kẻ tấn công dùng **web shell** để thao túng web server bằng cách tạo shell trong website, cho phép truy cập từ xa các chức năng của server. Qua web shell, chúng thực hiện data exfiltration, chuyển và tải tệp. Chuyên gia an ninh nhận diện web shell bằng cách phân tích **server access, error logs, chuỗi nghi vấn cho thấy encoding, user agent strings** và các phương pháp khác.

### Data Staging

Sau khi xâm nhập thành công, kẻ tấn công dùng kỹ thuật **data staging** để thu thập và gộp càng nhiều dữ liệu càng tốt: dữ liệu nhạy cảm về nhân viên và khách hàng, chiến thuật kinh doanh, thông tin tài chính, thông tin hạ tầng mạng. Sau khi thu thập, chúng có thể exfiltrate hoặc phá hủy dữ liệu. Chuyên gia an ninh phát hiện data staging bằng cách giám sát network traffic tìm **chuyển tệp độc hại, file integrity monitoring và event logs**.

---

## Indicators of Compromise (IoCs)

**Indicators of Compromise (IoCs)** là các **manh mối, dấu vết (artifacts) và mảnh dữ liệu pháp y (forensic data)** được tìm thấy trên mạng hoặc hệ điều hành của tổ chức, cho thấy khả năng có xâm nhập hoặc hoạt động độc hại trong hạ tầng.

IoCs **không phải là intelligence** (tình báo), nhưng đóng vai trò **nguồn thông tin tốt** về các mối đe dọa, phục vụ làm data point trong quy trình intelligence. **Actionable threat intelligence** trích xuất từ IoCs giúp tổ chức tăng cường chiến lược xử lý sự cố.

Chuyên gia an ninh cần **giám sát liên tục (continuous monitoring)** IoCs để phát hiện và phản ứng hiệu quả với các mối đe dọa mạng đang tiến hóa. Một số tổ chức như **STIX** và **TAXII** đã phát triển báo cáo chuẩn hóa chứa dữ liệu cô đọng về tấn công và chia sẻ để hỗ trợ phản ứng sự cố.

*Hình — Indicators of Compromise (IoCs) (Module 01, trang 24)*

### Các loại chỉ báo (theo bản chất)

| Loại chỉ báo | Mô tả | Ví dụ |
|--------------|-------|-------|
| **Atomic indicators** | Không thể chia nhỏ hơn, ý nghĩa không đổi trong ngữ cảnh xâm nhập | Địa chỉ IP, địa chỉ email |
| **Computed indicators** | Thu được từ dữ liệu trích xuất khỏi sự cố bảo mật | Giá trị hash, regular expressions |
| **Behavioral indicators** | Nhóm gộp cả atomic và computed indicators dựa trên một logic nào đó | (kết hợp logic của các chỉ báo trên) |

---

## Categories of Indicators of Compromise

Hiểu IoCs giúp chuyên gia an ninh **nhanh chóng phát hiện mối đe dọa** đối với tổ chức và bảo vệ khỏi các mối đe dọa tiến hóa. Vì mục đích này, IoCs được chia thành **4 loại**:

*Hình — Categories of Indicators of Compromise (Module 01, trang 25)*

| Loại IoC | Vai trò | Ví dụ |
|----------|---------|-------|
| **Email Indicators** | Email thường được kẻ tấn công ưu tiên để gửi dữ liệu độc hại tới mục tiêu (dễ dùng, ẩn danh tương đối) | Địa chỉ email người gửi, tiêu đề email, tệp đính kèm hoặc liên kết |
| **Network Indicators** | Hữu ích cho C2, phân phối malware, xác định OS/trình duyệt và thông tin máy tính khác | URL, domain name, địa chỉ IP |
| **Host-Based Indicators** | Tìm được bằng cách phân tích hệ thống bị nhiễm trong mạng tổ chức | Filename, file hash, registry key, DLL, mutex |
| **Behavioral Indicators** | Dùng để xác định hành vi cụ thể liên quan hoạt động độc hại | Tài liệu thực thi PowerShell script, remote command execution |

### Behavioral Indicators (chi tiết)

IoCs thông thường hữu ích để xác định dấu hiệu xâm nhập như IP độc hại, virus signatures, MD5 hash và domain names. **Behavioral IoCs** được dùng để xác định hành vi cụ thể liên quan đến hoạt động độc hại như **code injection vào memory** hoặc chạy script của ứng dụng. Các hành vi được định nghĩa rõ cho phép bảo vệ rộng, chặn cả hoạt động độc hại hiện tại lẫn tương lai, và hữu ích để nhận biết khi dịch vụ hệ thống hợp lệ bị dùng cho hoạt động bất thường. Ví dụ: tài liệu thực thi PowerShell script và remote command execution.

---

### Một số IoC quan trọng tiêu biểu

- Lưu lượng mạng ra ngoài bất thường (**Unusual outbound network traffic**)
- Hoạt động bất thường qua tài khoản người dùng đặc quyền (**privileged user account**)
- Bất thường địa lý (**Geographical anomalies**)
- Nhiều lần đăng nhập thất bại (**Multiple login failures**)
- Tăng lượng đọc database (**Increased database read volume**)
- Kích thước phản hồi HTML lớn (**Large HTML response size**)
- Nhiều yêu cầu cho cùng một tệp (**Multiple requests for the same file**)
- Lưu lượng cổng-ứng dụng không khớp (**Mismatched port-application traffic**)
- Thay đổi registry hoặc tệp hệ thống đáng ngờ (**Suspicious registry or system file changes**)
- DNS request bất thường (**Unusual DNS requests**)
- Vá hệ thống ngoài dự kiến (**Unexpected patching of systems**)
- Dấu hiệu hoạt động DDoS (**Signs of DDoS activity**)
- Các gói dữ liệu nằm sai vị trí (**Bundles of data in the wrong places**)
- Lưu lượng web với hành vi siêu phàm (**Web traffic with superhuman behavior**)
