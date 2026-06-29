# Network Footprinting

> Module 02 | Trang 117–127

## Giới thiệu

Sau khi thu thập thông tin DNS, bước tiếp theo là thu thập thông tin liên quan đến mạng. **Network footprinting** là phương pháp thu thập dấu vết (footprint) về mạng của tổ chức mục tiêu.

Phần này trình bày:

- Xác định dải địa chỉ mạng (network range)
- Phân tích traceroute
- Các công cụ traceroute

---

## Locate the Network Range (Xác định dải mạng)

Trước tiên cần thu thập thông tin cơ bản, quan trọng về tổ chức mục tiêu: tổ chức làm gì, ai làm việc ở đó, loại công việc nào. Những câu trả lời này hé lộ **cấu trúc nội bộ** của mạng mục tiêu.

Sau khi có thông tin, kẻ tấn công có thể tìm **network range** của hệ thống mục tiêu. Thông tin chi tiết về phân bổ IP và bản chất của việc cấp phát có sẵn trong cơ sở dữ liệu registry khu vực phù hợp. Kẻ tấn công cũng có thể xác định subnet mask của domain và lần theo (trace) tuyến đường giữa hệ thống của mình và hệ thống mục tiêu.

- **Công cụ traceroute** phổ biến: **Path Analyzer Pro** và **VisualRoute**.

**IANA** (Internet Assigned Numbers Authority) đã dành 3 khối địa chỉ IP cho mạng riêng (private internets):

```
10.0.0.0     – 10.255.255.255   (10/8 prefix)
172.16.0.0   – 172.31.255.255   (172.16/12 prefix)
192.168.0.0  – 192.168.255.255  (192.168/16 prefix)
```

**Lợi ích của network range với kẻ tấn công:**

- Biết mạng được cấu trúc thế nào và máy nào trong mạng đang hoạt động (alive)
- Nhận diện network topology, thiết bị kiểm soát truy cập (access control device) và OS dùng trong mạng mục tiêu

**Cách tìm:** Nhập IP server (thu được khi làm Whois footprinting) vào công cụ tìm kiếm **ARIN Whois database**. Người dùng cũng có thể truy cập website ARIN (`https://www.arin.net/about/welcome/region`) và nhập IP server vào ô **SEARCH Whois** để nhận dải mạng của mục tiêu.

> DNS server cấu hình sai tạo cơ hội tốt cho kẻ tấn công lấy danh sách máy nội bộ trên server. Ngoài ra, đôi khi nếu trace route đến một máy, có thể lấy được địa chỉ IP nội bộ của gateway.

*Hình 2.65 — Screenshot of ARIN's Region: trang ARIN "Our Region", kẻ tấn công dùng IP của server mục tiêu (`207.46.232.182`) để xác định network range.*

---

## Network Whois Record (Bản ghi Whois mạng)

Kết quả truy vấn `whois.arin.net` với IP **207.46.232.182** trả về bản ghi Network Whois của Microsoft:

| Trường | Giá trị |
|--------|---------|
| Network | NET-207-46-0-0-1 |
| Source Registry | ARIN |
| Net Range | 207.46.0.0 – 207.46.255.255 |
| CIDR | 207.46.0.0/16 |
| Name | MICROSOFT-GLOBAL-NET |
| Handle | NET-207-46-0-0-1 |
| Parent | NET-207-0-0-0-0 |
| Net Type | DIRECT ASSIGNMENT |
| Origin AS | *not provided* |
| Registration | Mon, 31 Mar 1997 |
| Last Changed | Wed, 21 Aug 2013 |
| Port 43 Whois | whois.arin.net |

**Related Entity (1 Entity):**

| Trường | Giá trị |
|--------|---------|
| Kind | Org |
| Full Name | Microsoft Corporation |
| Handle | MSFT |
| Address | One Microsoft Way, Redmond, WA, 98052, United States |
| Roles | Registrant |
| Registration | Fri, 10 Jul 1998 |
| Last Changed | Sat, 28 Jan 2017 |

*Hình 2.66 — Screenshot showing result of ARIN Whois database search result.*

> Kẻ tấn công thường dùng **nhiều hơn một công cụ** để lấy thông tin mạng, vì một công cụ đơn lẻ không thể cung cấp toàn bộ thông tin cần thiết.

---

## Traceroute

Tìm tuyến đường (route) của host mục tiêu trên mạng là cần thiết để kiểm tra phòng chống tấn công man-in-the-middle và các tấn công liên quan. Hầu hết hệ điều hành đều đi kèm tiện ích Traceroute. Nó truy vết đường đi mà các gói tin của host mục tiêu di chuyển qua mạng.

### Khái niệm hoạt động

Traceroute dùng khái niệm của **giao thức ICMP** và trường **Time to Live (TTL)** trong header của gói IP để tìm đường đi đến host mục tiêu.

Tiện ích Traceroute có thể cho biết:

- Đường đi mà gói IP di chuyển giữa hai hệ thống
- Số lượng router gói tin đi qua
- Round-trip time (thời gian truyền giữa hai router)
- Tên router và network affiliation (nếu router có DNS entry)
- Vị trí địa lý (geographic location)

**Nguyên lý TTL:** Trường TTL chỉ số router tối đa mà một gói có thể đi qua. Mỗi router xử lý gói sẽ **giảm TTL đi 1**. Khi TTL đạt 0, router **loại bỏ gói** và gửi một **ICMP error message** về nguồn.

**Quy trình:**

1. Gửi gói với **TTL = 1** → hết hạn tại router đầu tiên → router gửi ICMP error message về; Traceroute ghi lại IP và DNS name của router đó.
2. Gửi gói với **TTL = 2** → vượt qua router đầu, hết hạn tại router thứ hai → router thứ hai gửi error message về.
3. Tiếp tục tăng TTL, ghi lại IP và tên từng router cho đến khi gói tới host mục tiêu hoặc xác định host không thể tiếp cận (unreachable).
4. Ghi lại thời gian round trip cho mỗi gói đến từng router.
5. Khi tới đích, phản hồi ICMP ping bình thường (**ICMP reply message**) được gửi về người gửi.

Tiện ích này giúp lộ ra địa chỉ IP của các hop trung gian trên tuyến từ nguồn đến host mục tiêu.

```
IP Source                    Router Hop   Router Hop   Router Hop   Destination Host
   |-- ICMP Echo request --> TTL=1 X
   |<-- ICMP error message --
   |-- ICMP Echo request -------------->  TTL=2 X
   |<-- ICMP error message --------------
   |-- ICMP Echo request ----------------------------> TTL=3 X
   |<-- ICMP error message -----------------------------
   |-- ICMP Echo request ------------------------------------------> TTL=4
   |<-- ICMP reply message ------------------------------------------
```

*Hình 2.67 — Illustration of Traceroute.*

---

## ICMP Traceroute

Hệ điều hành **Windows** mặc định dùng ICMP traceroute. Mở Command Prompt và gõ lệnh **`tracert`** kèm IP đích hoặc domain name:

```
C:\>tracert 216.239.36.10

Tracing route to ns3.google.com [216.239.36.10] over a maximum of 30 hops:

  1   <1 ms    <1 ms    <1 ms   10.10.10.2
  2   20 ms     4 ms     5 ms   1.6.15.234
  3   21 ms    19 ms    21 ms   100.66.8.23
  4   20 ms    19 ms    19 ms   100.68.8.23
  5   23 ms    41 ms    20 ms   72.14.210.200
  6   21 ms    21 ms    23 ms   108.170.248.163
  7   68 ms    67 ms    67 ms   209.85.242.115
  8  102 ms   102 ms   102 ms   209.85.247.194
  9  100 ms   106 ms   122 ms   72.14.239.175
 10  114 ms   119 ms   114 ms   209.85.244.31
 11  114 ms   112 ms   112 ms   209.85.247.118
 12  114 ms   118 ms   115 ms   74.125.253.85
 13  111 ms   112 ms   113 ms   ns3.google.com [216.239.36.10]

Trace complete.
```

---

## TCP Traceroute

Nhiều thiết bị trong mạng thường được cấu hình để **chặn (block) ICMP traceroute**. Trong trường hợp này, kẻ tấn công dùng **TCP hoặc UDP traceroute** — còn gọi là **Layer 4 traceroute**.

Trên Linux, mở terminal và gõ lệnh **`tcptraceroute`** kèm IP đích hoặc domain name:

```
tcptraceroute www.google.com

Running:
    traceroute -T -O info www.google.com
traceroute to www.google.com (172.217.163.164), 30 hops max, 60 byte packets
 1  10.10.10.2 (10.10.10.2)  0.312 ms  0.172 ms  0.207 ms
 2  maa05s05-in-f4.1e100.net (172.217.163.164) <syn,ack>  17.775 ms  17.367 ms  17.491 ms
```

*Hình 2.68 — Screenshot showing the output of TCP Traceroute (Parrot Terminal).*

---

## UDP Traceroute

Giống Windows, **Linux** cũng có tiện ích traceroute tích hợp sẵn, nhưng dùng **giao thức UDP** để truy vết tuyến đến đích. Mở terminal trên Linux và gõ lệnh **`traceroute`** kèm IP đích hoặc domain name:

```
traceroute www.google.com

traceroute to www.google.com (172.217.163.164), 30 hops max, 60 byte packets
 1  10.10.10.2 (10.10.10.2)  0.260 ms  0.189 ms  0.196 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
```

*Hình 2.69 — Screenshot showing the output of UDP Traceroute (Parrot Terminal).*

---

## Traceroute Analysis (Phân tích traceroute)

Tiện ích Traceroute giúp tìm địa chỉ IP của các thiết bị trung gian (router, firewall) giữa nguồn và đích. Sau khi chạy nhiều lần traceroute, kẻ tấn công có thể xác định vị trí của một hop trong mạng mục tiêu.

Kẻ tấn công chạy traceroute để trích xuất thông tin về **network topology**, **trusted routers** và **vị trí firewall**.

**Ví dụ — các kết quả traceroute thu được:**

```
traceroute 1.10.10.20  → second to last hop is 1.10.10.1
traceroute 1.10.20.10  → third to last hop  is 1.10.10.1
traceroute 1.10.20.10  → second to last hop is 1.10.10.50
traceroute 1.10.20.15  → third to last hop  is 1.10.10.1
traceroute 1.10.20.15  → second to last hop is 1.10.10.50
```

Bằng cách ghép các thông tin này lại, kẻ tấn công có thể vẽ **network diagram** (sơ đồ mạng) của mục tiêu:

```
Hacker --- Internet --- 1.10.10.1 Router --- 1.10.10.50 Firewall ─┬─ 1.10.10.20 Bastion Host
                                                                  │
                                                          [DMZ ZONE]
                                                                  ├─ 1.10.20.10 Web Server
                                                                  ├─ 1.10.20.15 Mail Server
                                                                  └─ 1.10.20.50 Firewall
```

*Hình 2.70 — Traceroute Analysis.*

---

## Traceroute Tools (Công cụ traceroute)

Các công cụ traceroute như **Path Analyzer Pro**, **VisualRoute**, **Traceroute NG** và **PingPlotter** hữu ích trong việc trích xuất thông tin về vị trí địa lý của router, server và thiết bị IP trong mạng. Chúng giúp truy vết, nhận diện và giám sát hoạt động mạng trên bản đồ thế giới.

**Một số tính năng:**

| | |
|---|---|
| Hop-by-hop traceroutes | Ping plotting |
| Reverse tracing | Port probing |
| Historical analysis | Detect network problems |
| Packet loss reporting | Performance metrics analysis |
| Reverse DNS | Network performance monitoring |

**Bảng công cụ:**

| Công cụ | Nguồn | Mô tả |
|---------|-------|-------|
| **Path Analyzer Pro** | `https://www.pathanalyzer.com` | Thực hiện network route tracing với performance test, DNS, Whois và network resolution để điều tra sự cố mạng |
| **VisualRoute** | `http://www.visualroute.com` | Công cụ traceroute và chẩn đoán mạng (network diagnostic), xác định vị trí địa lý của router, server và thiết bị IP |

### Path Analyzer Pro

Kẻ tấn công dùng Path Analyzer Pro để nhận diện tuyến đường từ nguồn đến hệ thống đích **một cách trực quan (graphically)**. Công cụ giúp thu thập thông tin cho mỗi hop trên tuyến:

- Hop number
- IP address
- Hostname
- ASN
- Network name
- Percentage loss (% loss)
- Latency
- Average latency
- Standard deviation (Std Dev)

*Hình 2.71 — Screenshot of Path Analyzer Pro: hỗ trợ protocol ICMP / TCP / UDP, Maximum TTL 30, kết quả hiển thị dưới dạng report.*

### VisualRoute

VisualRoute là công cụ traceroute và chẩn đoán mạng. Kẻ tấn công dùng VisualRoute để xác định **vị trí địa lý** của router, server và các thiết bị IP trong mạng mục tiêu.

Công cụ giúp theo dõi đường đi giữa hệ thống nguồn và đích, trình bày kết quả ở **định dạng đồ họa**. Thông tin thu thập gồm:

- Hop number
- IP address
- Node name
- Vị trí địa lý của mỗi hop trên tuyến

*Hình 2.72 — Screenshot of VisualRoute (Business Edition): traceroute đến `www.facebook.com` (157.240.7.35), Network: Facebook, Inc., Location: Menlo Park USA, RTT 77.0ms / 75ms / 79ms, Route length 20 hops, kèm bản đồ thế giới hiển thị tuyến đường.*
