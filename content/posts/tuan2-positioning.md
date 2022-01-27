---
title: "[Tuần 2] CSS Cơ Bản: Positioning"
date: 2022-01-26
description: "Position trong CSS được sử dụng để định vị vị trí hiển thị của các phần tử thẻ HTML, với 5 thuộc tính cơ bản bao gồm Static, Relative, Absolute, Fixed và Sticky."
---

## Position trong CSS là gì?

Position trong CSS được sử dụng để định vị vị trí hiển thị của các phần tử thẻ HTML.

Khi nói đến vị trí, ta thường hình dung ra 4 vị trí chính, bao gồm: trên (top) - dưới (bottom) - trái (left) - phải (right). Khi thực hiện layout, ta sẽ cần quan tâm đến nhiều vị trí phức tạp hơn:\
![Position](/images/position1.png)

Position trong CSS có 5 thuộc tính cơ bản, bao gồm:\
**Static** - Mặc định, các phần tử HTML được định vị tĩnh. Không bị ảnh hưởng bởi các thuộc tính left, right, top, bottom.\
**Relative** - Vị trí của phần tử sẽ tương đối so với vị trí ban đầu của nó.\
**Absolute** - Vị trí tương đối so với phần tử ông/cha gần nhất. \
**Fixed** - Vị trí sẽ nằm cố định một chỗ, tương đối với Viewport, dù có làm gì, phần tử vẫn nằm cố định 1 vị trí trên màn hình.\
**Sticky** - Vị trí của phần tử sẽ được định vị khi người dùng sử dụng thanh cuộn.\
Ngoài ra còn có hai thuộc tính khác là **Initial** và **Inherit**.

Để dễ dàng hình dung, ta sẽ bắt đầu ví dụ với 3 boxes với vị trí mặc định như bên dưới:
![Position](/images/position0.png)

## Relative

Vị trí của phần tử sẽ tương đối so với vị trí ban đầu của nó. Ta có thể sử dụng các thuộc tính **left, right, top, bottom** để định vị vị trí của nó. Vị trí của các phần tử khác xung quanh sẽ không bị ảnh hưởng.

Trong ví dụ bên dưới, vị trí của **box-two** đã được dịch chuyển cách vị trí ban đầu của nó 3rem left và bottom. **box-one** và **box-three** không bị ảnh hưởng.\
![Position](/images/position2.png)

## Absolute

Vị trí tương đối so với phần tử ông/cha gần nhất, nếu không tìm thấy nó sẽ thiết lập vị trí tương đối so với Viewport của trình duyệt.\
Phần tử ông/cha cần được thiết lập **position: relative**.\
Khi vị trí của phần tử được set **absolute**, nó sẽ bị tách biệt, xoá ra khỏi flow thông thường của trang.

Trong ví dụ bên dưới, phần tử cha **boxes** được set **position: relative**, chú ý vị trí **box-three** đã được tự động đưa lên.\
![Position](/images/position3.png)

Khi phần tử ông/cha không được set **position: relative**, nó sẽ thiết lập vị trí tương đối với Viewport.\
Trong ví dụ bên dưới, ta chú ý thấy **box-two** đã nằm bên ngoài container.\
![Position](/images/position4.png)

## Fixed

Phần tử được định vị bằng **fixed** sẽ có vị trí tương đối so với Viewport trên trình duyệt. Cũng bị tách biệt ra khỏi flow thông thường của trang như **absolute**. Vị trí của nó sẽ luôn cố định.\
![Viewport](/images/viewport.png)\
Một trong những ứng dụng của **fixed** là khi ta muốn thanh navigation luôn luôn nằm ở vị trí trên cùng của trang.

Trong ví dụ bên dưới, ta chú ý thấy **box-two** đã nằm bên ngoài container, vị trí của nó lúc này tương đối so với Viewport. Khi cuộn trang, vị trí của nó vẫn luôn cố đinh (**top: 0**).\
![Position](/images/position5.gif)

## Sticky

Phần tử được định vị bằng **sticky** sẽ được coi như có vị trí tương đối, cho đến khi thanh cuộn đạt đến một ngưỡng được chỉ định, khi đó phần tử sẽ có vị trí cố định tại nơi được yêu cầu. Tức linh động chuyển từ trạng thái **relative** sang **fixed** và ngược lại.

Trong ví dụ bên dưới, ban đầu, **box-two** sẽ có vị trí mặc định, cho tới khi người dùng thực hiện thao tác cuộn trang, khi **box-two** đạt ngưỡng được chỉ định **top: 1rem**, tức vị trí của nó cách top một khoảng **1rem**, **fixed** sẽ được kích hoạt, nó sẽ được đính cố định tại vị trí này. Khi người dùng cuộn trang trở lại, **box-two** sẽ được đính lại vị trí đầu nếu đi qua vị trí ban đầu của nó (**relative**).
![Position](/images/position6.gif)

Một lưu ý nữa là **sticky** không hỗ trợ trên IE và các phiên bản trình duyệt cũ, nên ta cần cân nhắc kĩ khi sử dụng. Ta có thể tham khảo cụ thể hơn ở [đây](https://caniuse.com/?search=sticky)
![Position](/images/position7.png)

## Initial và Inherit (Không chỉ có trong Position mà còn có trong hầu hết các thuộc tính khác của CSS.)

**Initial** - Thiết lập về giá trị position mặc định của nó.\
**Inherit** - Kế thừa thuộc tính position từ phần tử cha.
