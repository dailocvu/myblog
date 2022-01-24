---
title: "[Tuần 1] Một số khái niệm cơ bản về công nghệ Web"
date: 2022-01-19
description: "DNS là gì, cách thức hoạt động của nó, cũng như những khái niệm liên quan như Domain Name, Hosting, HTTP là gì?
Các trình duyệt web là gì? Cách thức hoạt động của chúng ra sao?"
---

> Trong tuần đầu tiên, ta sẽ đi tìm hiểu về một số khái niệm cơ bản nhưng rất quan trọng trong lĩnh vực công nghệ web, bao gồm DNS, Domain Name, Hosting, HTTP và các trình duyệt web.

## 1. DNS là gì, cách thức hoạt động của nó?

**DNS (Domain Name System hay hệ thống phân giải tên miền)** giống như một cuốn sổ lưu trữ danh bạ của Internet. Nghĩa là thay vì phải nhớ hàng tá số điện thoại với một đống con số, thì ta chỉ cần nhớ tên của chủ nhân số điện thoại.

Các thiết bị máy tính tìm kiếm và giao tiếp với nhau thông qua địa chỉ IP, là những dãy số duy nhất, việc ghi nhớ tất cả dãy số là bất khả thi. Trong trường hợp này, số điện thoại sẽ tương ứng với địa chỉ IP của Website, còn tên chủ nhân chính là tên miền của website đó.

Do đó, khi mở trình duyệt và muốn tìm một trang web, ta truy cập thông qua tên miền (vd: google.com, facebook.com) mà ta có thể ghi nhớ dễ dàng, nhiệm vụ của DNS lúc này là chuyển đổi các tên miền này qua một địa chỉ IP tương ứng, và đưa ta đến đúng trang web mà mình mong muốn.
![DNS](/images/dns.gif)
_Thay vì phải ghi nhớ một chuỗi địa chỉ IP nhiều chữ số (vd: 142.250.68.14), ta có thể truy cập thông qua tên miền google.com_

Ngoài ra thì mỗi DNS còn có chức năng ghi nhớ những tên miền mà nó đã phân giải và trong những lần truy cập tới, nó sẽ ưu tiên sử dụng giúp ta truy cập nhanh chóng và dễ dàng hơn.

### Để tìm hiểu rõ hơn về cách thức DNS hoạt động, ta cần tìm hiểu một chút về các loại DNS Server và vai trò của chúng. Có tới 4 server tham gia vào hệ thống phân giải tên miền:

#### 1. DNS Recursor

DNS Recursor có thể được coi như một thủ thư, nhận nhiệm vụ lấy và trả thông tin về cho trình duyệt để tìm đúng thông tin mà chúng cần. Nói cách khác, DNS Recursor giữ trách nhiệm liên lạc với các Server khác để phản hồi đến trình duyệt người dùng.

#### 2. Root Name Server

Đây là Server quan trọng nhất trong hệ thống cấp bậc của DNS. Là bước đầu tiên trong việc biên dịch tên máy chủ thành địa chỉ IP. Ta cũng có thể hiểu rằng, Root Name Server chính là một thư viện để định hướng tìm kiếm.

#### 3. TLD Nameserver

Có thể được coi như một giá sách cụ thể trong thư viện. Máy chủ định danh này là bước tiếp theo trong quá trình tìm kiếm địa chỉ IP cụ thể và nó lưu trữ phần cuối cùng của tên máy chủ. Khi ta truy cập Google, phần mở rộng sẽ là “.com”. Đây được gọi là Top-level Domain.'
TLD Nameserver sẽ phản hồi từ DNS Recursor, sau đó giới thiệu nó cho một Authoritative DNS Server – hay nơi chứa nguồn dữ liệu của tên miền đó.

#### 4. Authoritative Nameserver

Khi DNS Resolver tìm thấy Authoritative Nameserver, đó là lúc mà việc phân giải tên miền diễn ra. Nó có thể được coi như một cuốn từ điển trên giá sách, chứa thông tin cho biết tên miền đang gắn với địa chỉ nào. Nó sẽ cung cấp cho DNS Recursor địa chỉ IP cần thiết tìm thấy trong danh mục những bản ghi của nó.

### Cách thức hoạt động của DNS

DNS hoạt động từng bước theo cấu trúc của nó. Bước đầu là một truy vấn để lấy thông tin được gọi là **"DNS query"**.
Đầu tiên, DNS server sẽ tìm thông tin phân giải trong file hosts, chịu trách nhiệm chuyển hostname thành IP.
Nếu không thấy thông tin, nó sẽ quay về tìm trong cache – bộ nhớ tạm. Nơi phổ biến nhất thường lưu thông tin này chính là bộ nhớ tạm của trình duyệt và bộ nhớ tạm ISP (Internet Service Providers).
Nếu không nhận được thông tin, ta sẽ thấy mã lỗi hiện lên.

### 10 bước khi DNS thực hiện tra cứu

**Bước 1.** Người dùng nhập tên miền (VD: google.com) vào trình duyệt. Truy vấn này sẽ được tiếp nhận bởi trình phân giải DNS.\
**Bước 2.** Trình phân giải sẽ gửi truy vấn đến DNS Root Name Server.\
**Bước 3.** Sau đó, Root Name Server sẽ phản hồi lại địa chỉ của Top Level Domain (tròng trường hợp này là .com), nơi lưu trữ thông tin về tên miền.\
**Bước 4.** Trình phân giải gửi yêu cầu tới .com TLD.\
**Bước 5.** Máy chủ TLD phản hồi lại địa chỉ IP của máy chủ tên miền (google.com).\
**Bước 6.** Trình phân giải gửi truy vấn đến máy chủ tên miền.\
**Bước 7.** Địa chỉ IP của google.com sau đó được trả về trình phân giải từ máy chủ định danh.\
**Bước 8.** Sau đó, trình phân giải DNS sẽ phản hồi lại trình duyệt web bằng địa chỉ IP của tên miền được yêu cầu.\
**Bước 9.** Trình duyệt gửi HTTP request tới địa chỉ IP này.\
**Bước 10.** Máy chủ của IP đó trả về nội dung trang web và hiển thị lên trình duyệt.\
![DNS Step](/images/dnsstep.png)

## 2. Domain Name (tên miền) là gì?

Như đã tìm hiểu ở trên, tên miền là một đoạn văn bản mà người dùng nhập vào trình duyệt để truy vấn đến một trang web cụ thể. Tên miền này ánh xạ tới một địa chỉ IP cụ thể. Ví dụ, tên miền của Google là ‘google.com’.

Địa chỉ thực của một trang web là một địa chỉ IP, là chuỗi số dài và khó nhớ (VD: 142.250.68.14), nhưng nhờ DNS, người dùng có thể nhập vào các tên miền dễ nhớ và truy cập được trang web mình mong muốn.

### Ta cùng phân tích 1 tên miền gồm có những gì nhé.

Một tên miền có thể được chia thành 2 hoặc 3 phần, ngăn cách nhau bởi dấu "." Khi đọc từ phải sang trái, phía bên phải sẽ có cấp độ cao nhất và giảm dần. Phần đầu tiên từ phải qua được gọi là top-level domain (TLD) bao gồm các TLD chung (.com, .net) hoặc định danh khu vực, đất nước (.vn, .uk)

Bên trái của TLD là second-level domain (2LD), tiếp đến là third-level domain (3LD) nếu tồn tại

VD: Tên miền của Google: google.com

- .com là TLD
- Google là 2LD

Nhưng trong trường hợp tên miền của Google tại Việt Nam: google.com.vn

- .vn là TLD
- .com là 2LD
- Google là 3LD

Bên cạnh đó còn có Subdomain, tên miền phụ như một phần mở rộng của TLD.
(VD: images.google.com, mail.google.com)

### Vậy ai sẽ quản lý nhưng tên miền này? Có quy ước chung nào không?

Tất cả các tên miền đều do công ty đăng ký tên miền quản lý, và được uỷ quyền việc bảo lưu tên miền. Bất cứ ai muốn tạo một website thì cần có tên miền riêng của mình, hiện tại đã có trên 300 triệu tên miền được đăng ký

## 3. Hosting là gì?

![Hosting ](/images/hosting.png)
Hosting là quá trình xuất bản một website lên Internet. Để một website hoạt động, ta cần lưu trữ chúng trên một máy chủ, nơi chứa tất cả các files và dữ liệu cần thiết để website có thể chạy được

Trong đó máy chủ là một máy tính vật lý (gồm RAM, bộ nhớ, băng thông,..) chạy xuyên suốt để website có thể luôn hoạt động mọi lúc cho tất cả mọi người truy cập vào. Nhà cung cấp chịu trách nhiệm cho việc giữ server hoạt động, chống tấn công bởi mã độc, và chuyển nội xuống trình duyệt người dùng.

### Cách thực Hosting hoạt động?

Khi quyết định tạo một website, bên cạnh việc chọn tên miền, ta cũng cần lưu ý việc chọn công ty hosting để lưu trữ nội dung của trang web. Khi ta truy cập tên miền lên thanh địa chỉ, hosting sẽ chuyển các nội dung cần thiết từ máy chủ xuống trình duyệt

### Các loại web hosting?

Có nhiều loại hosting khác nhau để đáp ứng từng nhu cầu khác nhau của khách hàng, với chi phí tương ứng tuỳ theo các dịch vụ mà hosting cung cấp (băng thông, dung lượng, giới hạn nội dung, độ bảo mật, tốc độ,…), bao gồm các loại phổ biến là:

#### 1. Shared Hosting

Phổ biến nhất và lựa chọn hàng đầu cho những doanh nghiệp nhỏ và blog, chia sẽ tài nguyên server với những khách hàng khác của nhà cung cấp hosting, Website được đặt trên cùng một server để sử dụng chung tài nguyên và bộ nhớ, sức mạnh xử lý, dung lượng đĩa.

**Ưu điểm:**\
• Giá thành thấp\
• Thân thiện cho người mới bắt đầu\
• Server được cấu hình sẵn\
• Nhà cung cấp chịu trách nhiệm quản lý và vận hành server

#### 2. VPS Hosting

Là loại web hosting cũng dùng chung server với người dùng khác, tuy nhiên nhà cung cấp web host sẽ phân chia phân vùng trên server cho riêng bạn với bộ nhớ và sức mạnh vi xử lý riêng chỉ cho bạn phù hợp cho những doanh nghiệp cỡ vừa và các website đang có phát triển nhanh chóng.

**Ưu điểm:**\
• Tài nguyên server riêng (mà không phải mua hẵn một server)\
• Truy cập lớn từ website khác không làm ảnh hưởng tới hiệu năng của site của bạn\
• Truy cập quyền root lên server\
• Dễ nâng cấp\
• Khả năng tùy biến cao

#### 3. Cloud Hosting

Đang là giải pháp đáng tin cậy nhất trên thị trường, vì dường như nó hoàn toàn không có downtime. Với cloud hosting, nhà cung cấp của bạn có một bộ các server. Files và tài nguyên được phân phối trên các server. Khi một trong các server cloud bị quá tải hoặc có bất kỳ vấn đề nào, traffic của bạn sẽ tự động được chuyển tới và xử lý tại server khác

**Ưu điểm:**\
• Gần như không có downtime\
• Server hỏng không ảnh hưởng tới site của bạn\
• Tài nguyên được phân phối tùy nhu cầu\
• Thanh toán tùy vào mức độ sử dụng\
• Linh hoạt hơn VPS, về khả năng mở rộng

#### 4. WordPress Hosting

WordPress hosting là một dạng của shared hosting, được thiết kế riêng cho chủ website WordPress. Server của bạn được cấu hình riêng cho WordPress và site được gắn các plugin được cài sẵn như là caching pluign và plugin bảo mật. Vì lý do cấu hình được tùy chỉnh riêng, site của bạn sẽ tải nhanh hơn và chạy ngay không gặp vấn đề gì. WordPress hosting thường có nhiều tính năng liên quan đến WordPRess như là, WordPress theme được thiết kế riêng, builder kéo thả và các công cụ đặc thù riêng.

**Ưu điểm:**\
• Giá thành thấp\
• Dễ sử dụng cho người mới bắt đầu\
• Một click cài được WordPress\
• Hiệu năng tốt cho WordPress site\
• Đội ngũ hỗ trợ kỹ thuật được đạo tào để xử lý các vấn đề liên quan đến WordPress\
• WordPress plugins và theme được cài sẵn

#### 5. Dedicated Server Hosting

Là một server vật lý của riêng bạn, toàn bộ tài nguyên trên server đó là dánh riêng cho bạn. Vì vậy, dedicated server cho bạn toàn bộ quyền quyết định lên server, hoàn toàn linh hoạt sử dụng. Bạn có thể cấu hình server tùy thích, chọn lựa hệ điều hành và phần mềm cần sử dụng, cài đặt một môi trường hosting riêng, đặc biệt cho nhu cầu của bạn.

**Ưu điểm:**\
• Toàn quyền kiểm soát cấu hình server\
• Đáng tin (Bạn không chia sẽ bất kỳ tài nguyên nào với bất kỳ ai)\
• Quyền truy cập root\
• Tính bảo mật cao

## 4. HTTP là gì?

HTTP là từ viết tắt của **Hyper Text Transfer Protocol** nghĩa là giao thức truyền tải siêu văn bản được sử dụng trong World Wide Web.

Là nền tảng của bất kỳ sự trao đổi dữ liệu nào trên Web và cũng là giao thức giữa client và server. Một tài liệu hoàn chỉnh được tái tạo từ các tài liệu con khác nhau chẳng hạn như văn bản, mô tả bố cục, hình ảnh, video,..
![Fetching](/images/fetching_a_page.png)

Client và Server giao tiếp bằng cách trao đổi các thông điệp độc lập. Các thông điệp được gửi từ Client, thường là một trình duyệt Web, được gọi là requests và các thông điệp phản hồi về từ Server được gọi là responses (giao thức yêu cầu – phản hồi).\
![HTTP](/images/http.jpg)

### Những thứ có thể được kiểm soát bởi HTTP.

-- Bộ nhớ đệm: HTTP có thể kiểm soát các tài liệu được lưu trong bộ đệm. Server có thể hướng dẫn Client về những gì cần lưu vào bộ nhớ cache và trong bao lâu.\
-- Ràng buộc: Để ngăn chặn việc theo dõi và các hành vi xâm phạm quyền riêng tư, các trình duyệt Web tạo ra sự tách biệt giữa các trang Web. Chỉ các trang có cùng nguồn gốc mới có thể truy cập vào tất cả thông tin của một trang Web
-- Xác thực: Một số trang có thể được bảo vệ để chỉ những người dùng cụ thể mới có thể truy cập chúng thông qua WWW-Authenticate hay HTTP cookies.\
-- Server hoặc Client thường được đặt trên mạng nội bộ và ẩn địa chỉ IP thực của chúng với các máy tính khác. Các yêu cầu HTTP sau đó sẽ đi qua proxy để vượt qua rào cản này.\
-- Phiên làm việc: thông qua Cookies cho phép ghi nhớ những thông tin như tên đăng nhập, mật khẩu, các tuỳ chọn do người dùng lựa chọn (vd giỏ hang,..). Các thông tin này được lưu trong máy tính để nhận biết người dùng khi truy cập vào một trang web.

### Các phương thức HTTP Requests

**Phân loại**\
Các phương thức HTTP được sử dụng phổ biến nhất là POST, GET, PUT, PATCH và DELETE. Các phương thức này tương ứng với các hoạt động tạo, đọc, cập nhật và xóa (Create – Read – Update – Delete ).\
Có một số phương pháp khác, nhưng chúng được sử dụng ít thường xuyên hơn (HEAD, CONNECT, OPTIONS, TRACE)

**Công dụng**\
![Usage](/images/usage.png)

### Các mã trạng thái HTTP phổ biến

![Status code](/images/statuscode.png)

### HTTP Request

![HTTP Request](/images/http_request.png)

### HTTP Response

![HTTP Response](/images/http_response.png)

## 5. Trình duyệt và cách chúng hoạt động.

Các Trình duyệt web về cơ bản là một ứng dụng phần mềm để truy cập thông tin trên World Wide Web. Mỗi trang web, hình ảnh và video riêng lẻ được xác định bằng một URL riêng biệt, cho phép các trình duyệt truy xuất và hiển thị chúng trên thiết bị của người dùng.

Hiện nay có các trình duyệt web phổ biến như Google Chrome, Mozilla Firefox, Safari, Microsoft Edge,..

Trình duyệt web thường giao tiếp với máy chủ web bằng việc sử dụng Giao thức HTTP để gửi thông tin đến các máy chủ và lấy về các tài nguyên của trang web.

### Cấu trúc trình duyệt

![Browser](/images/browser1.png)

#### User Interface

Là tầng cao nhất, nơi tương tác chủ yếu giữa người dùng và trình duyệt, nó bao gồm các thành phần quen thuộc như thanh Address, các nút Reload – Back – Home, Biểu tượng Bookmarks… Những thành phần này không ảnh hưởng đến việc hiển thị của trang mà chủ yếu giúp cho việc tương tác thuận tiện hơn.

#### Browser Engine

Đây là tầng nằm giữa và là cầu nối giữa User Interface & Rendering Engine. Tầng này sẽ cung cấp các hành động để giao tiếp và xử lý dữ liệu từ tầng Rendering Engine lên tầng User Interface và ngược lại, chuyển đổi những hành động người dùng thao tác trên tầng Interface xuống Rendering Engine.

#### Rendering Engine (Layout engine)

Đây là một tầng quan trọng, nó đóng vai trò xử lý (rendering) các thẻ – câu lệnh HTML, CSS, XML, JS để hình thành giao diện (layout) hiển thị lên tầng User Interface, những gì chúng ta sẽ nhìn thấy và tương tác. Nên cũng có thể hiểu nếu tầng này xử lý không hiệu quả thì phía trên người dùng cũng không hiển thị tốt.

Các trình duyệt dùng những bộ xử lý Rendering Engine khác nhau.

#### Networking – JavaScript Interpreter – Display UI Backend

Networking: Có nhiệm vụ gọi các giao thức về mạng. Ví dụ như các giao thức HTTP (Hypertext Transfer Protocol).

UI Backend: Có chức năng xử lý và hiển thị các UI components phổ biến như combo-boxes, textbox, drop-down hiển thị trên web.

JavaScript interpreter: xử lý và thực thi các đoạn mã JavaScript để hiển thị lên trang web. Đây cũng là một thành phần rất quan trọng ảnh hưởng đến việc hiển thị trang web, do các trang web hiện nay thường cần xử lý và sử dụng khá nhiều mã JavaScript.

#### Data persistence

Có chức năng lưu trữ thông tin và dữ liệu trên máy local. Những dữ liệu này có thể là Cache, Cookies, localStorage, IndexedDB, WebSQL and FileSystem tùy vào từng hệ thống web.

### Công việc của một trình duyệt chủ yếu bao gồm:

#### Phân tích DNS

Quá trình này đảm rằng khi người dùng nhâp URL, trình duyệt sẽ biết máy chủ đích mà mình cần kết nối. Trình duyệt sẽ liên hệ tới máy chủ DNS để biên dịch tên miền thành địa chỉ IP và kết nối tới địa chỉ này.

#### HTTP exchange

Khi trình duyệt đã xác định được mảy chủ mà mình cần gửi yêu cầu đến, nó sẽ bắt đầu kết nối TCP và thực hiện HTTP exchange. Dựa trên giao thức request - response.

#### Rendering

Tiến trình quan trọng, là yếu tố cơ bản của trình duyệt, đó là hiển thị lên giao diện các nội dung cần thiết.

![Parsing](/images/parsing.png)

**Bước 1:**

**Phân tích HTML & CSS**

Ở bước đầu tiên này, Rendering Engine sẽ có nhiệm vụ:

Phân tích thẻ HTML: Phân tích các thẻ HTML được viết trong trong code và tạo thành một cấu trúc cây dạng DOM (Document Object Model)

**Phân tích CSS qua CSSOM (CSS Object Model)**

Giống như HTML, CSS cũng chia thành dạng nhánh với mục đích tạo thành một cấu trúc các elements phục vụ cho quá trình render, tuy nhiên giữa DOM và CSSOM là hai quá trình độc lập nhau.

Có thể hiểu, giai đoạn đầu tiên phân tích là chuyển các thẻ HTML sang dạng DOM & chuyển CSS sang CSSOM – sẽ được dùng trong bước tiếp theo. DOM sẽ lo về nội dung hiển thị, CSSOM sẽ tập trung vào style sẽ dùng trong những nội dung document.

**Bước 2: Render tree**

Sau khi nhận được kết quả là cấu trúc DOM/CSSOM ở bước trên, giai đoạn thứ 2 này sẽ tạo cấu trúc cây từ DOM/CSSOM. Các nút từ cây DOM và CSSOM sẽ được kết hợp lại với nhau tại giai đoạn này. Mục tiêu của Render cây là sẽ sắp xếp các thành phần theo thứ tự sẽ được hiển thị (từ trên xuống dưới).

![Render Tree](/images/render-treepng.png)

**Bước 3: Layout**

Giai đoạn này đcó nhiệm vụ tính toán vị trí hiển thị cũng như hình dáng của các đối tượng của render tree. Việc tính toán và phân bổ đối đối tượng sẽ được thực hiện tuần tự từ trái sang phải và trên xuống dưới tính từ tọa độ trên cùng từ bên trái. Việc này sẽ mang ý nghĩa quan trọng và quyết định đến hiển thị và bố cục layout trước khi chuyển sang giai đoạn xuất ra giao diện.

**Bước 4: Painting**

Đây là giai đoạn cuối của quá trình, trình duyệt sẽ hiển thị nội dung đến cho người dùng. Quá trình painting này cũng được làm theo thứ tự nhất định và xuất ra dạng pixels hiển thị.

Thời gian để painting sẽ phụ thuộc và kích thước của cấu trúc DOM, CSSOM. Một vài thuộc tính sẽ tốn thời gian painting hơn những thuộc tính khác.
