# CEH v11 — Ethical Hacking and Countermeasures

> **EC-Council Official Curricula — Professional Series**
> Certified Ethical Hacker | Exam **312-50**
> Nguồn: EC-Council, *Ethical Hacking and Countermeasures*, Version 11

Repo này chứa **ghi chú học tập tiếng Việt** được biên soạn từ bộ giáo trình chính thức CEH v11 của EC-Council. Mỗi module được tổ chức theo các mục (section) với file `content.md` tóm tắt nội dung từng nhóm trang.

> ⚠️ **Lưu ý bản quyền:** Bản scan gốc (ảnh trong các thư mục `images/`) **không** được đưa lên repo (xem `.gitignore`). Repo chỉ lưu phần ghi chú/diễn giải phục vụ mục đích học tập cá nhân. Toàn bộ nội dung gốc thuộc bản quyền © 2020 EC-Council.

---

## Giới thiệu chương trình CEH

> *"If you want to stop hackers from invading your network, first you've got to invade their minds."*

Mục tiêu của **ethical hacker** là giúp tổ chức chủ động phòng vệ trước các cuộc tấn công độc hại bằng cách tự mình tấn công hệ thống — nhưng luôn nằm trong giới hạn pháp lý. Triết lý này xuất phát từ nguyên tắc "muốn bắt trộm phải nghĩ như kẻ trộm".

Ethical Hacker là người thường được tổ chức thuê và **được tin cậy** để thử xâm nhập mạng/hệ thống bằng chính các phương pháp mà hacker dùng. Hacking là hành vi phạm pháp ở nhiều quốc gia; chỉ hợp pháp khi **có yêu cầu và hợp đồng** giữa ethical hacker và tổ chức. Điểm mấu chốt: ethical hacker phải có **ủy quyền (authorization)** để kiểm thử mục tiêu.

Chứng chỉ **Certified Ethical Hacker (C|EH)** xác nhận năng lực theo hướng *vendor-neutral*, củng cố kiến thức cho security officer, auditor, security professional, site administrator và bất kỳ ai quan tâm đến tính toàn vẹn của hạ tầng mạng.

Thông tin chi tiết: https://www.eccouncil.org/programs/certified-ethical-hacker-ceh

---

## Thông tin kỳ thi CEH

| Mục | Chi tiết |
|-----|----------|
| **Exam Title** | Certified Ethical Hacker (CEH) |
| **Exam Code** | 312-50 |
| **Availability** | EC-Council Exam Portal (https://www.eccexam.com) · VUE (https://home.pearsonvue.com/eccouncil) |
| **Duration** | 4 giờ |
| **Questions** | 125 câu |
| **Passing Score** | Tham khảo https://cert.eccouncil.org/faq.html |

Thông tin thêm: https://cert.eccouncil.org/certified-ethical-hacker.html

---

## Danh mục Module

| # | Module | Trạng thái ghi chú |
|---|--------|--------------------|
| 01 | [Introduction to Ethical Hacking](./Module%2001%20-%20Introduction%20to%20Ethical%20Hacking/00-module-overview.md) | ✅ Hoàn thiện |
| 02 | [Footprinting and Reconnaissance](./Module%2002%20-%20Footprinting%20and%20Reconnaissance/00-module-overview.md) | ✅ Hoàn thiện |
| 03 | Scanning Networks | ⏳ Chưa làm |
| 04 | Enumeration | ⏳ Chưa làm |
| 05 | Vulnerability Analysis | ⏳ Chưa làm |
| 06 | System Hacking | ⏳ Chưa làm |
| 07 | Malware Threats | ⏳ Chưa làm |
| 08 | Sniffing | ⏳ Chưa làm |
| 09 | Social Engineering | ⏳ Chưa làm |
| 10 | Denial-of-Service | ⏳ Chưa làm |
| 11 | Session Hijacking | ⏳ Chưa làm |
| 12 | Evading IDS, Firewalls, and Honeypots | ⏳ Chưa làm |
| 13 | Hacking Web Servers | ⏳ Chưa làm |
| 14 | Hacking Web Applications | ⏳ Chưa làm |
| 15 | SQL Injection | ⏳ Chưa làm |
| 16 | Hacking Wireless Networks | ⏳ Chưa làm |
| 17 | Hacking Mobile Platforms | ⏳ Chưa làm |
| 18 | IoT and OT Hacking | ⏳ Chưa làm |
| 19 | Cloud Computing | ⏳ Chưa làm |
| 20 | Cryptography | ⏳ Chưa làm |

**Phụ lục:** Appendix A — Ethical Hacking Essential Concepts I · Appendix B — Ethical Hacking Essential Concepts II · Glossary · References

---

## Các chứng chỉ khác của EC-Council

EC-Council (*International Council of Electronic Commerce Consultants*, thành lập cuối 2001) là tổ chức toàn cầu về chứng chỉ và đào tạo an ninh thông tin, hiện cung cấp tại hơn 145 quốc gia qua hơn 950 trung tâm đào tạo được ủy quyền.

| Chứng chỉ | Lĩnh vực |
|-----------|----------|
| **CSCU** — Certified Secure Computer User | Security Awareness — kiến thức nền bảo vệ tài sản thông tin |
| **CND** — Certified Network Defender | Network Defense — phòng thủ mạng thực chiến |
| **CPENT** — Certified Penetration Testing Professional | Penetration Testing nâng cao (Windows, IoT, OT, pivoting…) |
| **CHFI** — Computer Hacking Forensic Investigator | Computer Forensics — điều tra số |
| **E\|CIH** — Certified Incident Handler | Incident Handling — xử lý sự cố sau xâm nhập |
| **CCISO** — Certified Chief Information Security Officer | Management — vai trò CISO |
| **CASE** (.NET / Java) — Certified Application Security Engineer | Application Security trong vòng đời SDLC |
| **C\|TIA** — Certified Threat Intelligence Analyst | Threat Intelligence |
| **CSA** — Certified SOC Analyst | SOC operations (Tier I & II) |

---

## Cấu trúc thư mục

```
CEH-v11/
├── README.md
├── .gitignore                         # bỏ qua **/images/
├── Module 01 - Introduction to Ethical Hacking/
│   ├── 00-module-overview.md          # tổng quan + Module Flow
│   ├── images/                        # bản scan gốc (không commit)
│   ├── Information Security Overview/content.md
│   ├── Cyber Kill Chain Concepts/content.md
│   ├── Hacking Concepts/content.md
│   ├── Ethical Hacking Concepts/content.md
│   ├── Information Security Controls/content.md
│   └── Information Security Laws and Standards/content.md
├── Module 02 ... Module 20/
├── Appendix A / Appendix B / Glossary / References/
```

---

## Bản quyền & Miễn trừ

Copyright © 2020 by **EC-Council**. All Rights Reserved. Reproduction is Strictly Prohibited.

EC-Council New Mexico — 101C Sun Ave NE, Albuquerque, NM 87109.
Yêu cầu cấp phép: legal@eccouncil.org · Hỗ trợ: support@eccouncil.org

Tài liệu trong repo là **ghi chú học tập cá nhân**, không phải bản phân phối lại của giáo trình gốc. Mọi nhãn hiệu (CEH, CND, CHFI, …) thuộc về EC-Council. Người đọc tự chịu trách nhiệm khi áp dụng các kỹ thuật được mô tả và chỉ thực hiện kiểm thử khi **có ủy quyền hợp pháp**.
