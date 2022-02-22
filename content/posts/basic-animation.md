---
title: "CSS Cơ Bản: Animation Cơ Bản"
date: 2022-01-31
description: "Một trang web đẹp và hiện đại không thể thiếu những hiệu ứng, chuyển động mượt mà và đẹp mắt. Trong bài viết này, ta sẽ tìm hiểu về các thành phần tạo nên các hiệu ứng ấy, bao gồm transformations, transitions và animations."
---

> Một trang web đẹp và hiện đại không thể thiếu những hiệu ứng, chuyển động mượt mà và đẹp mắt. Trong bài viết này, ta sẽ tìm hiểu về các thành phần tạo nên các hiệu ứng ấy, bao gồm transformations, transitions và animations.

![Animation](/images/animation2.png)

## Transformations

**Transform** là những thuộc tính dùng để "biến đổi" các phần tử, cho phép chúng thay đổi vị trị, hình dáng, kích thước hay xoay phần tử theo các chiều.

Có 2 kiểu là **2D** và **3D transformation**.
![Animation](/images/animation1.png)
Tên các thuộc tính tương ứng với hiệu ứng mà chúng mang lại, lần lượt là: **xoay, thay đổi tỉ lệ, tạo độ lệch, dịch chuyển**. Ta sẽ dùng các ví dụ để dễ dàng hình dung các thay đổi mà thuộc tính của **transform** mang lại.

### Rotate

![Animation](/images/animation3.gif)

### Scale

![Animation](/images/animation4.gif)

### Skew

![Animation](/images/animation5.gif)

### Translate

![Animation](/images/animation6.gif)

### Sử dụng kết hợp

![Animation](/images/animation7.gif)

## 3D Transformations

Với **3D Transformations**, bên cạnh các hiệu ứng thay đổi trên **trục x** và **trục y** như trên **2D Transformations**, ta còn cần quan tâm thêm **trục z** (độ gần, xa). Bên cạnh đó, ta còn cần quan tâm thuộc tính **transform-origin** - vị trí chọn làm gốc cho hiệu ứng diễn ra.

Dưới đây là ví dụ về một số **3D Transformations** thường gặp.

### Translate

![Animation](/images/animation8.gif)

### Rotate

![Animation](/images/animation9.gif)

### Transform nhiều items

![Animation](/images/animation10.gif)

## Transitions

Thuộc tính **Transition** được sử dụng khá rộng rãi để tạo ra các hiệu ứng chuyển đổi đẹp mắt trên website một cách dễ dàng. Hoạt động bằng cách thay đổi giá trị thuộc tính một cách trơn tru từ giá trị này sang giá trị khác trong khoảng thời gian nhất định.

Các tham số thường được sử dụng:\
**- transition-property:** thuộc tính cần chuyển đổi (all nếu muốn tất cả).\
**- transition-duration:** khoảng thời gian chuyển đổi diễn ra.\
**- transition-timing-function:** tốc độ chuyển đổi diễn ra (ease, linear, ease-in, ease-out, ease-in-out, cubic-bezier: tốc độ tuỳ chọn).\
**- transition-delay:** khoảng thời gian dừng cho mỗi hiệu ứng chuyển đổi.

Để tạo ra hiệu ứng chuyển đổi Transition, bạn phải xác định ít nhất hai điều:\
**- Thuộc tính CSS muốn thêm hiệu ứng vào**.\
**- Thời gian chuyển đổi diễn ra (duration)**.

Trong ví dụ bên dưới, ta sẽ chọn thuộc tính áp dụng là **transform** với thời gian **0.5s**, tốc độ **ease-in** (chậm tới nhanh)

![Animation](/images/animation11.gif)

## Animations

**Animation** được hiểu là hiệu ứng chuyển động, sử dụng để tạo hiệu ứng di chuyển cho các phần tử và được sử dụng khá nhiều trong các website hiện nay.

Để tạo một chuyển động **Animation**, ta cần phải có các **keyframe**. Mỗi **keyframe** sẽ được chạy ở một thời điểm xác định và trong keyframe đó nó quy định việc phần tử sẽ di chuyển ra sao.

Một số thuộc tính quan trọng:\
**- animation-name**: tên namiation cần thực thi.\
**- animation-duration**: khoảng thời gian diễn ra hiệu ứng.\
**- animation-timing-function**: tốc độ thay đổi hiệu ứng (ease, linear, ease-in, ease-out, ease-in-out, cubic-bezier: tốc độ tuỳ chọn).\
**- animation-delay**: khoảng thời gian trì hoãn.\
**- animation-iteration-count**: số lần thực hiện một animation (số lần, infinite).\
**- aniamtion-direction**: xác định hướng chạy animation.\
**- animation-fill-mode**: thay đổi trạng thái của phần tử trước khi bắt đầu sau khi kết thúc Animation.

Ta có ví dụ đơn giản như bên dưới để tìm hiểu về các thuộc tính của **Animation**. Ta khởi tạo 1 **keyframes** với tên **pop**, và thiết lập các mốc thời gian và hiệu ứng thay đổi tương ứng. Sau đó áp dụng shorthand **animation** với các thông số lần lượt là: **pop (name) - 4s (duration) - ease-out (timing-function) - 1s (delay) - infinite (iteration-count) - alternate (direction).**
![Animation](/images/animation12.gif)

### Tái sử dụng Animation

Thay vì phải áp dụng thuộc tính animation cho từng phần tử, ta có thể tách riêng hiệu ứng animation thành một class riêng, và áp dụng vào bất cứ phần tử mà mình mong muốn. Ví dụ:
![Animation](/images/animation13.png)

