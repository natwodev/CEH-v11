# Information Security Overview

> Module 01 | Trang 3–11

## Giới thiệu

**Information security** (an ninh thông tin) là việc bảo vệ thông tin và các hệ thống thông tin sử dụng, lưu trữ và truyền tải thông tin khỏi truy cập trái phép, tiết lộ, thay đổi và phá hủy.

Thông tin là tài sản quan trọng mà tổ chức phải bảo vệ. Nếu thông tin nhạy cảm rơi vào tay kẻ xấu, tổ chức có thể chịu thiệt hại lớn về tài chính, uy tín thương hiệu, khách hàng hoặc theo nhiều cách khác.

Phần này giới thiệu:

- Các yếu tố của an ninh thông tin
- Phân loại tấn công
- Information warfare

---

## Elements of Information Security

An ninh thông tin là trạng thái **an toàn** của thông tin và hạ tầng, trong đó khả năng **đánh cắp, giả mạo (tampering)** và **gián đoạn** thông tin/dịch vụ được giữ ở mức thấp hoặc chấp nhận được.

Năm yếu tố cốt lõi:

### 1. Confidentiality (Bảo mật)

Đảm bảo thông tin chỉ được truy cập bởi những người **được phép**.

- Vi phạm có thể do xử lý dữ liệu không đúng hoặc tấn công hacking
- Biện pháp: phân loại dữ liệu, mã hóa, tiêu hủy thiết bị lưu trữ đúng cách (DVD, USB, Blu-ray, …)

### 2. Integrity (Toàn vẹn)

Độ tin cậy của dữ liệu/tài nguyên — ngăn thay đổi trái phép hoặc không phù hợp.

- Biện pháp: **checksum** (hàm toán học xác minh dữ liệu không bị đổi), **access control** (chỉ người được phép mới cập nhật/thêm/xóa)

### 3. Availability (Sẵn sàng)

Đảm bảo hệ thống lưu trữ, xử lý và cung cấp thông tin **luôn truy cập được** khi người dùng được phép cần.

- Biện pháp: disk array, clustered machines, antivirus, hệ thống chống DDoS

### 4. Authenticity (Xác thực)

Đặc tính đảm bảo thông tin, giao tiếp hoặc tài liệu là **genuine** (thật, không bị giả mạo).

- Vai trò chính của authentication: xác nhận người dùng là thật
- Biện pháp: sinh trắc học, smart card, chứng chỉ số (digital certificates)

### 5. Non-Repudiation (Không thể chối bỏ)

Đảm bảo người gửi **không thể phủ nhận** đã gửi tin nhắn và người nhận **không thể phủ nhận** đã nhận.

- Biện pháp: **chữ ký số** (digital signatures)

---

## Motives, Goals, and Objectives of Information Security Attacks

```
Attacks = Motive (Goal) + Method + Vulnerability
```

**Motive** (động cơ) xuất phát từ việc hệ thống mục tiêu lưu trữ hoặc xử lý thứ gì đó **có giá trị**, dẫn đến mối đe dọa tấn công. Kẻ tấn công dùng công cụ và kỹ thuật để khai thác lỗ hổng trong hệ thống, chính sách bảo mật hoặc biện pháp kiểm soát nhằm đạt mục tiêu.

**Động cơ phổ biến:**

| | |
|---|---|
| Phá gián đoạn hoạt động kinh doanh | Đánh cắp và thao túng dữ liệu |
| Gây sợ hãi, hỗn loạn qua hạ tầng trọng yếu | Gây thiệt hại tài chính |
| Truyền bá tín ngưỡng/chính trị | Đạt mục tiêu quân sự của quốc gia |
| Làm hại danh tiếng mục tiêu | Trả thù |
| Đòi tiền chuộc (ransom) | |

---

## Classification of Attacks

Theo **IATF** (Information Assurance Technical Framework), tấn công được phân thành **5 loại**:

### Passive Attacks (Tấn công thụ động)

- **Không** thay đổi dữ liệu; chặn và giám sát lưu lượng mạng
- Rất khó phát hiện vì không tương tác chủ động với hệ thống mục tiêu
- Mục tiêu: thu thập dữ liệu để dùng cho tấn công chủ động sau này

**Ví dụ:** footprinting, sniffing/eavesdropping, phân tích lưu lượng mạng, giải mã traffic mã hóa yếu

### Active Attacks (Tấn công chủ động)

- Thay đổi dữ liệu đang truyền hoặc phá vỡ dịch vụ/giao tiếp
- Gửi traffic chủ động → **có thể phát hiện**
- Xâm nhập mạng nội bộ, chiếm hệ thống từ xa

**Ví dụ:**

| | |
|---|---|
| DoS | Firewall và IDS attack |
| Bypass cơ chế bảo vệ | Profiling |
| Malware (virus, worm, ransomware) | Arbitrary code execution |
| Sửa đổi thông tin | Privilege escalation |
| Spoofing, replay | Backdoor access |
| Password-based attacks | Cryptography attacks |
| Session hijacking | SQL injection |
| Man-in-the-Middle | XSS |
| DNS và ARP poisoning | Directory traversal |
| Compromised-key attack | Khai thác lỗi ứng dụng/OS |

### Close-in Attacks (Tấn công cận cảnh)

- Kẻ tấn công ở **gần vật lý** với hệ thống/mạng mục tiêu
- Mục tiêu: thu thập/sửa thông tin hoặc chặn truy cập
- Tiếp cận qua xâm nhập lén, truy cập mở hoặc cả hai

**Ví dụ:** social engineering — eavesdropping, shoulder surfing, dumpster diving

### Insider Attacks (Tấn công nội bộ)

- Do người **được tin cậy** có quyền truy cập vật lý vào tài sản quan trọng
- Lạm dụng quyền hạn, bỏ qua quy tắc bảo mật, truy cập dữ liệu nhạy cảm
- Ảnh hưởng CIA; khó phát hiện, tổn hại lớn đến hoạt động và uy tín

**Ví dụ:** eavesdropping, wiretapping, trộm thiết bị vật lý, social engineering, data theft/spoliation, pod slurping, cài keylogger/backdoor/malware

### Distribution Attacks (Tấn công phân phối)

- Can thiệp **phần cứng hoặc phần mềm trước khi cài đặt** — tại nguồn hoặc khi vận chuyển
- Ví dụ: backdoor do nhà sản xuất tạo sẵn lúc sản xuất

**Ví dụ:**

- Sửa phần mềm/phần cứng trong quá trình sản xuất
- Sửa phần mềm/phần cứng trong quá trình phân phối

---

## Information Warfare

> Nguồn: http://www.iwar.org.uk

**Information warfare (InfoWar)** là việc sử dụng công nghệ thông tin và truyền thông (**ICT**) để đạt lợi thế cạnh tranh trước đối thủ.

**Vũ khí InfoWar:** virus, worm, Trojan horse, logic bomb, trap door, nanomachines/microbes, electronic jamming, penetration exploits và công cụ.

### Phân loại theo Martin Libicki

| Loại | Mô tả |
|------|--------|
| **Command and control warfare (C2)** | Mức độ kiểm soát kẻ tấn công có trên hệ thống/mạng đã bị xâm nhập |
| **Intelligence-based warfare** | Công nghệ cảm biến làm hỏng hệ thống kỹ thuật; thiết kế, bảo vệ và từ chối hệ thống để chiếm ưu thế trên chiến trường |
| **Electronic warfare** | Kỹ thuật radio-electronic (tấn công phương tiện vật lý truyền tin) và cryptographic (dùng bit/byte phá vỡ truyền tin) |
| **Psychological warfare** | Propaganda, khủng bố để làm suy giảm tinh thần đối phương |
| **Hacker warfare** | Tắt hệ thống, lỗi dữ liệu, đánh cắp thông tin/dịch vụ, giám sát, tin nhắn giả, truy cập dữ liệu — thường dùng virus, logic bomb, Trojan, sniffer |
| **Economic warfare** | Ảnh hưởng kinh tế doanh nghiệp/quốc gia bằng cách chặn dòng thông tin |
| **Cyberwarfare** | Dùng hệ thống thông tin chống lại persona ảo của cá nhân/nhóm; bao gồm information terrorism, semantic attacks (chiếm hệ thống nhưng vẫn tạo cảm giác hoạt động bình thường), simula-warfare (mô phỏng chiến tranh) |

### Defensive vs Offensive

| Defensive Information Warfare | Offensive Information Warfare |
|------------------------------|------------------------------|
| Chiến lược và hành động **phòng thủ** tài sản ICT | Tấn công vào tài sản ICT của đối phương |
| Prevention, Deterrence, Alerts, Detection, Emergency Preparedness, Response | Web Application Attacks, Web Server Attacks, Malware Attacks, MITM, System Hacking |

```
[Defensive]  ←—— Internet ——→  [Offensive]
 INFO SECURITY                    Tấn công
```

*Hình 1.1 — Block Diagram of Information Warfare (Module 01, trang 11)*
