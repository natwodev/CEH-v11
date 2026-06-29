# Information Security Laws and Standards

> Module 01 | Trang 76–91

## Giới thiệu

**Law** (luật) là hệ thống các quy tắc và hướng dẫn được một quốc gia hoặc cộng đồng cụ thể thực thi để điều chỉnh hành vi.

**Standard** (tiêu chuẩn) là "tài liệu được thiết lập bằng sự đồng thuận và được một cơ quan có thẩm quyền phê duyệt, cung cấp các quy tắc, hướng dẫn hoặc đặc tính cho hoạt động và kết quả của chúng, nhằm đạt được mức độ trật tự tối ưu trong một bối cảnh nhất định" — dùng chung và lặp lại nhiều lần.

Phần này trình bày các luật và tiêu chuẩn về an ninh thông tin ở nhiều quốc gia khác nhau:

- PCI DSS
- ISO/IEC 27001:2013
- HIPAA
- SOX (Sarbanes-Oxley Act)
- DMCA
- FISMA
- Cyber Law ở các quốc gia khác nhau

---

## Payment Card Industry Data Security Standard (PCI DSS)

> Nguồn: https://www.pcisecuritystandards.org

**PCI DSS** (Payment Card Industry Data Security Standard — tiêu chuẩn an ninh dữ liệu ngành thẻ thanh toán) là một **information security standard** (tiêu chuẩn an ninh thông tin) độc quyền, dành cho các tổ chức xử lý thông tin chủ thẻ (cardholder) đối với các loại thẻ ghi nợ (debit), tín dụng (credit), thẻ trả trước (prepaid), e-purse, ATM và POS.

Tiêu chuẩn này cung cấp một bộ tiêu chuẩn toàn diện cùng tài liệu hỗ trợ (framework gồm các đặc tả kỹ thuật, công cụ, phép đo và tài nguyên hỗ trợ) nhằm nâng cao an ninh dữ liệu thẻ thanh toán.

PCI DSS **áp dụng cho mọi thực thể tham gia xử lý thẻ thanh toán** — gồm merchant (đơn vị bán hàng), processor (đơn vị xử lý), acquirer (ngân hàng thanh toán), issuer (đơn vị phát hành) và service provider (nhà cung cấp dịch vụ), cũng như mọi thực thể lưu trữ, xử lý hoặc truyền tải dữ liệu chủ thẻ.

PCI DSS bao gồm một bộ yêu cầu **tối thiểu** để bảo vệ dữ liệu chủ thẻ. Bộ tiêu chuẩn này do **PCI Security Standards Council** xây dựng và duy trì.

| Mục tiêu (Objective) | Yêu cầu (Requirements) |
|---|---|
| **Build and Maintain a Secure Network** (xây dựng và duy trì mạng an toàn) | • Cài đặt và duy trì cấu hình firewall để bảo vệ dữ liệu chủ thẻ<br>• Không dùng giá trị mặc định của nhà cung cấp cho mật khẩu hệ thống và các tham số bảo mật khác |
| **Protect Cardholder Data** (bảo vệ dữ liệu chủ thẻ) | • Bảo vệ dữ liệu chủ thẻ được lưu trữ<br>• Mã hóa khi truyền dữ liệu chủ thẻ qua mạng công cộng, mở |
| **Maintain a Vulnerability Management Program** (duy trì chương trình quản lý lỗ hổng) | • Sử dụng và thường xuyên cập nhật phần mềm/chương trình diệt virus<br>• Phát triển và duy trì hệ thống và ứng dụng an toàn |
| **Implement Strong Access Control Measures** (triển khai biện pháp kiểm soát truy cập mạnh) | • Hạn chế truy cập dữ liệu chủ thẻ theo nhu cầu công việc (business need to know)<br>• Gán ID duy nhất cho mỗi người có quyền truy cập máy tính<br>• Hạn chế truy cập vật lý vào dữ liệu chủ thẻ |
| **Regularly Monitor and Test Networks** (giám sát và kiểm thử mạng thường xuyên) | • Theo dõi và giám sát mọi truy cập vào tài nguyên mạng và dữ liệu chủ thẻ<br>• Thường xuyên kiểm thử hệ thống và quy trình bảo mật |
| **Maintain an Information Security Policy** (duy trì chính sách an ninh thông tin) | • Duy trì chính sách an ninh thông tin áp dụng cho toàn bộ nhân sự |

*Bảng 1.3 — PCI Data Security Standard: High-Level Overview (Module 01, trang 78)*

> Việc không đáp ứng các yêu cầu PCI DSS có thể dẫn đến **phạt tiền (fines)** hoặc **chấm dứt đặc quyền xử lý thẻ thanh toán**.

---

## ISO/IEC 27001:2013

> Nguồn: https://www.iso.org

**ISO/IEC 27001:2013** quy định các yêu cầu để **thiết lập (establishing), triển khai (implementing), duy trì (maintaining) và liên tục cải tiến** một **information security management system (ISMS — hệ thống quản lý an ninh thông tin)** trong bối cảnh của tổ chức. Tiêu chuẩn này bao gồm các yêu cầu về đánh giá và xử lý rủi ro an ninh thông tin phù hợp với nhu cầu của tổ chức.

Tiêu chuẩn được thiết kế phù hợp cho nhiều mục đích sử dụng khác nhau:

1. Dùng trong tổ chức để xây dựng **security requirements** (yêu cầu bảo mật) và mục tiêu
2. Dùng trong tổ chức để đảm bảo rủi ro bảo mật được **quản lý một cách hiệu quả về chi phí (cost-effectively)**
3. Dùng trong tổ chức để đảm bảo **tuân thủ luật và quy định (compliance with laws and regulations)**
4. Định nghĩa các **information security management processes** (quy trình quản lý an ninh thông tin) mới
5. Xác định và làm rõ các quy trình quản lý an ninh thông tin hiện có
6. Dùng bởi ban quản lý tổ chức để xác định **trạng thái** của các hoạt động quản lý an ninh thông tin
7. Triển khai **business-enabling information security** (an ninh thông tin hỗ trợ kinh doanh)
8. Dùng để cung cấp thông tin liên quan về an ninh thông tin cho khách hàng

---

## Health Insurance Portability and Accountability Act (HIPAA)

> Nguồn: https://www.hhs.gov

**HIPAA Privacy Rule** cung cấp các biện pháp bảo vệ cấp liên bang cho thông tin sức khỏe cá nhân có thể nhận dạng (individually identifiable health information) do covered entity (thực thể được điều chỉnh) và business associate của họ nắm giữ, đồng thời trao cho bệnh nhân nhiều quyền đối với thông tin đó. Quy tắc này cũng cho phép tiết lộ thông tin sức khỏe cần thiết cho việc chăm sóc bệnh nhân và các mục đích cần thiết khác.

**HIPAA Security Rule** quy định một loạt các biện pháp bảo vệ hành chính (administrative), vật lý (physical) và kỹ thuật (technical) mà covered entity và business associate phải áp dụng để đảm bảo **confidentiality, integrity, và availability** của thông tin sức khỏe được bảo vệ dưới dạng điện tử.

Văn phòng Dân quyền (Office of Civil Rights) đã triển khai **HIPAA's Administrative Simplification Statute and Rules** (đạo luật và quy tắc đơn giản hóa hành chính của HIPAA), gồm:

### Electronic Transactions and Code Set Standards (chuẩn giao dịch điện tử và bộ mã)

Transaction (giao dịch) là trao đổi điện tử giữa hai bên cho các mục đích cụ thể. HIPAA 1996 chỉ định một số loại tổ chức là covered entity, bao gồm health plan (chương trình bảo hiểm y tế), health care clearinghouse và một số nhà cung cấp dịch vụ y tế. Secretary of Health and Human Services (HHS) đã áp dụng các giao dịch tiêu chuẩn cho **Electronic Data Interchange (EDI)** của dữ liệu y tế: claims (yêu cầu bồi thường) và encounter information, payment và remittance advice, claim status, eligibility, enrollment/disenrollment, referral và authorization, coordination of benefits, premium payment. Nếu covered entity thực hiện điện tử một trong các giao dịch đã được áp dụng, họ phải dùng chuẩn đã ban hành — từ ASC, X12N hoặc NCPDP (đối với một số giao dịch dược phẩm). Mọi nhà cung cấp giao dịch điện tử đều phải dùng chung health care transaction, code set và identifier.

### Privacy Rule (quy tắc về quyền riêng tư)

Thiết lập chuẩn quốc gia để bảo vệ hồ sơ y tế và thông tin sức khỏe cá nhân, áp dụng cho health plan, health care clearinghouse và nhà cung cấp dịch vụ y tế thực hiện một số giao dịch điện tử. Quy tắc yêu cầu các biện pháp bảo vệ phù hợp, đặt ra giới hạn và điều kiện về việc sử dụng và tiết lộ thông tin khi chưa có sự cho phép của bệnh nhân, đồng thời trao cho bệnh nhân quyền với thông tin sức khỏe của mình (gồm quyền xem, lấy bản sao hồ sơ và yêu cầu sửa chữa).

### Security Rule (quy tắc về an ninh)

Thiết lập chuẩn quốc gia để bảo vệ thông tin sức khỏe điện tử cá nhân do covered entity tạo, nhận, sử dụng hoặc duy trì. Yêu cầu áp dụng các biện pháp bảo vệ hành chính, vật lý và kỹ thuật phù hợp để đảm bảo confidentiality, integrity và security của thông tin.

### Employer Identifier Standard (chuẩn mã định danh người sử dụng lao động)

HIPAA yêu cầu mỗi employer (người sử dụng lao động) phải có một số định danh quốc gia tiêu chuẩn để nhận dạng trên các giao dịch tiêu chuẩn.

### National Provider Identifier Standard (NPI)

**NPI** là một HIPAA Administrative Simplification Standard — số định danh duy nhất gán cho nhà cung cấp dịch vụ y tế. Nhà cung cấp, health plan và health care clearinghouse phải dùng NPI trong các giao dịch hành chính và tài chính theo HIPAA. NPI là mã số 10 chữ số (10-digit), "intelligence-free" — tức là con số không mang thông tin khác về nhà cung cấp (như bang cư trú hay chuyên khoa y tế).

### Enforcement Rule (quy tắc thực thi)

Chứa các điều khoản liên quan đến việc tuân thủ và điều tra, cũng như việc áp đặt các khoản phạt tiền dân sự (civil monetary penalties) đối với vi phạm các quy tắc HIPAA Administrative Simplification và quy trình tổ chức điều trần (hearings).

---

## Sarbanes-Oxley Act (SOX)

> Nguồn: https://www.sec.gov

Được ban hành năm **2002**, **Sarbanes-Oxley Act (SOX)** nhằm **bảo vệ công chúng và nhà đầu tư (protect the public and investors)** bằng cách tăng độ chính xác và độ tin cậy của các công bố thông tin doanh nghiệp (corporate disclosures). Đạo luật không giải thích tổ chức phải lưu trữ hồ sơ như thế nào, mà mô tả những hồ sơ tổ chức phải lưu và thời gian lưu trữ. SOX yêu cầu nhiều cải cách để nâng cao trách nhiệm doanh nghiệp (corporate responsibility), tăng cường công bố tài chính và chống gian lận kế toán/doanh nghiệp.

Các yêu cầu và điều khoản chính của SOX được tổ chức thành **11 titles** (chương):

| Title | Tên | Nội dung |
|---|---|---|
| **I** | Public Company Accounting Oversight Board (PCAOB) | Gồm 9 mục; thiết lập PCAOB để giám sát độc lập các công ty kế toán đại chúng cung cấp dịch vụ kiểm toán ("auditors"); tạo ban giám sát trung tâm lo việc đăng ký, định nghĩa quy trình kiểm toán tuân thủ, kiểm tra và giám sát hành vi/chất lượng, thực thi tuân thủ SOX |
| **II** | Auditor Independence (tính độc lập của kiểm toán viên) | Gồm 9 mục; thiết lập chuẩn về tính độc lập của kiểm toán viên bên ngoài để hạn chế xung đột lợi ích; đề cập phê duyệt kiểm toán viên mới, luân chuyển audit partner, yêu cầu báo cáo; hạn chế công ty kiểm toán cung cấp dịch vụ phi kiểm toán (như tư vấn) cho cùng khách hàng |
| **III** | Corporate Responsibility (trách nhiệm doanh nghiệp) | Gồm 8 mục; yêu cầu lãnh đạo cấp cao chịu trách nhiệm cá nhân về độ chính xác và đầy đủ của báo cáo tài chính; định nghĩa tương tác giữa kiểm toán viên bên ngoài và ủy ban kiểm toán; nêu giới hạn hành vi của cán bộ và mức phạt dân sự khi không tuân thủ |
| **IV** | Enhanced Financial Disclosures (tăng cường công bố tài chính) | Gồm 9 mục; mô tả yêu cầu báo cáo nâng cao cho giao dịch tài chính, gồm giao dịch ngoài bảng cân đối (off-balance-sheet), số liệu pro-forma và giao dịch cổ phiếu của cán bộ; yêu cầu kiểm soát nội bộ, kiểm toán và báo cáo về các kiểm soát đó; báo cáo kịp thời thay đổi trọng yếu |
| **V** | Analyst Conflicts of Interest (xung đột lợi ích của chuyên viên phân tích) | Gồm 1 mục; bàn về các biện pháp khôi phục niềm tin nhà đầu tư vào báo cáo của securities analyst; định nghĩa quy tắc ứng xử và yêu cầu công bố mọi xung đột lợi ích đã biết |
| **VI** | Commission Resources and Authority (nguồn lực và thẩm quyền của Ủy ban) | Gồm 4 mục; định nghĩa thực hành khôi phục niềm tin nhà đầu tư vào securities analyst; định nghĩa thẩm quyền của SEC trong việc khiển trách hoặc cấm hành nghề; điều kiện cấm một người hành nghề môi giới, cố vấn hoặc đại lý |
| **VII** | Studies and Reports (nghiên cứu và báo cáo) | Gồm 5 mục; yêu cầu Comptroller General và SEC thực hiện các nghiên cứu và báo cáo kết quả, gồm tác động của việc hợp nhất công ty kế toán, vai trò của cơ quan xếp hạng tín nhiệm, vi phạm chứng khoán và hành động thực thi, và việc liệu ngân hàng đầu tư có hỗ trợ Enron, Global Crossing... thao túng lợi nhuận và che giấu tình hình tài chính thực |
| **VIII** | Corporate and Criminal Fraud Accountability (trách nhiệm gian lận doanh nghiệp và hình sự) | Còn gọi là "Corporate and Criminal Fraud Accountability Act of 2002"; gồm 7 mục; mô tả các hình phạt hình sự cụ thể cho việc thao túng, phá hủy hoặc thay đổi hồ sơ tài chính hoặc cản trở điều tra; cung cấp bảo vệ cho người tố giác (whistle-blower) |
| **IX** | White-Collar-Crime Penalty Enhancement (tăng nặng hình phạt tội phạm cổ cồn trắng) | Còn gọi là "White Collar Crime Penalty Enhancement Act of 2002"; gồm 6 mục; tăng hình phạt hình sự với tội phạm cổ cồn trắng và đồng phạm; khuyến nghị hướng dẫn tuyên án mạnh hơn; coi việc không chứng thực báo cáo tài chính là tội hình sự |
| **X** | Corporate Tax Returns (báo cáo thuế doanh nghiệp) | Gồm 1 mục; quy định Chief Executive Officer (CEO) phải ký vào báo cáo thuế của công ty |
| **XI** | Corporate Fraud Accountability (trách nhiệm gian lận doanh nghiệp) | Gồm 7 mục; Section 1101 đề xuất tên "Corporate Fraud Accountability Act of 2002"; xác định gian lận doanh nghiệp và làm sai lệch hồ sơ là tội hình sự gắn với hình phạt cụ thể; sửa đổi hướng dẫn tuyên án và tăng nặng hình phạt; cho phép SEC tạm thời đóng băng các giao dịch/thanh toán "lớn" hoặc "bất thường" |

*Các Title của SOX (Module 01, trang 82–84)*

---

## The Digital Millennium Copyright Act (DMCA)

> Nguồn: https://www.copyright.gov

**DMCA** là luật bản quyền (copyright law) của Hoa Kỳ, triển khai hai hiệp ước năm 1996 của **World Intellectual Property Organization (WIPO — Tổ chức Sở hữu Trí tuệ Thế giới)**: WIPO Copyright Treaty và WIPO Performances and Phonograms Treaty.

DMCA định nghĩa các quy định pháp lý cấm hành vi **vô hiệu hóa (circumvention)** các biện pháp bảo vệ công nghệ (technological protection measures) mà chủ bản quyền dùng để bảo vệ tác phẩm, và cấm việc gỡ bỏ hoặc thay đổi thông tin quản lý bản quyền (copyright management information). DMCA gồm **5 titles**:

### Title I: WIPO Treaty Implementation

Triển khai các hiệp ước WIPO. Thứ nhất, thực hiện một số sửa đổi kỹ thuật vào luật Hoa Kỳ để tạo tham chiếu và liên kết phù hợp với các hiệp ước. Thứ hai, tạo hai quy định cấm mới trong Title 17 của U.S. Code — một về việc circumvention các biện pháp công nghệ bảo vệ tác phẩm, một về việc can thiệp copyright management information — và bổ sung biện pháp khắc phục dân sự (civil remedies) cùng hình phạt hình sự (criminal penalties).

### Title II: Online Copyright Infringement Liability Limitation

Bổ sung **section 512** mới vào Copyright Act, tạo bốn giới hạn trách nhiệm pháp lý cho việc xâm phạm bản quyền bởi online service provider, dựa trên bốn loại hành vi:

- Transitory communications (truyền tin tạm thời)
- System caching (lưu đệm hệ thống)
- The user-directed storage of information on systems or networks (lưu trữ thông tin theo chỉ dẫn người dùng)
- Information location tools (công cụ định vị thông tin)

Section 512 cũng có quy định đặc biệt áp dụng cho các cơ sở giáo dục phi lợi nhuận (nonprofit educational institutions).

### Title III: Computer Maintenance or Repair

Cho phép chủ sở hữu một bản sao chương trình được sao chép hoặc chuyển thể khi cần thiết để dùng chương trình cùng máy tính. Sửa đổi cho phép chủ sở hữu hoặc người thuê máy tính được tạo (hoặc ủy quyền tạo) bản sao chương trình trong quá trình bảo trì hoặc sửa chữa máy.

### Title IV: Miscellaneous Provisions

Chứa sáu quy định khác: (1) làm rõ thẩm quyền của Copyright Office; (2) miễn trừ cho việc tạo "ephemeral recordings"; (3) thúc đẩy nghiên cứu qua distance education; (4) miễn trừ cho thư viện và lưu trữ phi lợi nhuận; (5) cho phép Webcasting Amendments to the Digital Performance Right in Sound Recordings; (6) giải quyết mối lo về khả năng nhận thanh toán còn lại của nhà văn, đạo diễn, diễn viên khi nhà sản xuất không còn khả năng chi trả.

### Title V: Protection of Certain Original Designs

Còn gọi là **Vessel Hull Design Protection Act (VHDPA)**. Tạo hệ thống mới bảo vệ thiết kế gốc của một số vật phẩm hữu ích làm cho vật phẩm hấp dẫn hoặc khác biệt. Theo VHDPA, "useful articles" giới hạn ở thân tàu (hull) — gồm cả boong (deck) — của tàu thuyền dài không quá 200 feet.

---

## The Federal Information Security Management Act (FISMA)

> Nguồn: https://csrc.nist.gov

**FISMA** (Federal Information Security Management Act of 2002) được ban hành nhằm tạo ra một số chuẩn và hướng dẫn an ninh quan trọng theo yêu cầu của Quốc hội. FISMA cung cấp một **framework toàn diện** để đảm bảo **hiệu quả của các information security control** (biện pháp kiểm soát an ninh thông tin) đối với tài nguyên thông tin hỗ trợ hoạt động và tài sản liên bang.

FISMA yêu cầu mỗi cơ quan liên bang xây dựng, lập tài liệu và triển khai một chương trình an ninh thông tin toàn cơ quan cho thông tin và hệ thống thông tin hỗ trợ hoạt động và tài sản của cơ quan đó — bao gồm cả những thứ do cơ quan khác, nhà thầu (contractor) hoặc nguồn khác cung cấp/quản lý.

Framework FISMA bao gồm:

- Chuẩn phân loại (categorizing) thông tin và hệ thống thông tin theo tác động sứ mệnh (mission impact)
- Chuẩn về yêu cầu an ninh tối thiểu (minimum security requirements) cho thông tin và hệ thống thông tin
- Hướng dẫn lựa chọn các security control phù hợp cho hệ thống thông tin
- Hướng dẫn đánh giá security control trong hệ thống thông tin và xác định hiệu quả của chúng
- Hướng dẫn cho việc cấp phép an ninh (security authorization) cho hệ thống thông tin

---

## Cyber Law in Different Countries

**Cyberlaw** (luật mạng) hay Internet law là các luật liên quan đến việc bảo vệ Internet và các công nghệ truyền thông trực tuyến khác. Cyberlaw bao gồm các chủ đề như truy cập và sử dụng Internet, quyền riêng tư, tự do ngôn luận và quyền tài phán (jurisdiction).

Luật mạng đảm bảo tính toàn vẹn, an ninh, quyền riêng tư và bảo mật của thông tin trong cả tổ chức công và tư. Các luật này trở nên nổi bật do sự gia tăng sử dụng Internet trên toàn cầu. Cyberlaw khác nhau theo từng quyền tài phán và quốc gia nên việc triển khai khá thách thức. Vi phạm các luật này dẫn đến hình phạt từ phạt tiền đến phạt tù (imprisonment).

| Quốc gia | Laws/Acts | Website |
|---|---|---|
| **United States** | Section 107 of the Copyright Law (doctrine of "fair use") | https://www.copyright.gov |
| | Online Copyright Infringement Liability Limitation Act | https://www.copyright.gov |
| | The Lanham (Trademark) Act (15 USC §§ 1051 - 1127) | https://www.uspto.gov |
| | The Electronic Communications Privacy Act | https://fas.org |
| | Foreign Intelligence Surveillance Act | https://fas.org |
| | Protect America Act of 2007 | https://www.justice.gov |
| | Privacy Act of 1974 | https://www.justice.gov |
| | National Information Infrastructure Protection Act of 1996 | https://www.nrotc.navy.mil |
| | Computer Security Act of 1987 | https://csrc.nist.gov |
| | Freedom of Information Act (FOIA) | https://www.foia.gov |
| | Computer Fraud and Abuse Act | https://energy.gov |
| | Federal Identity Theft and Assumption Deterrence Act | https://www.ftc.gov |
| **Australia** | The Trade Marks Act 1995 | https://www.legislation.gov.au |
| | The Patents Act 1990 | https://www.legislation.gov.au |
| | The Copyright Act 1968 | https://www.legislation.gov.au |
| | Cybercrime Act 2001 | https://www.legislation.gov.au |
| **United Kingdom** | The Copyright, Etc. and Trademarks (Offenses And Enforcement) Act 2002 | https://www.legislation.gov.uk |
| | Trademarks Act 1994 (TMA) | https://www.legislation.gov.uk |
| | Computer Misuse Act 1990 | https://www.legislation.gov.uk |
| **China** | Copyright Law of the People's Republic of China (Amendments on October 27, 2001) | http://www.npc.gov.cn |
| | Trademark Law of the People's Republic of China (Amendments on October 27, 2001) | http://www.npc.gov.cn |
| **India** | The Patents (Amendment) Act, 1999, Trade Marks Act, 1999, The Copyright Act, 1957 | http://www.ipindia.nic.in |
| | Information Technology Act | https://www.meity.gov.in |
| **Germany** | Section 202a. Data Espionage, Section 303a. Alteration of Data, Section 303b. Computer Sabotage | https://www.cybercrimelaw.net |
| **Italy** | Penal Code Article 615 ter | https://www.cybercrimelaw.net |
| **Japan** | The Trademark Law (Law No. 127 of 1957), Copyright Management Business Law (4.2.2.3 of 2000) | https://www.iip.or.jp |
| **Canada** | Copyright Act (R.S.C., 1985, c. C-42), Trademark Law, Canadian Criminal Code Section 342.1 | https://laws-lois.justice.gc.ca |
| **Singapore** | Computer Misuse Act | https://sso.agc.gov.sg |
| **South Africa** | Trademarks Act 194 of 1993 | http://www.cipc.co.za |
| | Copyright Act of 1978 | https://www.nlsa.ac.za |
| **South Korea** | Copyright Law Act No. 3916 | https://www.copyright.or.kr |
| | Industrial Design Protection Act | https://www.kipo.go.kr |
| **Belgium** | Copyright Law, 30/06/1994 | https://www.wipo.int |
| | Computer Hacking | https://www.cybercrimelaw.net |
| **Brazil** | Unauthorized modification or alteration of the information system | https://www.domstol.no |
| **Hong Kong** | Article 139 of the Basic Law | https://www.basiclaw.gov.hk |

*Bảng 1.4 — Cyber Law in Different Countries (Module 01, trang 88–90)*

---

## Module Summary

Module này đã trình bày:

- Các yếu tố của **information security** (an ninh thông tin), các cuộc tấn công và **information warfare**
- **Cyber kill chain methodology**, TTPs và IoCs một cách chi tiết
- Các khái niệm hacking (concepts), các loại (types) và các giai đoạn (phases)
- Các khái niệm **ethical hacking** như phạm vi (scope) và giới hạn (limitations), kỹ năng của ethical hacker và các thông tin liên quan
- Các **information security control** như defense-in-depth, risk management, cyber threat intelligence, threat modeling, incident management process, và AI & ML
- Kết thúc bằng phần thảo luận chi tiết về nhiều đạo luật và luật an ninh thông tin trên thế giới

Module tiếp theo sẽ đi sâu vào cách attacker, cũng như ethical hacker và pen tester, thực hiện **footprinting** để thu thập thông tin về mục tiêu trước khi tấn công hoặc kiểm toán (audit).
