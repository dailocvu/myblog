---
title: "[Tuần 3] CSS Cơ Bản: Flexible Box Layout (FlexBox)"
date: 2022-01-27
description: "Dàn bố cục cho trang là một trong những công việc quan trọng nhất khi ta bắt đầu lập trình giao diện một trang web. Có hai cách để ta có thể dàn trang một cách linh hoạt và dễ dàng là sử dụng FlexBox và Grid Layout, trong bài viết này, ta sẽ tìm hiểu về FlexBox và các đặc điểm của nó."
---

> Dàn bố cục cho trang là một trong những công việc quan trọng nhất khi ta bắt đầu lập trình giao diện một trang web. Có hai cách để ta có thể dàn trang một cách linh hoạt và dễ dàng là sử dụng FlexBox và Grid Layout, trong bài viết này, ta sẽ tìm hiểu về FlexBox và các đặc điểm của nó.

## FlexBox là gì?

**FlexBox** (hay Flexible Box) là một kiểu bố cục trang **theo một hướng** (chiều ngang/dọc), có khả năng tự cân đối kích thước, thay đổi chiều rộng/chiều cao và thứ tự phần tử bên trong để phù hợp với tất cả các loại thiết bị hiển thị và kích thước màn hình.\
![Flexbox](/images/flex1.gif)

## Cấu trúc của FlexBox

**FlexBox** được cấu tạo từ hai thành phần chính:\
**- Container:** chứa đựng các items bên trong, các items sẽ được hiển thị dựa trên thiết lập của container.\
**- Items:** là các phần tử con, ta có thể dùng các thiết lập để điều chính cách thức chúng được hiện thị.

Để có thể điều chỉnh các items theo hướng ta mong muốn, ta cần quan tâm tới **Axes** (các trục), các trục này sẽ phụ thuộc vào hướng mà ta muốn dàn trang (ngang/dọc). Gồm **main axis (primary)** và **cross axis (secondary)**
![Flexbox](/images/flex2.webp)
![Flexbox](/images/flex3.png)

## Các thuộc tính của Container

Nắm được hai trục trên, ta có thể dễ dàng căn chỉnh các **items** bên trong **container** dựa vào các thuộc tính:\
![Flexbox](/images/flex4.png)

Để minh hoạ dễ hiểu hơn, ta sẽ bắt đầu với ví dụ dưới đây, **gồm 1 container chứa 3 boxes**:\
![Flexbox](/images/flex5.png)

Ta có thể dễ dàng áp dụng **FlexBox** layout bằng cách thêm thuộc tính **display: flex** vào **container**. Mặc định các items sẽ được dàn theo chiều ngang (row) khi ta áp dụng **flex** mà không thiết lập hướng cho chúng.
![Flexbox](/images/flex6.png)

### Flex Direction

Để điều chỉnh hướng ta muốn hiển thị của các **items** bên trong **container**, ta sử dụng thuộc tính **flex-direction**, với các tuỳ chọn gồm **row | row-reverse | column | column-reverse**.

![Flexbox](/images/flex7.png)

### Justify Content

Thuộc tính **justify-content** để điều chỉnh vị trí bắt đầu và căn chỉnh các items bên trong container dọc theo trục **main axis**, chiều ngang/dọc tùy thuộc vào **flex-direction**. Trong ví dụ bên dưới, **flex-direction** theo chiều ngang. Tức **justify-content** sẽ căn chỉnh các items theo **chiều ngang**.

Bao gồm các thuộc tính **flex-start | flex-end | center | space-between | space-around | space-evenly**.\
![Flexbox](/images/flex8.png)

### Align Items

Thuộc tính **align-items** sử dụng để điều chỉnh vị trí bắt đầu và căn chỉnh các item bên trong container dọc theo trục **cross axis**, chiều ngang/dọc tùy thuộc vào **flex-direction**. Trong ví dụ bên dưới, **flex-direction** theo chiều ngang. Tức **align-items** sẽ căn chỉnh các items theo **chiều dọc**.

Bao gồm các thuộc tính **stretch | flex-start | flex-end | center | baseline**\
![Flexbox](/images/flex9.png)

### Flex Wrap

Mặc định, items sẽ tự động thay đổi kích thước để nó luôn hiển thị trên cùng một dòng dù ta có thay đổi kích thước trình duyệt, điều này dễ làm cho nội dung bên trong bị giãn hay ép nhỏ lại. Thuộc tính **flex-wrap** cho phép items tự động xuống dòng khi kích thước container thay đổi.

Bao gồm các thuộc tính **nowrap | wrap | wrap-reverse**
![Flexbox](/images/flex11.png)

### Align Content

Thuộc tính **align-content** sử dụng để căn chỉnh khoảng cách các item bên trong container dọc theo trục **cross axis**, chiều ngang/dọc tùy thuộc vào **flex-direction**. Trong ví dụ bên dưới, **flex-direction** theo chiều ngang. Tức **align-items** sẽ căn chỉnh các items theo **chiều dọc**.

Bao gồm các thuộc tính **flex-start | flex-end | center | space-between | space-around | stretch**
![Flexbox](/images/flex10.png)

## Các thuộc tính của Items

### Align Self

Ở phần trên, ta đã biết cách để bố cục, di chuyển tất cả các **items** bên trong **container**, vậy nếu ta chỉ muốn di chuyển duy nhất 1 item thì sao?

Thuộc tính **align-self** có tác dụng tương tự như **align-items** của container nhưng sử dụng riêng cho từng item, ta có thể dùng nó để đặt vị trí cho item.

**Align-self** cũng có các thuộc tính giống như **align-items**, gồm: **flex-start | flex-end | center | baseline | stretch**
![Flexbox](/images/flex12.png)

### Sizing Items

Ở trên ta đã nói khá nhiều về căn chỉnh vị trí, tiếp theo đây, ta sẽ tìm hiểu về điều chỉnh kích thước của các **items** bên trong **container**.
![Flexbox](/images/flex13.png)

### Flex Basis

Thuộc tính **flex-basis** sử dụng để xác định **độ dài** ban đầu của một item.

Nếu **flex-direction: row** - **flex-basis** sẽ ghi đè thuộc tính của **width**.\
Nếu **flex-direction: column** - **flex-basis** sẽ ghi đè thuộc tính của **height**.
![Flexbox](/images/flex14.png)

### Flex Grow

Thuộc tính **flex-grow** cho phép các phần tử giãn theo độ rộng của container, nhằm chiếm lấy các phần còn trống bên trong container.
![Flexbox](/images/flex15.png)

### Flex Shrink

Thuộc tính **flex-shrink** ngược lại với **flex-grow**, nó không giãn ra mà co lại nếu các items không đủ khoảng trống để vừa container, khi chúng ta thay đổi độ rộng của nó.

Giá trị mặc định trong **flex-shrink** là 1, cho phép các phần tử co lại bằng nhau khi độ rộng container giảm xuống. Nếu **flex-shrink: 0** thì item sẽ không co giãn. Giá trị càng lớn thì độ co lại nhiều hơn.
![Flexbox](/images/flex16.gif)

### Flex

Thuộc tính **flex** là shorthand sử dụng để gộp chung ba thuộc tính **flex-grow, flex-shrink và flex-basis**.
![Flexbox](/images/flex17.png)

### Order

Mặc định, các item sẽ hiển thị theo thứ tự trong HTML, nhưng với thuộc tính order, ta có thể sắp xếp lại vị trí của các item.
![Flexbox](/images/flex18.png)

