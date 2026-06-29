# Footprinting through Social Engineering

> Module 02 | Trang 128–130

## Giới thiệu

**Social engineering** (kỹ thuật tấn công phi kỹ thuật) là **nghệ thuật khai thác hành vi con người** để **moi thông tin bí mật**. Kẻ tấn công dựa vào thực tế rằng **con người không nhận thức được giá trị** của thông tin mình nắm giữ và thường bất cẩn trong việc bảo vệ nó.

Đây là một tiến trình **non-technical** (không thiên về kỹ thuật): kẻ tấn công đánh lừa nạn nhân để họ **vô tình** cung cấp thông tin bí mật. Nạn nhân không hề biết rằng có người đang đánh cắp thông tin của mình. Kẻ tấn công lợi dụng **bản tính cả tin (gullible)** và sự sẵn lòng chia sẻ thông tin của con người.

Để thực hiện social engineering, kẻ tấn công trước tiên cần **chiếm được lòng tin** của một người dùng hợp lệ, sau đó dẫn dụ họ tiết lộ thông tin bí mật. Mục tiêu là lấy được thông tin cần thiết rồi dùng vào các mục đích xấu như:

- Truy cập trái phép vào hệ thống
- Đánh cắp danh tính (identity theft)
- Gián điệp công nghiệp (industrial espionage)
- Xâm nhập mạng (network intrusion)
- Gian lận (fraud), …

## Thông tin mà social engineer cố gắng thu thập

- Credit card details và social security number
- User names và passwords
- Các security product đang sử dụng
- Operating systems và phiên bản phần mềm
- Thông tin về bố cục mạng (network layout)
- IP addresses và tên của các server

## Các kỹ thuật Social Engineering

Social engineering có thể được thực hiện theo nhiều cách:

- **Eavesdropping** (nghe lén)
- **Shoulder surfing** (nhìn trộm qua vai)
- **Dumpster diving** (lục thùng rác)
- **Impersonation** (giả mạo danh tính)
- Tailgating, third-party authorization, piggybacking, reverse social engineering, …

---

## Collecting Information Using Eavesdropping, Shoulder Surfing, Dumpster Diving, and Impersonation

Bốn kỹ thuật social engineering được dùng phổ biến để thu thập thông tin từ con người:

### 1. Eavesdropping (Nghe lén)

- **Nghe lén trái phép** các cuộc trò chuyện hoặc đọc trộm tin nhắn.
- Là hành vi **chặn bắt (interception)** bất kỳ hình thức giao tiếp nào: **audio, video hoặc text**.

Eavesdropping là hành vi bí mật lắng nghe cuộc trò chuyện của người khác qua điện thoại hoặc hội nghị truyền hình mà **không có sự đồng ý** của họ. Nó cũng bao gồm việc đọc các tin nhắn bí mật từ phương tiện giao tiếp như instant messaging hoặc fax. Kẻ tấn công lấy thông tin bằng cách **nghe lén cuộc gọi điện thoại** hoặc chặn bắt audio, video, hoặc giao tiếp dạng văn bản.

### 2. Shoulder Surfing (Nhìn trộm qua vai)

- **Bí mật quan sát mục tiêu** để thu thập thông tin quan trọng như **passwords, mã PIN (personal identification number)**, số tài khoản và thông tin thẻ tín dụng.

Trong kỹ thuật này, kẻ tấn công đứng **phía sau nạn nhân** và bí mật quan sát hoạt động trên máy tính của họ, chẳng hạn các phím gõ (keystrokes) khi nhập username, password. Kỹ thuật này hiệu quả trong việc lấy passwords, mã PIN, mã bảo mật, số tài khoản, thông tin thẻ tín dụng. Kẻ tấn công dễ dàng thực hiện shoulder surfing ở **nơi đông người**, vì có thể đứng sau và quan sát nạn nhân mà họ không hề hay biết.

### 3. Dumpster Diving (Lục thùng rác)

- **Tìm "kho báu" trong rác của người khác.**
- Thu thập **hóa đơn điện thoại, thông tin liên hệ, thông tin tài chính**, thông tin liên quan đến vận hành, … từ thùng rác của công ty mục tiêu, thùng rác máy in, bàn làm việc (sticky notes), v.v.

Kỹ thuật "kém lịch sự" này còn gọi là **trashing**, nghĩa là kẻ tấn công bới tìm thông tin trong thùng rác. Thông tin có thể thu được gồm: hóa đơn điện thoại, thông tin liên hệ, thông tin tài chính, thông tin vận hành, bản in mã nguồn (source codes), bản in thông tin nhạy cảm, … từ thùng rác công ty, thùng rác máy in, sticky notes trên bàn người dùng. Kẻ tấn công cũng có thể thu thập thông tin tài khoản từ **thùng rác của máy ATM**. Những thông tin này hỗ trợ kẻ tấn công thực hiện các cuộc tấn công khác.

### 4. Impersonation (Giả mạo danh tính)

- **Giả vờ là một người hợp lệ hoặc có thẩm quyền** và dùng điện thoại hoặc phương tiện giao tiếp khác để đánh lừa mục tiêu, dụ họ tiết lộ thông tin.

Kẻ tấn công thực hiện impersonation trực tiếp hoặc qua điện thoại/phương tiện giao tiếp khác. Kẻ tấn công có thể đóng giả:

- Nhân viên giao hàng (courier/delivery person)
- Lao công (janitor)
- Doanh nhân (businessman)
- Khách hàng (client)
- Kỹ thuật viên (technician)
- Hoặc giả vờ là khách đến thăm (visitor)

Bằng kỹ thuật này, kẻ tấn công thu thập thông tin nhạy cảm bằng cách: dò tìm password trên các terminal, lục soát tài liệu quan trọng trên bàn, bới thùng rác, … Kẻ tấn công thậm chí có thể cố **nghe lén** các cuộc trò chuyện bí mật và "**shoulder surf**" để lấy thông tin nhạy cảm.
