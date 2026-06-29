# Footprinting Concepts

> Module 02 | Trang 3–9

## Giới thiệu

**Ethical hacking** (hack có đạo đức) mang bản chất hợp pháp và được tiến hành để đánh giá an ninh hạ tầng IT của tổ chức mục tiêu **với sự đồng ý** của họ. **Footprinting** — khi kẻ tấn công cố gắng thu thập thông tin về mục tiêu — là **bước đầu tiên** trong ethical hacking. Đây là giai đoạn chuẩn bị, kẻ tấn công cần thu thập càng nhiều thông tin càng tốt để dễ dàng tìm cách xâm nhập mạng mục tiêu.

Phần này giới thiệu về footprinting, lý do cần thiết và các mục tiêu của nó.

### Module Flow

| # | Nội dung |
|---|----------|
| **1** | **Footprinting Concepts** |
| 2 | Footprinting Methodology |
| 3 | Footprinting Tools |
| 4 | Footprinting Countermeasures |

*Hình 2.1 — Module Flow (Module 02, trang 94)*

---

## What is Footprinting?

**Footprinting** là bước đầu tiên của bất kỳ cuộc tấn công nào vào hệ thống thông tin, trong đó kẻ tấn công **thu thập thông tin về một mạng mục tiêu** để xác định các cách khác nhau nhằm xâm nhập hệ thống.

Một khía cạnh thiết yếu của footprinting là xác định **mức độ rủi ro** liên quan đến thông tin công khai có thể truy cập được của tổ chức. Là bước đầu tiên trong ethical hacking, footprinting đề cập đến quá trình thu thập thông tin về mạng mục tiêu và môi trường của nó. Thông qua footprinting, ta tìm ra nhiều cơ hội để thâm nhập và đánh giá mạng của tổ chức mục tiêu.

Sau khi hoàn tất footprinting một cách có phương pháp, ta sẽ có được **"blueprint"** (bản thiết kế) — hồ sơ hệ thống độc nhất (unique system profile) về hồ sơ bảo mật của tổ chức mục tiêu.

Không có một phương pháp luận duy nhất nào cho footprinting, vì thông tin có thể được truy vết theo nhiều cách. Tuy nhiên, hoạt động này rất quan trọng vì cần thu thập tất cả thông tin then chốt về tổ chức mục tiêu **trước khi** bắt đầu giai đoạn hacking. Do đó, footprinting cần được thực hiện một cách có tổ chức. Thông tin thu thập ở bước này giúp phát hiện lỗ hổng tồn tại trong mạng mục tiêu và xác định các cách khai thác chúng.

### Tổng quan (sơ đồ)

| Types of Footprinting | Information Obtained | Objectives of Footprinting |
|-----------------------|----------------------|----------------------------|
| **Passive Footprinting** — thu thập thông tin **không tương tác trực tiếp** | **Organization information** — chi tiết nhân viên, số điện thoại, vị trí, bối cảnh, công nghệ web, … | Knowledge of security posture (hiểu rõ thế trận bảo mật) |
| **Active Footprinting** — thu thập thông tin **có tương tác trực tiếp** | **Network information** — domain và sub-domain, network blocks, địa chỉ IP của hệ thống truy cập được, Whois record, DNS, … | Reduction of focus area (thu hẹp phạm vi tập trung) |
| | **System information** — OS, vị trí web server, users và passwords, … | Identifying vulnerabilities (xác định lỗ hổng) |
| | | Drawing of network map (vẽ bản đồ mạng) |

*Hình 2.2 — What is Footprinting? (Module 02, trang 95)*

---

## Types of Footprinting

Footprinting được phân thành **passive footprinting** và **active footprinting**.

### Passive Footprinting (Footprinting thụ động)

Passive footprinting là thu thập thông tin về mục tiêu **mà không tương tác trực tiếp**. Cách này chủ yếu hữu ích khi không muốn bị mục tiêu phát hiện hoạt động thu thập thông tin. Thực hiện passive footprinting về mặt kỹ thuật khá khó vì **không gửi traffic chủ động** đến tổ chức mục tiêu từ một host hoặc từ các host/dịch vụ ẩn danh qua Internet. Ta chỉ có thể thu thập thông tin được lưu trữ và lưu trữ qua các công cụ như search engine, mạng xã hội, v.v.

**Kỹ thuật passive footprinting:**

- Tìm thông tin qua search engine
- Tìm Top-level Domains (TLDs) và sub-domain của mục tiêu qua web services
- Thu thập thông tin vị trí của mục tiêu qua web services
- Tìm kiếm người (people search) qua mạng xã hội và dịch vụ tìm người
- Thu thập thông tin tài chính về mục tiêu qua dịch vụ tài chính
- Thu thập chi tiết hạ tầng của tổ chức mục tiêu qua các trang tuyển dụng (job sites)
- Thu thập thông tin qua deep web và dark web footprinting
- Xác định hệ điều hành (operating systems) mà tổ chức mục tiêu đang dùng
- Thực hiện competitive intelligence (tình báo cạnh tranh)
- Giám sát mục tiêu bằng dịch vụ cảnh báo (alert services)
- Thu thập thông tin qua groups, forums, blogs và NNTP Usenet newsgroups
- Thu thập thông tin qua social engineering trên mạng xã hội
- Trích xuất thông tin về mục tiêu qua Internet archives
- Thu thập thông tin qua các trang hồ sơ doanh nghiệp (business profile sites)
- Giám sát lưu lượng truy cập website của mục tiêu
- Theo dõi danh tiếng trực tuyến (online reputation) của mục tiêu

### Active Footprinting (Footprinting chủ động)

Active footprinting là thu thập thông tin về mục tiêu **có tương tác trực tiếp**. Trong active footprinting, mục tiêu **có thể nhận ra** quá trình thu thập thông tin đang diễn ra vì ta tương tác công khai với mạng mục tiêu. Active footprinting đòi hỏi chuẩn bị nhiều hơn passive footprinting, vì có thể để lại dấu vết cảnh báo tổ chức mục tiêu.

**Kỹ thuật active footprinting:**

- Truy vấn các name server đã công bố của mục tiêu
- Tìm kiếm các tệp số (digital files)
- Trích xuất liên kết website và thu thập wordlist từ website mục tiêu
- Trích xuất metadata của tài liệu và tệp đã công bố
- Thu thập thông tin website bằng công cụ web spidering và mirroring
- Thu thập thông tin qua email tracking
- Thu thập danh sách email (harvesting email lists)
- Thực hiện Whois lookup
- Trích xuất thông tin DNS
- Thực hiện phân tích traceroute
- Thực hiện social engineering

---

## Information Obtained in Footprinting

Các mục tiêu chính của footprinting bao gồm thu thập **network information**, **system information** và **organizational information** của mục tiêu. Bằng cách footprinting ở các cấp mạng khác nhau, ta có thể thu được thông tin như network blocks, địa chỉ IP cụ thể, chi tiết nhân viên, v.v. Những thông tin này giúp kẻ tấn công truy cập dữ liệu nhạy cảm hoặc thực hiện nhiều dạng tấn công vào mạng mục tiêu.

### Organization Information (Thông tin tổ chức)

Thông tin này có sẵn từ website của tổ chức. Ngoài ra, có thể truy vấn domain name của mục tiêu trong cơ sở dữ liệu **Whois** để thu thập thông tin giá trị.

Thông tin thu thập gồm:

- Chi tiết nhân viên (tên, địa chỉ liên hệ, chức danh, kinh nghiệm làm việc)
- Địa chỉ và số điện thoại di động/cố định
- Chi tiết chi nhánh và vị trí
- Đối tác của tổ chức
- Web links tới các site liên quan của công ty
- Bối cảnh (background) của tổ chức
- Web technologies (công nghệ web)
- Tin tức, thông cáo báo chí và tài liệu liên quan
- Tài liệu pháp lý liên quan đến tổ chức
- Bằng sáng chế (patents) và thương hiệu (trademarks) liên quan đến tổ chức

Kẻ tấn công có thể truy cập thông tin tổ chức để xác định nhân sự chủ chốt và phát động tấn công social engineering nhằm trích xuất dữ liệu nhạy cảm.

### Network Information (Thông tin mạng)

Có thể thu thập network information bằng cách phân tích cơ sở dữ liệu Whois, trace routing, v.v.

Thông tin thu thập gồm:

- Domain và sub-domains
- Network blocks
- Network topology, trusted routers và firewalls
- Địa chỉ IP của các hệ thống truy cập được
- Whois records
- DNS records và thông tin liên quan

### System Information (Thông tin hệ thống)

Có thể thu thập system information bằng cách thực hiện network footprinting, DNS footprinting, website footprinting, email footprinting, v.v.

Thông tin thu thập gồm:

- Web server OS
- Vị trí của web server
- Địa chỉ email công khai
- Usernames, passwords, v.v.

---

## Objectives of Footprinting

Để xây dựng chiến lược tấn công, kẻ tấn công cần thu thập thông tin về mạng của tổ chức mục tiêu, rồi dùng thông tin đó để tìm cách dễ nhất nhằm vượt qua vành đai bảo mật (security perimeter). Như đã đề cập, footprinting methodology giúp việc thu thập thông tin trở nên dễ dàng và đóng vai trò quan trọng trong quá trình hacking.

**Footprinting giúp:**

- **Know Security Posture** (Nắm thế trận bảo mật): Footprinting cung cấp hồ sơ đầy đủ về thế trận bảo mật của tổ chức. Hacker có thể phân tích báo cáo để tìm lỗ hổng trong thế trận bảo mật và xây dựng kế hoạch hacking phù hợp.
- **Reduce Focus Area** (Thu hẹp phạm vi tập trung): Bằng cách kết hợp công cụ và kỹ thuật, kẻ tấn công có thể lấy một thực thể chưa biết (ví dụ XYZ Organization) và thu hẹp nó xuống một dải cụ thể gồm domain names, network blocks và các địa chỉ IP riêng lẻ của hệ thống kết nối trực tiếp Internet, cùng nhiều chi tiết khác liên quan đến thế trận bảo mật.
- **Identify Vulnerabilities** (Xác định lỗ hổng): Một footprint chi tiết cung cấp tối đa thông tin về tổ chức mục tiêu, cho phép kẻ tấn công xác định lỗ hổng trong hệ thống mục tiêu để chọn exploit phù hợp. Kẻ tấn công có thể tự xây dựng cơ sở dữ liệu về các điểm yếu bảo mật của mục tiêu, từ đó giúp tìm ra mắt xích yếu nhất trong vành đai bảo mật.
- **Draw Network Map** (Vẽ bản đồ mạng): Kết hợp kỹ thuật footprinting với các công cụ như **Tracert** cho phép kẻ tấn công tạo biểu diễn sơ đồ về sự hiện diện mạng của tổ chức mục tiêu. Cụ thể, nó cho phép vẽ bản đồ/phác thảo hạ tầng mạng để hiểu môi trường thực tế mà chúng định xâm nhập. Bản đồ mạng phản ánh hiểu biết của kẻ tấn công về footprint Internet của mục tiêu và có thể dẫn dắt việc thực hiện tấn công.

---

## Footprinting Threats (Các mối đe dọa từ Footprinting)

Kẻ tấn công thực hiện footprinting như bước đầu của bất kỳ cuộc tấn công nào vào hệ thống thông tin. Trong giai đoạn này, chúng cố thu thập thông tin cấp hệ thống có giá trị như account details, phiên bản hệ điều hành và phần mềm, tên server, chi tiết database schema, v.v. — hữu ích cho quá trình hacking.

Các mối đe dọa phát sinh từ footprinting:

- **Social Engineering**: Không cần dùng phương pháp xâm nhập, hacker thu thập thông tin trực tiếp và gián tiếp qua thuyết phục và các cách khác. Hacker lấy thông tin then chốt từ nhân viên sẵn lòng cung cấp mà không nhận ra ý đồ của hacker.
- **System and Network Attacks**: Footprinting cho phép kẻ tấn công thu thập thông tin về cấu hình hệ thống, hệ điều hành đang chạy, v.v. của tổ chức mục tiêu. Dựa vào đó, chúng tìm lỗ hổng và khai thác để chiếm quyền kiểm soát hệ thống mục tiêu hoặc toàn bộ mạng.
- **Information Leakage** (Rò rỉ thông tin): Rò rỉ thông tin là mối đe dọa với bất kỳ tổ chức nào. Nếu thông tin nhạy cảm rơi vào tay kẻ tấn công, chúng có thể dựa vào đó để tấn công hoặc dùng cho mục đích thu lợi tài chính.
- **Privacy Loss** (Mất quyền riêng tư): Qua footprinting, hacker có thể truy cập hệ thống và mạng của tổ chức, thậm chí leo thang đặc quyền lên cấp admin, dẫn đến mất quyền riêng tư cho cả tổ chức lẫn từng cá nhân.
- **Corporate Espionage** (Gián điệp doanh nghiệp): Đây là mối đe dọa trọng tâm, vì đối thủ thường tìm cách chiếm dữ liệu nhạy cảm qua footprinting. Với cách này, đối thủ có thể tung sản phẩm tương tự ra thị trường, thay đổi giá và làm suy yếu vị thế thị trường của tổ chức mục tiêu.
- **Business Loss** (Tổn thất kinh doanh): Footprinting có thể ảnh hưởng lớn đến các tổ chức như doanh nghiệp trực tuyến, website thương mại điện tử, ngân hàng và tài chính. Hàng tỷ đô la bị mất mỗi năm do các cuộc tấn công độc hại của hacker.

---

## Footprinting Methodology (giới thiệu)

Sau khi đã quen với các khái niệm và mối đe dọa của footprinting, phần tiếp theo bàn về **footprinting methodology** — quy trình thu thập thông tin về tổ chức mục tiêu từ tất cả nguồn có sẵn. Nó bao gồm thu thập thông tin như URLs, vị trí, chi tiết thành lập, số lượng nhân viên, dải domain names cụ thể, thông tin liên hệ và các thông tin liên quan khác. Kẻ tấn công thu thập những thông tin này từ các nguồn công khai như search engine, mạng xã hội, cơ sở dữ liệu Whois, v.v.

**Footprinting techniques (kỹ thuật footprinting):**

- Footprinting qua search engine
- Footprinting qua web services
- Footprinting qua mạng xã hội (social networking sites)
- Website footprinting
- Email footprinting
- Whois footprinting
- DNS footprinting
- Network footprinting
- Footprinting qua social engineering

*Hình 2.3 — Module Flow: Footprinting Methodology (Module 02, trang 100)*
