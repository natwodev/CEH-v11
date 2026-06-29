# Information Security Controls

> Module 01 | Trang 47–75

## Giới thiệu

**Information security controls** (biện pháp kiểm soát an ninh thông tin) giúp ngăn chặn các sự kiện không mong muốn xảy ra và giảm rủi ro cho tài sản thông tin của tổ chức.

- Các khái niệm bảo mật cơ bản đối với thông tin trên Internet: **confidentiality** (bảo mật), **integrity** (toàn vẹn), **availability** (sẵn sàng).
- Các khái niệm liên quan đến người truy cập thông tin: **authentication** (xác thực), **authorization** (phân quyền), **non-repudiation** (không thể chối bỏ).

Thông tin là tài sản lớn nhất của tổ chức, phải được bảo vệ bằng nhiều chính sách, tạo nhận thức (awareness), triển khai cơ chế bảo mật hoặc các biện pháp khác.

Phần này trình bày các chủ đề:

- Information Assurance (IA)
- Defense-in-Depth
- Risk Management
- Cyber Threat Intelligence
- Threat Modeling
- Incident Management
- AI và ML trong an ninh mạng

---

## Information Assurance (IA)

**Information Assurance (IA — bảo đảm thông tin)** là sự bảo đảm về **integrity, availability, confidentiality và authenticity** của thông tin và hệ thống thông tin trong suốt quá trình **sử dụng, xử lý, lưu trữ và truyền tải**.

Chuyên gia bảo mật đạt được IA nhờ các biện pháp kiểm soát **physical** (vật lý), **technical** (kỹ thuật) và **administrative** (hành chính). IA cùng với **Information Risk Management (IRM)** đảm bảo chỉ nhân sự được phép mới truy cập và sử dụng thông tin, qua đó đạt được an ninh thông tin và **business continuity** (liên tục kinh doanh).

### Các quy trình giúp đạt được Information Assurance

1. **Xây dựng chính sách, quy trình và hướng dẫn nội bộ** sao cho duy trì hệ thống thông tin ở mức bảo mật tối ưu.
2. **Thiết kế chiến lược xác thực mạng và người dùng** — mạng an toàn đảm bảo riêng tư cho hồ sơ người dùng và thông tin khác; chiến lược xác thực người dùng hiệu quả bảo vệ dữ liệu của hệ thống.
3. **Nhận diện lỗ hổng và mối đe dọa mạng** — vulnerability assessment phác họa tình trạng bảo mật của mạng, giúp đưa ra biện pháp khắc phục phù hợp.
4. **Xác định vấn đề và yêu cầu tài nguyên.**
5. **Lập kế hoạch cho các yêu cầu tài nguyên đã xác định.**
6. **Áp dụng các biện pháp kiểm soát IA phù hợp.**
7. **Thực hiện quy trình Certification and Accreditation (C&A)** của hệ thống thông tin nhằm truy vết lỗ hổng và triển khai biện pháp an toàn để vô hiệu hóa chúng.
8. **Cung cấp đào tạo information assurance** cho toàn bộ nhân sự trong các tổ chức công và tư, nâng cao nhận thức về công nghệ thông tin.

---

## Defense-in-Depth

**Defense-in-depth** (phòng thủ theo chiều sâu) là chiến lược bảo mật trong đó các chuyên gia bảo mật đặt **nhiều lớp bảo vệ (protection layers)** xuyên suốt hệ thống thông tin.

Chiến lược dựa trên nguyên lý quân sự: đánh bại một hệ thống phòng thủ **phức tạp, nhiều lớp** khó hơn nhiều so với xuyên thủng một rào cản đơn lẻ.

- Giúp **ngăn tấn công trực tiếp** vào hệ thống và dữ liệu, vì phá vỡ một lớp chỉ dẫn kẻ tấn công đến lớp tiếp theo.
- Nếu hacker xâm nhập được hệ thống, defense-in-depth giảm thiểu tác động xấu và cho quản trị viên/kỹ sư thời gian triển khai biện pháp đối phó mới hoặc cập nhật để ngăn tái diễn.

Các lớp phòng thủ (từ ngoài vào trong):

```
┌──────────────────────────────────────────┐
│  Policies, Procedures, and Awareness       │
│  ┌──────────────────────────────────────┐ │
│  │  Physical                              │ │
│  │  ┌──────────────────────────────────┐ │ │
│  │  │  Perimeter                        │ │ │
│  │  │  ┌──────────────────────────────┐ │ │ │
│  │  │  │  Internal Network             │ │ │ │
│  │  │  │  ┌──────────────────────────┐ │ │ │ │
│  │  │  │  │  Host                     │ │ │ │ │
│  │  │  │  │  ┌──────────────────────┐ │ │ │ │ │
│  │  │  │  │  │  Application          │ │ │ │ │ │
│  │  │  │  │  │  ┌──────────────────┐ │ │ │ │ │ │
│  │  │  │  │  │  │  Data             │ │ │ │ │ │ │
│  │  │  │  │  │  └──────────────────┘ │ │ │ │ │ │
│  │  │  │  │  └──────────────────────┘ │ │ │ │ │
│  │  │  │  └──────────────────────────┘ │ │ │ │
│  │  │  └──────────────────────────────┘ │ │ │
│  │  └──────────────────────────────────┘ │ │
│  └──────────────────────────────────────┘ │
└──────────────────────────────────────────┘
```

*Hình 1.3 — Defense in Depth (Module 01, trang 50)*

---

## Risk Management

### What is Risk? (Rủi ro là gì?)

**Risk** (rủi ro) là mức độ **uncertainty** (bất định) hoặc kỳ vọng về thiệt hại tiềm tàng mà một sự kiện bất lợi có thể gây ra cho hệ thống hoặc tài nguyên, trong những điều kiện xác định. Rủi ro cũng có thể hiểu là:

- Xác suất xảy ra của một threat hoặc sự kiện gây thiệt hại, tổn thất hay tác động tiêu cực đến tổ chức (từ trách nhiệm nội bộ hoặc bên ngoài).
- Khả năng một threat tác động lên một vulnerability nội bộ/bên ngoài và gây hại cho tài nguyên.
- Tích của likelihood (khả năng) một sự kiện xảy ra và impact (tác động) sự kiện đó có thể gây ra cho tài sản CNTT.

Quan hệ giữa Risk, Threats, Vulnerabilities và Impact:

```
RISK = Threats x Vulnerabilities x Impact

RISK = Threat x Vulnerability x Asset Value
```

Rủi ro là sự kết hợp của hai yếu tố:

- **Xác suất** xảy ra của một sự kiện bất lợi.
- **Hậu quả (consequence)** của sự kiện bất lợi.

### Risk Level (Mức độ rủi ro)

Risk level là đánh giá tác động tạo ra trên mạng. Một phương pháp phổ biến để phân loại rủi ro là xây dựng **ma trận hai chiều (two-dimensional matrix)**.

```
Level of Risk = Consequence x Likelihood
```

Rủi ro được phân thành các mức theo tác động ước tính lên hệ thống. Chủ yếu có **bốn mức**: extreme, high, medium và low. Lưu ý: biện pháp kiểm soát có thể giảm mức rủi ro nhưng không phải lúc nào cũng loại bỏ hoàn toàn.

| Risk Level | Consequence | Action |
|------------|-------------|--------|
| **Extreme or High** | Serious or Imminent danger (nguy hiểm nghiêm trọng/cận kề) | • Cần biện pháp tức thì để xử lý rủi ro<br>• Xác định và áp đặt controls để giảm rủi ro xuống mức thấp hợp lý |
| **Medium** | Moderate danger (nguy hiểm vừa phải) | • Không cần hành động tức thì nhưng nên triển khai nhanh<br>• Áp dụng controls sớm nhất có thể để giảm rủi ro xuống mức thấp hợp lý |
| **Low** | Negligible danger (nguy hiểm không đáng kể) | • Thực hiện các bước phòng ngừa để giảm nhẹ ảnh hưởng của rủi ro |

*Bảng 1.1 — Risk Levels (Module 01, trang 52)*

### Risk Matrix (Ma trận rủi ro)

Risk matrix biểu diễn **likelihood** (khả năng/xác suất xảy ra) cùng với **consequences** (hậu quả/tác động) của rủi ro. Đây là biểu diễn đồ họa về mức độ nghiêm trọng của rủi ro và mức độ mà controls có thể giảm nhẹ. Risk matrix là một trong những quy trình đơn giản nhất để tăng khả năng nhìn nhận rủi ro và hỗ trợ ra quyết định của ban quản lý. Có nhiều risk matrix tiêu chuẩn, nhưng mỗi tổ chức nên tự xây dựng cho riêng mình.

| Probability | | Insignificant | Minor | Moderate | Major | Severe |
|-------------|---|---|---|---|---|---|
| 81–100% | Very High Probability | Low | Medium | High | Extreme | Extreme |
| 61–80% | High Probability | Low | Medium | High | High | Extreme |
| 41–60% | Equal Probability | Low | Medium | Medium | High | High |
| 21–40% | Low Probability | Low | Low | Medium | Medium | High |
| 1–20% | Very Low Probability | Low | Low | Medium | Medium | High |

*Bảng 1.2 — Risk Matrix (cột ngang = Consequences, hàng dọc = Likelihood) (Module 01, trang 53)*

- **Likelihood:** khả năng rủi ro xảy ra.
- **Consequence:** mức độ nghiêm trọng của sự kiện rủi ro khi xảy ra.

> **Lưu ý:** Đây chỉ là ví dụ về risk matrix. Tổ chức phải tự tạo ma trận rủi ro riêng dựa trên nhu cầu kinh doanh của mình.

### Risk Management (Quản lý rủi ro)

**Risk management** là quá trình nhận diện, đánh giá, ứng phó và triển khai các hoạt động kiểm soát cách tổ chức quản lý tác động tiềm tàng của rủi ro. Đây là quá trình **liên tục** và ngày càng phức tạp, giữ vị trí quan trọng xuyên suốt vòng đời bảo mật.

**Mục tiêu của Risk Management:**

- Nhận diện rủi ro tiềm tàng — đây là mục tiêu chính.
- Nhận diện tác động của rủi ro, giúp tổ chức xây dựng chiến lược và kế hoạch quản lý rủi ro tốt hơn.
- Ưu tiên rủi ro theo tác động/mức độ nghiêm trọng, dùng các phương pháp, công cụ và kỹ thuật đã thiết lập.
- Hiểu và phân tích rủi ro, báo cáo các sự kiện rủi ro đã xác định.
- Kiểm soát rủi ro và giảm nhẹ tác động.
- Tạo nhận thức trong đội ngũ bảo mật và phát triển chiến lược, kế hoạch quản lý rủi ro lâu dài.

### Các giai đoạn của Risk Management (Risk Management Phases)

Bốn bước chính (risk management phases):

| Giai đoạn | Mô tả |
|-----------|-------|
| **Risk Identification** | Nhận diện nguồn gốc, nguyên nhân, hậu quả và chi tiết khác của các rủi ro nội bộ và bên ngoài ảnh hưởng đến bảo mật của tổ chức |
| **Risk Assessment** | Đánh giá rủi ro của tổ chức và ước tính likelihood cùng impact của rủi ro |
| **Risk Treatment** | Lựa chọn và triển khai các controls phù hợp cho những rủi ro đã xác định |
| **Risk Tracking** | Đảm bảo các controls phù hợp được triển khai để xử lý rủi ro đã biết và tính toán khả năng xuất hiện rủi ro mới |
| **Risk Review** | Đánh giá hiệu quả của các chiến lược quản lý rủi ro đã triển khai |

#### Risk Identification

Bước khởi đầu của kế hoạch quản lý rủi ro. Mục tiêu chính là nhận diện rủi ro — bao gồm nguồn gốc, nguyên nhân và hậu quả của rủi ro nội bộ và bên ngoài ảnh hưởng đến bảo mật trước khi chúng gây hại. Quy trình phụ thuộc vào kỹ năng của con người và khác nhau giữa các tổ chức.

#### Risk Assessment

Đánh giá rủi ro và ước tính likelihood, impact. Là quá trình **lặp đi lặp lại liên tục**, gán mức ưu tiên cho việc giảm nhẹ rủi ro và kế hoạch triển khai, qua đó xác định giá trị **định lượng (quantitative)** và **định tính (qualitative)** của rủi ro. Tổ chức nên áp dụng quy trình đánh giá rủi ro để phát hiện, ưu tiên và loại bỏ rủi ro. Đánh giá rủi ro được thực hiện khi phát hiện mối nguy nhưng chưa thể kiểm soát ngay, và được kèm theo cập nhật định kỳ toàn bộ cơ sở thông tin.

#### Risk Treatment

Quá trình lựa chọn và triển khai các controls phù hợp cho rủi ro đã xác định nhằm điều chỉnh chúng. Quyết định ở giai đoạn này dựa trên kết quả của risk assessment, xác định thứ tự ưu tiên xử lý/giám sát/đánh giá rủi ro. Thông tin cần có trước khi xử lý rủi ro:

- Phương pháp xử lý phù hợp
- Người chịu trách nhiệm xử lý
- Chi phí liên quan
- Lợi ích của việc xử lý
- Khả năng thành công
- Cách đo lường và đánh giá việc xử lý

#### Risk Tracking and Review

Kế hoạch quản lý rủi ro hiệu quả cần cơ cấu **theo dõi (tracking)** và **rà soát (review)** để đảm bảo nhận diện, đánh giá rủi ro và sử dụng controls/ứng phó phù hợp. Quá trình tracking và review xác định các biện pháp và thủ tục đã áp dụng, đảm bảo việc đánh giá là phù hợp. Giai đoạn review đánh giá hiệu quả của các chiến lược quản lý rủi ro đã triển khai. Việc kiểm tra và rà soát định kỳ chính sách, tiêu chuẩn giúp phát hiện cơ hội cải tiến. Quá trình giám sát đảm bảo các controls phù hợp luôn sẵn sàng và mọi thủ tục được hiểu và tuân thủ.

---

## Cyber Threat Intelligence

Theo từ điển Oxford, một **threat** là "khả năng một nỗ lực ác ý nhằm làm hỏng hoặc gián đoạn một mạng hay hệ thống máy tính." Threat là sự xuất hiện tiềm tàng của một sự kiện không mong muốn, có thể làm hỏng và gián đoạn hoạt động của tổ chức, ảnh hưởng đến integrity và availability. Threat có thể vô tình, cố ý, hoặc do tác động của một hành động nào đó.

**Cyber Threat Intelligence (CTI)** là việc **thu thập và phân tích thông tin** về threats và adversaries (đối thủ), đồng thời vẽ ra các mẫu (patterns) để có thể ra quyết định hiểu biết phục vụ **preparedness** (sẵn sàng), **prevention** (phòng ngừa) và **response** (ứng phó) trước các cuộc tấn công mạng. Đây là quá trình nhận diện hoặc khám phá "unknown threats" (mối đe dọa chưa biết) để áp dụng cơ chế phòng thủ cần thiết.

CTI giúp tổ chức **nhận diện và giảm thiểu các rủi ro kinh doanh** bằng cách chuyển hóa unknown threats thành known threats, hỗ trợ triển khai nhiều chiến lược phòng thủ chủ động và nâng cao. Mục tiêu chính của CTI là giúp tổ chức nhận thức về threats hiện hữu/mới nổi và chuẩn bị tư thế an ninh chủ động trước khi bị khai thác.

Quy trình threat intelligence có thể dùng để nhận diện các yếu tố rủi ro gây ra: malware attacks, SQL injection, web application attacks, data leaks, phishing, denial-of-service attacks và các tấn công khác.

### Types of Threat Intelligence (Các loại tình báo mối đe dọa)

Từ góc độ tiêu thụ (consumption), threat intelligence được chia thành **bốn loại**: strategic, tactical, operational và technical. Bốn loại này khác nhau về thu thập dữ liệu, phân tích và đối tượng tiêu thụ.

```
                 Long-term Use          Short-term/Immediate Use
              ┌────────────────┐        ┌────────────────────┐
  High-Level  │   Strategic    │        │   Operational      │
              │ (Executives,   │        │ (Security Managers,│
              │  Management)   │        │  Network Defenders)│
              ├────────────────┤        ├────────────────────┤
  Low-Level   │   Tactical     │        │   Technical        │
              │ (IT Service &  │        │ (SOC Staff &       │
              │  SOC Managers, │        │  IR Teams)         │
              │  Administrators)│       │                    │
              └────────────────┘        └────────────────────┘
```

#### Strategic Threat Intelligence

Cung cấp thông tin **mức cao (high-level)** về tư thế an ninh mạng, threats, tác động tài chính của các hoạt động mạng, attack trends và tác động đến quyết định kinh doanh cấp cao.

- **Tiêu thụ bởi:** lãnh đạo cấp cao và ban quản lý (IT management, CISO).
- Cung cấp góc nhìn dựa trên rủi ro (risk-based view), tập trung vào khái niệm cấp cao về rủi ro và xác suất; xử lý vấn đề dài hạn và cảnh báo thời gian thực về threats tới tài sản trọng yếu.
- Thường ở dạng báo cáo (report), thu thập từ **OSINT, CTI vendors, ISAOs và ISACs**, đòi hỏi chuyên gia trình độ cao.

Thông tin thường gồm:

- Tác động tài chính của hoạt động mạng
- Attribution (quy trách nhiệm) cho các vụ xâm nhập và rò rỉ dữ liệu
- Threat actors và attack trends
- Bối cảnh đe dọa (threat landscape) cho các ngành khác nhau
- Thông tin thống kê về data breaches, data theft và malware
- Xung đột địa chính trị liên quan đến các cuộc tấn công mạng
- Thông tin về cách TTPs của adversary thay đổi theo thời gian
- Các ngành có thể bị ảnh hưởng do quyết định kinh doanh cấp cao

#### Tactical Threat Intelligence

Đóng vai trò chính trong bảo vệ tài nguyên tổ chức. Cung cấp thông tin về **TTPs** (Tactics, Techniques, Procedures) mà threat actors sử dụng để tấn công.

- **Tiêu thụ bởi:** chuyên gia an ninh mạng như IT service managers, security operations managers, nhân viên NOC, administrators, architects.
- Giúp hiểu cách adversary tấn công, nhận diện rò rỉ thông tin và đánh giá năng lực kỹ thuật cùng mục tiêu của attacker theo attack vectors.
- Nguồn thu thập: campaign reports, malware, incident reports, attack group reports, human intelligence. Thường lấy từ white/technical papers, trao đổi với tổ chức khác hoặc mua từ bên thứ ba; gồm thông tin kỹ thuật cao dưới dạng forensic reports.
- Hỗ trợ vận hành hằng ngày, giúp analyst đánh giá các sự cố bảo mật và hướng dẫn lãnh đạo cấp cao ra quyết định chiến lược.

#### Operational Threat Intelligence

Cung cấp thông tin về **các threats cụ thể** nhằm vào tổ chức; cung cấp thông tin ngữ cảnh về các sự kiện và sự cố bảo mật, giúp hé lộ rủi ro tiềm tàng, hiểu sâu hơn về phương pháp của attacker và điều tra hoạt động độc hại hiệu quả hơn.

- **Tiêu thụ bởi:** security managers hoặc trưởng nhóm incident response, network defenders, security forensics và fraud detection teams.
- Giúp hiểu threat actors tiềm năng, ý định, năng lực và cơ hội tấn công, cùng tác động của một cuộc tấn công thành công.
- Nhiều khi chỉ tổ chức chính phủ mới thu thập được loại này; giúp đội IR và forensic triển khai tài sản bảo mật để nhận diện/dừng tấn công sắp xảy ra, cải thiện khả năng phát hiện sớm và giảm thiệt hại.
- Nguồn: con người, mạng xã hội, chat rooms, hoạt động và sự kiện thực tế dẫn đến tấn công mạng; thu thập qua phân tích hành vi con người, threat groups. Thường ở dạng report gồm hoạt động độc hại đã xác định, khuyến nghị hành động và cảnh báo về tấn công mới nổi.

#### Technical Threat Intelligence

Cung cấp thông tin về **tài nguyên mà attacker sử dụng** để thực hiện tấn công; gồm command and control channels, tools và các mục khác. Có vòng đời ngắn hơn tactical threat intelligence và tập trung vào một **IoC (Indicator of Compromise)** cụ thể, cho phép phân phối và ứng phó nhanh.

- Ví dụ: một mẫu malware dùng để tấn công là *tactical*, còn chi tiết về cách triển khai cụ thể của malware đó là *technical*. Các ví dụ khác: IP address và domain cụ thể của endpoint độc hại, phishing email headers, hash checksum của malware.
- **Tiêu thụ bởi:** SOC staff và IR teams.
- Các indicators được thu thập từ chiến dịch đang hoạt động, tấn công vào tổ chức khác hoặc data feeds từ bên thứ ba; giúp chuyên gia bổ sung indicators vào hệ thống phòng thủ như IDS/IPS, firewall, endpoint security để nâng cao khả năng phát hiện sớm. Thông tin được nạp trực tiếp vào thiết bị bảo mật dưới dạng số để chặn/nhận diện traffic độc hại vào-ra.

---

## Threat Modeling

**Threat modeling** (mô hình hóa mối đe dọa) là **phương pháp đánh giá rủi ro (risk assessment approach)** để phân tích an ninh của một ứng dụng bằng cách thu thập, tổ chức và phân tích mọi thông tin ảnh hưởng đến an ninh của ứng dụng.

Mô hình threat gồm ba khối chính:
1. Hiểu góc nhìn của adversary (kẻ tấn công)
2. Đặc tả an ninh của hệ thống
3. Xác định threats

Mọi ứng dụng nên có threat model được phát triển và lập tài liệu, cần xem lại khi ứng dụng tiến hóa.

Threat modeling giúp:

- Nhận diện threats liên quan đến một kịch bản ứng dụng cụ thể
- Nhận diện vulnerabilities chính trong thiết kế ứng dụng
- Cải thiện thiết kế an ninh

Lưu ý khi áp dụng: không cứng nhắc về các bước cụ thể (nếu bế tắc, chuyển ngay sang bước 4); dùng scenarios để xác định phạm vi; tận dụng tài liệu thiết kế hiện có (use cases, architectural diagrams, data flow diagrams); bắt đầu với whiteboard; dùng phương pháp lặp; lấy input về ràng buộc host và network từ system/network administrators.

### Threat Modeling Process (Quy trình 5 bước)

| # | Bước | Mô tả |
|---|------|-------|
| 01 | **Identify Security Objectives** | Giúp xác định cần đầu tư bao nhiêu công sức cho các bước tiếp theo |
| 02 | **Application Overview** | Nhận diện components, data flows và trust boundaries |
| 03 | **Decompose the Application** | Giúp tìm ra các threats liên quan và chi tiết hơn |
| 04 | **Identify Threats** | Nhận diện threats liên quan tới kịch bản/ngữ cảnh control, dùng thông tin từ bước 2 và 3 |
| 05 | **Identify Vulnerabilities** | Nhận diện điểm yếu liên quan tới threats đã tìm, dùng vulnerability categories |

#### 1. Identify Security Objectives

Security objectives là các mục tiêu và ràng buộc liên quan đến confidentiality, integrity và availability của ứng dụng. Quản trị viên nên đặt câu hỏi:

- Dữ liệu nào cần được bảo vệ?
- Có yêu cầu compliance (tuân thủ) nào không?
- Có yêu cầu quality-of-service cụ thể nào không?
- Có tài sản vô hình (intangible assets) nào cần bảo vệ không?

#### 2. Application Overview

Nhận diện components, data flows và trust boundaries. Vẽ kịch bản triển khai end-to-end bằng whiteboard. Deployment diagram nên gồm:

- End-to-end deployment topology
- Logical layers
- Key components
- Key services
- Communication ports and protocols
- Identities
- External dependencies

**Identify Roles:** xác định người dùng cùng vai trò và hành động họ có thể thực hiện (ai đọc / cập nhật / xóa dữ liệu, có nhóm đặc quyền cao hơn không).

**Identify Key Usage Scenarios:** dùng use cases để xác định mục tiêu — use cases mô tả cách ứng dụng được dùng và bị lạm dụng.

**Identify Technologies:** liệt kê công nghệ và tính năng chính:

- Operating systems
- Web server software
- Database server software
- Công nghệ cho presentation, business và data access layers
- Development languages

Việc này giúp tập trung vào các threats đặc thù theo công nghệ.

**Identify Application Security Mechanisms:** xác định các điểm chính về:

- Input and data validation
- Authorization and authentication
- Sensitive data
- Configuration management
- Session management
- Parameter manipulation
- Cryptography
- Exception management
- Auditing and logging

#### 3. Decompose the Application

Phân rã ứng dụng để nhận diện trust boundaries, data flows, entry points và exit points, giúp dễ tìm threats và vulnerabilities chi tiết hơn.

**Identify Trust Boundaries:** chỉ ra nơi trust levels thay đổi.
- Xác định outer system boundaries
- Xác định access control points / nơi cần thêm đặc quyền hoặc role membership
- Xác định trust boundaries từ góc độ data flow

**Identify Data Flows:** liệt kê luồng dữ liệu vào-ra của ứng dụng. Chú ý đặc biệt đến data flow qua trust boundaries và việc data validation tại điểm vào của trust boundary. Bắt đầu từ mức cao nhất rồi phân rã theo subsystem.

**Identify Entry Points:** entry point của ứng dụng cũng có thể là entry point cho tấn công. Tập trung vào các entry point cho phép truy cập chức năng trọng yếu để phòng thủ phù hợp.

**Identify Exit Points:** các điểm ứng dụng chuyển dữ liệu tới client hoặc hệ thống bên ngoài. Ưu tiên exit point ghi dữ liệu chứa input của client hoặc dữ liệu từ nguồn không tin cậy (ví dụ shared database).

#### 4. Identify Threats

Nhận diện threats liên quan tới kịch bản/ngữ cảnh control dùng thông tin từ bước application overview và decompose. Tập hợp thành viên đội development và test để nhận diện threats tiềm tàng; bắt đầu từ danh sách threats phổ biến nhóm theo application vulnerability category. Bước này dùng cách tiếp cận theo câu hỏi (question-driven).

#### 5. Identify Vulnerabilities

**Vulnerability** là điểm yếu trong ứng dụng (triển khai trong hệ thống thông tin) cho phép attacker khai thác, dẫn đến vi phạm an ninh. Quản trị viên bảo mật nên nhận diện mọi điểm yếu liên quan tới threats đã tìm, dùng vulnerability categories, và khắc phục trước để ngăn kẻ xâm nhập.

---

## Incident Management

**Incident management** (quản lý sự cố) là tập hợp các quy trình được định nghĩa để **identify, analyze, prioritize và resolve** các sự cố bảo mật, nhằm khôi phục hệ thống về hoạt động bình thường nhanh nhất có thể và **ngăn tái diễn** sự cố. Nó không chỉ ứng phó sự cố mà còn kích hoạt alerts để ngăn rủi ro và threats tiềm tàng.

Incident management bao gồm:

- Vulnerability analysis
- Artifact analysis
- Security awareness training
- Intrusion detection
- Public hoặc technology monitoring

Quy trình incident management được thiết kế để:

- Cải thiện chất lượng dịch vụ
- Giải quyết vấn đề một cách chủ động
- Giảm tác động của sự cố lên tổ chức/hoạt động kinh doanh
- Đáp ứng yêu cầu về availability dịch vụ
- Tăng hiệu suất và năng suất nhân sự
- Cải thiện sự hài lòng của người dùng và khách hàng
- Hỗ trợ xử lý sự cố trong tương lai

Tổ chức các buổi đào tạo để lan tỏa nhận thức (awareness) là phần quan trọng — giúp người dùng cuối nhận diện sự kiện/sự cố đáng ngờ và báo cáo hành vi của attacker cho cơ quan có thẩm quyền.

**Những người thực hiện hoạt động incident management:**

- **Human resources:** xử lý việc sa thải nhân viên bị nghi thực hiện hoạt động máy tính có hại.
- **Legal counsel:** đặt ra quy tắc/quy định trong tổ chức, ảnh hưởng tới chính sách và thực hành bảo mật nội bộ khi insider/attacker dùng hệ thống cho hoạt động độc hại.
- **Firewall manager:** duy trì các filter — nơi thường xảy ra denial-of-service attacks.
- **Outsourced service provider:** sửa chữa hệ thống bị nhiễm virus và malware.

**Incident response** là một chức năng trong **incident handling**; incident handling lại là một trong các dịch vụ thuộc **incident management**. Quan hệ này được minh họa như sau:

```
┌──────────────────────────── Incident Management ────────────────────────────┐
│                                                                              │
│  ┌────────────────────┐     ┌──────────── Incident Handling ─────────────┐   │
│  │ Vulnerability       │     │  ┌──────────┐   ┌────────────────────────┐ │   │
│  │ Handling            │     │  │ Triage    │   │ Reporting and Detection│ │   │
│  ├────────────────────┤     │  ├──────────┤   ├────────────────────────┤ │   │
│  │ Artifact Handling   │     │  │ Incident  │   │ Analysis               │ │   │
│  ├────────────────────┤     │  │ Response  │   │                        │ │   │
│  │ Announcements       │     │  └──────────┘   └────────────────────────┘ │   │
│  ├────────────────────┤     └─────────────────────────────────────────────┘   │
│  │ Alerts              │     ┌─────────────────────────────────────────────┐   │
│  │                     │     │ Other Incident Management Services          │   │
│  └────────────────────┘     └─────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────────────────────────┘
```

*Hình 1.4 — Block Diagram of Incident Management (Module 01, trang 66)*

---

## Incident Handling and Response (IH&R)

**Incident handling and response (IH&R)** là quá trình thực hiện các bước **có tổ chức và cẩn trọng** khi phản ứng với một sự cố bảo mật hoặc tấn công mạng. Đó là tập hợp các thủ tục, hành động và biện pháp thực hiện trước một sự kiện bất ngờ; bao gồm logging, recording và resolving các sự cố, ghi nhận thời điểm xảy ra, tác động và nguyên nhân.

IH&R quản lý các quy trình ứng phó như preparation, detection, containment, eradication và recovery để vượt qua tác động của sự cố nhanh và hiệu quả, khôi phục hoạt động bình thường với tác động tối thiểu. Nó cũng gồm: định nghĩa user policies, xây dựng protocols, lập incident response teams, kiểm toán tài sản, lập kế hoạch ứng phó, xin phê duyệt của ban quản lý, báo cáo và ưu tiên sự cố, thiết lập giao tiếp phù hợp giữa những người ứng phó.

### Các bước trong quy trình IH&R

```
1  Preparation                              7  Eradication
2  Incident Recording and Assignment        8  Recovery
3  Incident Triage                          9  Post-Incident Activities
4  Notification                                • Incident Documentation
5  Containment                                 • Incident Impact Assessment
6  Evidence Gathering and Forensic Analysis    • Review and Revise Policies
                                               • Close the Investigation
                                               • Incident Disclosure
```

**Step 1: Preparation** — kiểm toán tài nguyên và tài sản để xác định mục đích bảo mật; định nghĩa rules, policies, procedures dẫn dắt IH&R; xây dựng và đào tạo incident response team, định nghĩa thủ tục sẵn sàng và thu thập công cụ, đào tạo nhân viên bảo vệ hệ thống và tài khoản.

**Step 2: Incident Recording and Assignment** — báo cáo và ghi nhận ban đầu về sự cố; xác định incident và lập kế hoạch giao tiếp; thông báo cho nhân viên IT support hoặc gửi ticket phù hợp.

**Step 3: Incident Triage** — phân tích, xác thực, phân loại và ưu tiên các sự cố; phân tích thiết bị bị xâm nhập để tìm chi tiết: loại tấn công, mức độ nghiêm trọng, mục tiêu, tác động, phương thức lan truyền và lỗ hổng bị khai thác.

**Step 4: Notification** — đội IH&R thông báo cho các stakeholders gồm management, third-party vendors và clients về sự cố.

**Step 5: Containment** — ngăn lây lan sang các tài sản khác của tổ chức, ngăn thiệt hại bổ sung.

**Step 6: Evidence Gathering and Forensic Analysis** — thu thập mọi bằng chứng liên quan và gửi cho bộ phận forensic điều tra; phân tích forensic hé lộ phương thức tấn công, lỗ hổng bị khai thác, cơ chế bảo mật bị vượt qua, thiết bị mạng bị nhiễm và ứng dụng bị xâm nhập.

**Step 7: Eradication** — loại bỏ root cause của sự cố và đóng mọi attack vectors để ngăn sự cố tương tự trong tương lai.

**Step 8: Recovery** — sau khi loại bỏ nguyên nhân, khôi phục các hệ thống, dịch vụ, tài nguyên và dữ liệu bị ảnh hưởng; đảm bảo sự cố không gây gián đoạn dịch vụ/kinh doanh.

**Step 9: Post-Incident Activities** — rà soát và phân tích bổ sung trước khi đóng sự cố:

- Incident documentation
- Incident impact assessment
- Reviewing and revising policies
- Closing the investigation
- Incident disclosure

---

## Role of AI and ML in Cyber Security

**Machine Learning (ML)** và **Artificial Intelligence (AI)** ngày nay được dùng rộng rãi trong nhiều ngành nhờ sự gia tăng về **computing power, data collection và storage capabilities**.

Cùng với tiến bộ công nghệ (self-driving cars, language translators, big data) là sự gia tăng threats như ransomware, botnets, malware và phishing. Dùng AI và ML trong an ninh mạng giúp **nhận diện exploits và điểm yếu mới**, dễ dàng phân tích để giảm thiểu các tấn công tiếp theo, giảm áp lực cho chuyên gia bảo mật và cảnh báo khi cần hành động.

### What are AI and ML?

- **AI** là giải pháp duy nhất để phòng thủ mạng trước các tấn công mà antivirus scan không phát hiện được. Lượng lớn dữ liệu thu thập được nạp vào AI để xử lý và phân tích chi tiết, xu hướng.
- **ML** là một nhánh của AI, cho hệ thống khả năng **tự học (self-learn)** mà không cần chương trình tường minh. Hệ thống tự học này dùng để định nghĩa mạng bình thường (cùng các thiết bị) trông như thế nào, rồi truy ngược và báo cáo mọi sai lệch hay bất thường (anomalies) theo thời gian thực.

### ML Classification Techniques (Hai loại)

```
                    Machine Learning
                   /                \
        Unsupervised Learning     Supervised Learning
         /            \              /          \
  Dimensionality    Clustering   Classification  Regression
   Reduction
```

- **Supervised Learning:** dùng thuật toán nhập **labeled training data** (dữ liệu đã gán nhãn) để học sự khác biệt giữa các nhãn. Chia thành hai loại:
  - **Classification:** xử lý các lớp được phân tách hoàn toàn; nhiệm vụ chính là xác định lớp của test sample.
  - **Regression:** dùng khi các lớp dữ liệu không được phân tách, ví dụ dữ liệu liên tục (continuous).
- **Unsupervised Learning:** dùng thuật toán nhập **unlabeled training data** (dữ liệu không gán nhãn) để tự suy ra mọi danh mục mà không cần hướng dẫn. Chia thành:
  - **Clustering:** chia dữ liệu thành các cụm dựa trên độ tương đồng, bất kể thông tin lớp.
  - **Dimensionality Reduction:** giảm số chiều (attributes) của dữ liệu.

### Why AI and ML?

> Nguồn: https://www.gartner.com, https://www.marketsandmarkets.com

Bối cảnh threat tiếp tục tiến hóa không chỉ về quy mô mà còn về độ tinh vi (sophistication). Khi doanh nghiệp mở rộng dấu chân số (digital footprint), năng lực "identify và diagnose" không còn đủ để xử lý thách thức ngày càng lớn này. Phát triển advanced security analytics là cân nhắc quan trọng cho tổ chức muốn triển khai ML để phòng thủ trước các threats nội bộ và bên ngoài.

Thị trường an ninh mạng dự kiến vượt **$300 tỷ vào năm 2024**, và thị trường an ninh mạng liên quan đến AI dự đoán đạt giá trị **$38.2 tỷ vào năm 2026**.

```
AI in Cyber Security Market, by Region (USD Billion)
(North America | Asia Pacific | Europe | RoW)

                                                    ▇ 38.2
                                              ▇
                                        ▇
                                  ▇
                            ▇
                      ▇
         ▇      8.8 ▇
   ▇   ▇
  2018 2019 2020 2021 2022 2023 2024 2025 2026-p
```

*Hình 1.5 — AI in Cyber Security Market (Module 01, trang 71)*

### AI and ML Application Areas

> Nguồn: https://www.cbinsights.com

Theo CB Insights, cùng với hoạt động đầu tư gia tăng, nhiều công ty an ninh mạng đang nổi lên để cung cấp giải pháp mới cho các threats mạng bằng cách tận dụng AI. Theo AI Deals Tracker của CB Insights, an ninh mạng là ngành **đứng thứ tư** về số thương vụ cho các công ty ứng dụng AI; có hơn **80 công ty tư nhân** trong an ninh mạng dùng AI, được phân vào **chín lĩnh vực chính**:

| | |
|---|---|
| Anti-fraud and identity management | Cyber-risk management |
| Mobile security | App security |
| Predictive intelligence | IoT security |
| Behavioral analytics and anomaly detection | Deception security |
| Automated security | |

*Hình 1.6 — Companies using Artificial Intelligence (Module 01, trang 72): "Cybersecurity's Next Step Market Map: 80+ companies securing the future with artificial intelligence" (CB Insights)*

---

## How Do AI and ML Prevent Cyber Attacks?

AI (và cùng với nó là ML) là công nghệ mới nổi trong an ninh mạng, được áp dụng rộng rãi bởi các ngành quy mô lớn như automation, IT services, manufacturing, production và finance. AI đóng vai trò then chốt trong phát hiện threats sắp xảy ra bằng cách tích hợp ML như một tập con.

Mười cách AI và ML bảo vệ các ngành khỏi tấn công an ninh mạng:

| # | Cách | # | Cách |
|---|------|---|------|
| 1 | Password Protection and Authentication | 6 | Network Security |
| 2 | Phishing Detection and Prevention | 7 | AI-based Antivirus |
| 3 | Threat Detection | 8 | Fraud Detection |
| 4 | Vulnerability Management | 9 | Botnet Detection |
| 5 | Behavioral Analytics | 10 | AI to Combat AI Threats |

**1. Password Protection and Authentication** — credentials đóng vai trò quan trọng ngăn truy cập bất hợp pháp. Lập trình viên dùng AI để cải thiện biometric validation và face recognition, cung cấp các mô hình nhận diện khuôn mặt bằng cách theo dõi correlations và patterns chính.

**2. Phishing Detection and Prevention** — phishing là phương thức phổ biến gửi payload qua email. AI và ML nhận diện và ngăn phishing nhanh hơn con người, phân biệt nhanh website độc hại với website hợp lệ.

**3. Threat Detection** — ML giúp phát hiện tấn công trước khi hệ thống bị xâm nhập, liên tục thông báo cho admin về threats sắp xảy ra qua phân tích dữ liệu logic và deep learning.

**4. Vulnerability Management** — hệ thống AI/ML không để vulnerability tồn tại lâu; quét động mọi loại lỗ hổng và cảnh báo admin trước khi bị khai thác, cung cấp thông tin attacker và dự báo khi nào việc khai thác có thể xảy ra.

**5. Behavioral Analytics** — AI cùng ML tạo các pattern người dùng cụ thể dựa trên sử dụng thường nhật; cảnh báo admin tức thì nếu phát hiện hoạt động đáng ngờ hoặc sai lệch (ví dụ attacker đã trộm credentials).

**6. Network Security** — hai yếu tố quan trọng là tạo security policies toàn diện và lập bản đồ network topology của doanh nghiệp; cả hai đều tốn thời gian. AI tăng cường: thực hiện network traffic analysis và đề xuất security policies hiệu quả mặc định.

**7. AI-based Antivirus** — antivirus truyền thống quét file để khớp signatures của virus/malware đã biết; việc cập nhật tốn thời gian. AI-based antivirus dùng anomaly detection để hiểu hành vi chương trình, phát hiện hành vi đáng ngờ thay vì khớp signatures.

**8. Fraud Detection** — AI và ML thực hiện anomaly detection để nhận diện giao dịch gian lận và bất nhất thanh toán, tự động khám phá pattern, dễ dàng phân biệt giao dịch hợp lệ và bất hợp pháp, chặn giao dịch gian lận.

**9. Botnet Detection** — botnet có thể vượt qua IDS (Intrusion/Instruction Detection System) do IDS kém hiệu quả trong khớp signatures; botnet được nhúng bằng code tinh vi khó truy vết. Chuyên gia dùng AI/ML để cảnh báo về hành vi đáng ngờ của mạng và phát hiện xâm nhập trái phép.

**10. AI to Combat AI Threats** — attacker cũng có thể tận dụng AI để xâm nhập mạng; các threats này phải được phát hiện ngay. Phần mềm AI có thể phát hiện các tấn công AI-augmented trước khi mạng bị xâm nhập.
