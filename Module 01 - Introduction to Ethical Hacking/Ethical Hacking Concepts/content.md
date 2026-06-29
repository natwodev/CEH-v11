# Ethical Hacking Concepts

> Module 01 | Trang 38–46

## Giới thiệu

Một **ethical hacker** (hacker có đạo đức) thực hiện các quy trình tương tự như hacker độc hại. Các bước để **giành** (gain) và **duy trì** (maintain) quyền truy cập vào một hệ thống máy tính là giống nhau, bất kể ý định của hacker là gì.

Phần này cung cấp tổng quan về:

- Ethical hacking là gì
- Tại sao ethical hacking là cần thiết
- Phạm vi (scope) và giới hạn (limitations) của ethical hacking
- Kỹ năng của một ethical hacker

---

## What is Ethical Hacking?

**Ethical hacking** là việc sử dụng kỹ năng máy tính và mạng để **hỗ trợ tổ chức kiểm thử** an ninh mạng của họ nhằm tìm ra các lỗ hổng (loopholes, vulnerabilities).

Ba đặc điểm cốt lõi:

- Sử dụng **công cụ, thủ thuật và kỹ thuật hacking** để xác định lỗ hổng và đảm bảo an ninh hệ thống.
- Tập trung vào việc **mô phỏng (simulate) kỹ thuật của kẻ tấn công** để xác minh sự tồn tại của các lỗ hổng có thể khai thác (exploitable vulnerabilities) trong an ninh hệ thống.
- Ethical hacker thực hiện đánh giá an ninh (security assessment) cho tổ chức **với sự cho phép (permission) của bên có thẩm quyền liên quan**.

### White Hats

**White Hats** (còn gọi là security analysts hoặc ethical hackers) là các cá nhân/chuyên gia thực hiện ethical hacking. Ngày nay, hầu hết tổ chức (công ty tư nhân, trường đại học, cơ quan chính phủ) thuê White Hats để nâng cao an ninh mạng (cybersecurity). Họ hack theo cách hợp pháp — **có sự cho phép** của chủ sở hữu hệ thống/mạng và **không có ý định gây hại**. Ethical hacker báo cáo mọi lỗ hổng cho chủ sở hữu để khắc phục (remediation).

### Tranh luận về thuật ngữ "hacking"

Ngày nay thuật ngữ *hacking* gắn liền với các hoạt động bất hợp pháp và phi đạo đức, vì truy cập trái phép vào hệ thống là một tội phạm. Cần phân biệt các định nghĩa:

| Thuật ngữ | Ý nghĩa |
|-----------|---------|
| **Hacker** (danh từ) | Người thích tìm hiểu chi tiết hệ thống máy tính và mở rộng khả năng của chúng |
| **To hack** (động từ) | Phát triển nhanh chương trình mới hoặc reverse engineering phần mềm hiện có để cải thiện theo cách sáng tạo, hiệu quả hơn |
| **Cracker / Attacker** | Người dùng kỹ năng hacking cho mục đích tấn công (offensive) |
| **Ethical hacker** | Chuyên gia an ninh dùng kỹ năng hacking cho mục đích phòng thủ (defensive) |

Hầu hết công ty thuê chuyên viên IT để audit hệ thống tìm các lỗ hổng đã biết. Tuy hữu ích, nhưng cracker thường quan tâm tới các lỗ hổng mới, ít được biết đến — nên việc audit "theo sách vở" (by-the-numbers) là chưa đủ. Tổ chức cần người có thể **suy nghĩ như một cracker**, cập nhật các lỗ hổng và exploit mới nhất, và nhận ra lỗ hổng tiềm ẩn mà người khác không thấy. Đó là vai trò của ethical hacker.

Ethical hacker dùng cùng công cụ và kỹ thuật như hacker, với khác biệt quan trọng là **họ không phá hoại hệ thống**. Họ đánh giá an ninh, thông báo cho quản trị viên về lỗ hổng phát hiện, và đề xuất quy trình vá (patching).

> **Điểm phân biệt then chốt** giữa ethical hacker và cracker là **sự đồng thuận (consent)**. Cracker cố giành quyền truy cập trái phép; còn ethical hacker luôn hoàn toàn công khai, minh bạch về việc họ làm và cách họ làm. Do đó ethical hacking **luôn hợp pháp**.

---

## Why Ethical Hacking is Necessary

> **To beat a hacker, you need to think like one!** (Muốn đánh bại hacker, bạn phải tư duy như một hacker.)

Khi công nghệ phát triển nhanh, rủi ro đi kèm cũng tăng theo. Ethical hacking là cần thiết vì nó cho phép **phản công (counter attacks)** lại các hacker độc hại bằng cách dự đoán trước phương pháp họ dùng để xâm nhập hệ thống. Nó giúp dự báo sớm các lỗ hổng và khắc phục mà không phải chịu một cuộc tấn công từ bên ngoài.

Vì hacking liên quan đến tư duy sáng tạo, riêng việc kiểm thử lỗ hổng và security audit không đảm bảo mạng an toàn. Để đạt an ninh, tổ chức phải triển khai chiến lược **"defense-in-depth"** (phòng thủ theo chiều sâu) bằng cách tự thâm nhập (penetrating) mạng của mình để ước lượng và phơi bày lỗ hổng.

### Lý do tổ chức tuyển dụng ethical hacker

| | |
|---|---|
| Ngăn hacker truy cập hệ thống thông tin của tổ chức | Cung cấp biện pháp phòng ngừa đầy đủ để tránh security breach |
| Phát hiện lỗ hổng và đánh giá mức rủi ro của chúng | Giúp bảo vệ dữ liệu khách hàng |
| Phân tích và củng cố security posture (tư thế an ninh): chính sách, hạ tầng bảo vệ mạng, thực hành của người dùng cuối | Nâng cao nhận thức an ninh ở mọi cấp trong doanh nghiệp |

### Các câu hỏi ethical hacker cố gắng trả lời

Đánh giá của ethical hacker về an ninh hệ thống thông tin của khách hàng nhằm trả lời các câu hỏi cơ bản, gắn với các pha (phase) của một cuộc tấn công:

| # | Câu hỏi | Pha liên quan |
|---|---------|---------------|
| 1 | Kẻ xâm nhập có thể **thấy gì** trên hệ thống mục tiêu? | Reconnaissance & Scanning |
| 2 | Kẻ xâm nhập có thể **làm gì** với thông tin đó? | Gaining Access & Maintaining Access |
| 3 | Có ai ở tổ chức mục tiêu **nhận ra** nỗ lực/thành công của kẻ xâm nhập không? | Reconnaissance & Covering Tracks |
| 4 | Mọi thành phần của hệ thống thông tin đã được bảo vệ, cập nhật và vá đầy đủ chưa? | |
| 5 | Cần bao nhiêu thời gian, công sức và tiền bạc để đạt mức bảo vệ đầy đủ? | |
| 6 | Các biện pháp an ninh thông tin có tuân thủ chuẩn pháp lý và chuẩn ngành không? | |

**Diễn giải 3 câu hỏi nền tảng:**

1. **Kẻ tấn công thấy gì trên hệ thống mục tiêu?** — Kiểm tra an ninh thông thường của quản trị viên thường bỏ sót lỗ hổng. Ethical hacker phải suy nghĩ về những gì kẻ tấn công có thể thấy trong các pha reconnaissance và scanning.
2. **Kẻ xâm nhập làm được gì với thông tin đó?** — Ethical hacker phải hiểu ý đồ và mục đích đằng sau cuộc tấn công để xác định countermeasure phù hợp; trong các pha gaining-access và maintaining-access cần đi trước hacker một bước.
3. **Nỗ lực của kẻ tấn công có bị phát hiện không?** — Đôi khi kẻ tấn công thăm dò hệ thống trong nhiều ngày, tuần, thậm chí nhiều tháng. Trong các pha reconnaissance và covering tracks, ethical hacker nên phát hiện và chặn đứng cuộc tấn công.

Sau khi tấn công, hacker có thể xóa dấu vết bằng cách sửa file log và tạo backdoor, hoặc cài trojan. Ethical hacker phải điều tra xem các hoạt động đó có được ghi lại không và biện pháp phòng ngừa nào đã được áp dụng.

---

## Ethical Hacking Client Framework (Khung làm việc với khách hàng)

Toàn bộ quá trình ethical hacking và vá lỗ hổng phụ thuộc vào các câu hỏi như:

- Tổ chức đang cố bảo vệ **cái gì**?
- Họ đang bảo vệ **trước ai hoặc cái gì**?
- Mọi thành phần của hệ thống thông tin đã được bảo vệ, cập nhật và vá đầy đủ chưa?
- Khách hàng sẵn sàng đầu tư **bao nhiêu** thời gian, công sức và tiền bạc để đạt mức bảo vệ đầy đủ?
- Các biện pháp an ninh có tuân thủ chuẩn ngành và pháp lý không?

Đôi khi, để tiết kiệm tài nguyên hoặc tránh bị phát hiện thêm, khách hàng có thể quyết định **dừng đánh giá ngay sau khi tìm thấy lỗ hổng đầu tiên**. Do đó, điều quan trọng là ethical hacker và khách hàng **thống nhất trước một khung làm việc (framework)** phù hợp cho việc điều tra. Khách hàng cần được thuyết phục về tầm quan trọng của các bài tập an ninh này thông qua mô tả ngắn gọn về điều gì đang xảy ra và điều gì đang bị đe dọa.

> Ethical hacker cũng phải nhớ truyền đạt cho khách hàng rằng **không bao giờ có thể bảo vệ hệ thống một cách hoàn toàn**, nhưng luôn có thể cải thiện chúng.

---

## Scope and Limitations of Ethical Hacking

Chuyên gia an ninh phân loại tội phạm máy tính (computer crime) thành hai nhóm: tội phạm được **hỗ trợ bởi máy tính** và tội phạm trong đó **máy tính là mục tiêu**.

### Scope (Phạm vi)

- Ethical hacking là **đánh giá an ninh có cấu trúc và tổ chức**, thường là một phần của penetration test hoặc security audit.
- Là thành phần quan trọng của **risk assessment** (đánh giá rủi ro), **auditing** (kiểm toán), **counter fraud** (chống gian lận), và **best practices** về an ninh hệ thống thông tin.
- Dùng để **xác định rủi ro** và làm nổi bật **hành động khắc phục (remedial actions)**.
- Giúp **giảm chi phí ICT** (Information and Communications Technology) bằng cách giải quyết lỗ hổng.

Ethical hacker xác định phạm vi đánh giá theo mối quan tâm an ninh của khách hàng. Nhiều ethical hacker là thành viên của một **"Tiger Team"** — đội phối hợp thực hiện kiểm thử toàn diện, bao trùm mọi khía cạnh mạng cũng như xâm nhập vật lý (physical) và hệ thống.

### Limitations (Giới hạn)

- Trừ khi doanh nghiệp đã biết rõ họ đang tìm kiếm điều gì và **tại sao thuê bên ngoài (outside vendor)** để hack hệ thống, nếu không thì khó thu được nhiều giá trị từ trải nghiệm.
- Ethical hacker **chỉ có thể giúp** tổ chức hiểu rõ hơn hệ thống an ninh của mình; việc **đặt các biện pháp bảo vệ (safeguards) đúng đắn** lên mạng là trách nhiệm của tổ chức.

### Quy tắc đạo đức của ethical hacker

Ethical hacker phải biết các hình phạt của việc hack trái phép. **Không hoạt động ethical hacking nào** liên quan đến penetration test/security audit được bắt đầu **trước khi nhận được văn bản pháp lý có chữ ký** cho phép thực hiện. Họ phải:

- **Giành ủy quyền (authorization)** từ khách hàng và có **hợp đồng có chữ ký** cho phép tester thực hiện kiểm thử.
- **Giữ bảo mật (confidentiality)** khi thực hiện và tuân thủ **NDA** (Nondisclosure Agreement — thỏa thuận không tiết lộ) với khách hàng đối với thông tin mật được tiết lộ. Không được tiết lộ thông tin về bài kiểm thử hoặc dữ liệu mật của công ty cho bên thứ ba.
- **Thực hiện kiểm thử trong giới hạn đã thỏa thuận**, không vượt quá. Ví dụ, chỉ thực hiện tấn công DoS nếu đã thống nhất trước với khách hàng — vì mất doanh thu, uy tín (goodwill) và hậu quả tệ hơn có thể xảy ra khi server/ứng dụng không sẵn sàng với khách hàng do quá trình kiểm thử.

---

## Security Audit Framework (Khung kiểm toán an ninh)

Các bước sau cung cấp một khung để thực hiện security audit cho tổ chức, đảm bảo bài kiểm thử có tổ chức, hiệu quả và đúng đạo đức:

```
1. Talk to the client        → Trao đổi với khách hàng, thảo luận nhu cầu cần
                               giải quyết trong quá trình kiểm thử
2. Prepare & sign NDA        → Chuẩn bị và ký các văn bản NDA với khách hàng
3. Organize team & schedule  → Tổ chức đội ethical hacking và lập lịch kiểm thử
4. Conduct the test          → Tiến hành kiểm thử
5. Analyze & report          → Phân tích kết quả và chuẩn bị báo cáo
6. Present findings          → Trình bày kết quả báo cáo cho khách hàng
```

*Khung 6 bước thực hiện security audit (Module 01, trang 45)*

Tuy nhiên vẫn có giới hạn: trừ khi doanh nghiệp trước hết biết họ tìm gì và tại sao thuê bên ngoài hack hệ thống, nếu không sẽ khó thu được nhiều giá trị. Ethical hacker chỉ có thể giúp tổ chức hiểu rõ hơn hệ thống an ninh — việc đặt các safeguard đúng đắn lên mạng là trách nhiệm của tổ chức.

---

## Skills of an Ethical Hacker

Ethical hacker cần thu nạp kiến thức và kỹ năng để trở thành chuyên gia hacker và sử dụng kiến thức đó một cách hợp pháp. Kỹ năng chia thành hai nhóm:

### 1. Technical Skills (Kỹ năng kỹ thuật)

- Kiến thức **chuyên sâu về các môi trường hệ điều hành chính** như Windows, Unix, Linux và Macintosh.
- Kiến thức chuyên sâu về **networking** (mạng): khái niệm, công nghệ, phần cứng và phần mềm liên quan.
- Là **chuyên gia máy tính** thành thạo các lĩnh vực kỹ thuật.
- Am hiểu về **các lĩnh vực an ninh** (security areas) và các vấn đề liên quan.
- Kiến thức **kỹ thuật "cao"** (high technical) để khởi động các cuộc tấn công tinh vi (sophisticated attacks).

### 2. Non-Technical Skills (Kỹ năng phi kỹ thuật)

- **Khả năng học hỏi** và tiếp nhận công nghệ mới một cách nhanh chóng.
- **Đạo đức nghề nghiệp mạnh mẽ** (strong work ethic), kỹ năng giải quyết vấn đề và giao tiếp tốt.
- **Cam kết** với các chính sách an ninh của tổ chức.
- **Nhận thức** về các chuẩn mực và luật pháp địa phương (local standards and laws).
