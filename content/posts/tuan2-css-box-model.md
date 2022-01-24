---
title: "[Tuần 2] CSS Cơ Bản: Box Model"
date: 2022-01-23
description: "Trong tuần này, chúng ta bắt đầu tìm hiểu về các khái niệm cơ bản của CSS.
Bắt đầu với nền tảng quan trọng đầu tiên - CSS Box Model."
---

> Trong tuần này, chúng ta bắt đầu tìm hiểu về các khái niệm cơ bản của CSS.
> Bắt đầu với nền tảng quan trọng đầu tiên - CSS Box Model.

## CSS Box Model là gì?

Trong CSS, thuật ngữ **Box Model** được sử dụng khi nói về thiết kế và bố cục.\
Khi trình duyệt render một phần tử HTML, chúng sẽ được bao bọc xung quanh bởi một chiếc hộp vô hình, bao gồm nội dung, padding, border và margin.
![Box model](/images/box-model.jpg)

## Bao gồm:

**Content** - nội dung trong hộp, nơi hiển thị văn bản, hình ảnh,...\
**Padding** - phần khoảng trắng xung quanh nội dung, trong suốt.\
**Border** - đường viền xung quanh nội dung và padding.\
**Margin** - phần lề bên ngoài đường viền, trong suốt.

Giả sử ta có một phần tử **p**, khi rê chuột vào phần tử này trong HTML DOM, phần tử này sẽ được biểu diễn dạng Box Model như bên dưới:  
![Box model](/images/box-2.jpg)

**Content** - kích thước của nội dung, với chiều dài chiếm toàn bộ.\
**Padding** - không có.\
**Border** - không có.\
**Margin** - 16, mặc định của trình duyệt.

Ta có thể thay đổi các thông số trên dễ dàng với 1 vài cú pháp CSS:
![Box model](/images/box-3.png)

## Tính toán kích thước thực

Khi thiết lập đặc tính chiều cao và rộng (width, height) của phần tử bằng CSS, ta chỉ thiết lập cho phần nội dung mà thôi. (Mặc định **box-sizing: content-box**). Để tính toán chính xác kích thước phần tử, cần tính toán thêm cả phần padding và border - là 2 thành phần ảnh hưởng tới kích thước thực của nội dung.

Như ví dụ bên trên, phần kích thước thực sẽ là:\
**Chiều cao:** 18.286 + 10 + 10 + 5 + 5 = 48.286\
**Chiều rộng:** 481.429 + 20 + 20 + 5 + 5 = 531.429

Tuy nhiên, việc luôn phải tính toán thêm kích thước của các thành phần khác khiến mọi thứ trở lên khó khăn và bất tiện khi ta cần thay đổi kích thước của một giá trị. Do đó, ta có thể sử dụng việc thiết lập vùng kích thước tính toán cho cả padding và border: **box-sizing: border-box**.

Ví dụ khi thiết lập kích thước chiều cao và rộng của phần tử bằng **100px**. Dễ dàng nhận thấy ở **border-box** phần kích thước của nội dung đã được tính toán cùng padding và border.
![Box model](/images/box-4.png)

## Thuộc tính Margin có tính collapse

Không như khi ta thêm padding và border, phần kích thước được tăng hoặc giảm sẽ tác động trực tiếp nội dung và ta sẽ dễ dàng nhận ra. Tuy nhiên, nếu hai phần tử đều có thuộc tính margin nằm cạnh nhau, phần kích thước margin sẽ được tính bằng phần tử có kích thước lớn hơn.

Trong trường hợp dưới đây, thuộc tính margin được thiết lập với giá trị là **20px** cho cả hai phần tử **p**. Tuy nhiên, khoảng cách giữa hai phần tử chỉ là **20px**.\
![Margin](/images/margin.png)
