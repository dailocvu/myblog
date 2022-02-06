---
title: "[Tuần 3] CSS Cơ Bản: Responsive Design"
date: 2022-02-05
description: "Ngày nay, trong lĩnh vực lập trình web, ta nhanh chóng nhận ra rằng không thể theo kịp với sự phát triển chóng mặt của các thiết bị điện tử mới với độ phân giải màn hình khác nhau. Chính vì vậy thay vì thiết kế từng phiên bản phù hợp cho từng thiết bị, thì giải pháp tối ưu là sử dụng Responsive Design - giúp trang web của chúng ta có thể phù hợp với tất cả kích thước màn hình trên các thiết bị."
---

> Ngày nay, trong lĩnh vực lập trình web, ta nhanh chóng nhận ra rằng không thể theo kịp với sự phát triển chóng mặt của các thiết bị điện tử mới với độ phân giải màn hình khác nhau. Chính vì vậy thay vì thiết kế từng phiên bản phù hợp cho từng thiết bị, thì giải pháp tối ưu là sử dụng Responsive Design - giúp trang web của chúng ta có thể phù hợp với tất cả kích thước màn hình trên các thiết bị.

## Responsive Design là gì?

Hiểu một cách đơn giản, Responsive Design là kỹ thuật thiết kế web, mà trang web này có thể đáp ứng nhiều kích cỡ giao diện trên nhiều thiết bị khác nhau, không bị vỡ, mất giao diện, nội dung. Theo đó quy trình thiết kế và phát triển web sẽ đáp ứng mọi thiết bị và môi trường của người dùng theo các tiêu chí kích thước và chiều của màn hình thiết bị.

Có hai xu hướng thiết kế **Responsive Design** chính, đó là **Desktop first** và **Mobile first**.
![Responsive](/images/responsive1.png)
**- Desktop first:** Đối với phương pháp này, giao diện sẽ được ưu tiên code sao cho phù hợp với màn hình Desktop trước rồi sau đó mới tiếp tục thêm code CSS mới vào bằng **@media query** sao cho giao diện và bố cục trang web của bạn phù hợp với các màn hình bé hơn (tablet, mobile).\
**- Mobile first:** Ở phương pháp này, giao diện web sẽ được thực hiện theo hướng từ thiết bị có màn hình nhỏ (Mobile) rồi mới đến các thiết bị có màn hình lớn hơn (Tablet, Laptop, Desktop), và cũng sử dụng **@media query** để thực hiện quá trình này.\
![Responsive](/images/responsive4.png)

Hầu hết toàn bộ các nội dung trong website đều cần responsive, tuy nhiên có một số vị trí ta cần đặc biệt lưu tâm, đó là: **menu, các cột layout, font size và image**.

Tiếp theo đây chúng ta sẽ tìm hiểu các yếu tố quan trọng khi thực hiện **responsive** một trang web.

## Viewport

**Viewport** là khung hình người dùng nhìn thấy trên thiết bị của họ khi vào một trang web bất kì. Với mỗi thiết khác nhau lại có viewport khác nhau. Nếu trang web cố định kích thước thì trình duyệt sẽ tự động thu nhỏ nội dung khi chuyển từ màn hình máy tính qua smartphone - điều này tạo nên trải nghiệm không tốt cho người dùng.

HTML5 cung cấp cho ta phương pháp kiểm soát điều này một cách dễ dàng thông qua thẻ **meta**.
![Responsive](/images/responsive2.png)

**width=device-width:** thiết lập chiều rộng của trang web theo chiều rộng của thiết bị.\
**initial-scale=1.0:** thiết lập mức độ zoom ban đầu khi trang web được load bởi trình duyệt.
![Responsive](/images/responsive3.png)

## Grid-View

Rất nhiều trang web được xây dựng trên **grid-view**, có nghĩa là trang web được chia thành các cột đều nhau. Một **grid-view** thường có 12 cột ứng với 100% độ rộng và sẽ thu nhỏ hoặc mở rộng khi bạn thay đổi kích thước trình duyệt. Việc sử dụng **grid-view** sẽ giúp bạn dễ dàng đặt vị trí các phần tử trên trang hơn, thuận lợi cho việc thực hiện responsive về sau.
![Responsive](/images/responsive6.png)

## Media Queries

**Media Queries** là một kỹ thuật CSS được giới thiệu trong CSS3. Ta sử dụng cú pháp **@media** để bao gồm một khối các thuộc tính CSS chỉ khi một điều kiện nhất định là đúng. Nói một cách đơn giản là ta sẽ định nghĩa CSS riêng cho một nhóm các thiết bị có kích thước giống nhau.

### FlexBox và Grid Layout

Việc sử dụng thuần thục và hợp lý **FlexBox** và **Grid** trên các đối tượng phù hợp sẽ tạo ra trải nghiệm responsive trên layout và nội dung rất tốt trên mọi trình duyệt. Bằng cách kết hợp 2 đối tượng này với **media queries**, ta có thể tạo ta các layout khác nhau dựa trên kích thước màn hình của thiết bị.

Như trong ví dụ bên dưới với **FlexBox** sử dụng phương pháp responsive **Mobile first**, ta có thể sử dụng **flex-direction: row** trên các thiết bị có màn hình lớn, và chuyển sang **flex-direction: column** trên các thiết bị màn hình nhỏ hơn.
![Responsive](/images/responsive5.png)  
![Responsive](/images/responsive7.png)
Một công cụ hữu ích khác trong **Chrome Dev Tools**, ta có thể sử dụng **device toolbar** để mô phỏng nội dung được hiển thị trên màn hình của các thiết bị.
![Responsive](/images/responsive8.png)

### Breakpoints

Khi ta thay đổi kích thước của trình duyệt, ta chú ý thấy kích thước của **viewport** sẽ được hiển thị ở góc phải trên của màn hình. Dựa vào kích thước này và **breakpoints** ta có thể chủ động căn chỉnh sao cho phù hợp với kích cỡ các thiết bị mong muốn.
![Responsive](/images/responsive9.png)
![Responsive](/images/responsive10.png)

Ta sẽ áp dụng **media queries** để thực hiện responsive cho man hình trên các thiết bị lớn hơn, cụ thể ở đây là với kích thước > 600px, **flex-direction** sẽ chuyển sang **row**.
![Responsive](/images/responsive11.png)

## Sử dụng thư viện và frameworks

Hiện nay, có rất nhiều các thư viện và CSS frameworks hỗ trợ giúp cho việc responsive một trang web trở nên linh động, dễ dàng và hiệu quả hơn rất nhiều, các frameworks này cũng dựa trên **media queries**, **breakpoints** và các tuỳ chỉnh khác để giúp đỡ cho các lập trình viên thực hiện công việc responsive và styling của mình dễ dàng hơn. Tuy nhiên, ta không nên quá dựa dẫm vào các thư viện, frameworks, đây chỉ là các công cụ, ta cần nắm vững các kiến thức nền để có thể xử lý bất cứ tình huống và bài toán nào.
![Responsive](/images/responsive12.png)

