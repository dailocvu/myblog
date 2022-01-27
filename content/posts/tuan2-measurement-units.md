---
title: "[Tuần 2] CSS Cơ Bản: Measurement Units"
date: 2022-01-25
description: "CSS hỗ trợ nhiều đơn vị đo lường được chia thành hai loại chính, là đơn vị tuyệt đối và đơn vị tương đối."
---

## Các đơn vị đo lường trong CSS là gì?

CSS hỗ trợ nhiều đơn vị đo lường được chia thành hai loại chính, đơn vị tuyệt đối và đơn vị tương đối.

**Đơn vị tuyệt đối:** là những đơn vị mà giá trị của nó không bao giờ thay đổi và không bị ảnh hưởng bởi các thành phần khác. Tức là trong mọi kích thước màn hình thì kích thước của nó vẫn như thế.\
**Đơn vị tương đối:** là những đơn vị được tính một cách tương đối dựa trên các phần tử khác (có thể là phần tử cha hoặc root). Các đơn vị loại này khá linh động, thích hợp cho việc thích ứng trên các thiết bị khác nhau.

Các đơn vị thường gặp được biểu diễn qua bảng dưới đây:

![Units](/images/units.png)

## Đơn vị tuyệt đối

Với các đơn vị tuyệt đối thì giá trị của nó được cố định và không bị ảnh hưởng bởi bất kỳ thành phần nào khác.

Các đơn vị này chỉ nên sử dụng với những thành phần đã được xác định chính xác kích thước hoặc các thuộc tính có kích thước nhỏ ví dụ như **border: 3px solid orange;**
![Units](/images/px.png)\
Ta có thể xác mình bằng cách thay đổi kích thước trình duyệt. Các đơn vị này sẽ không bị thay đổi.

Trong các đơn vị tuyệt đối, đơn vị được sử dụng nhiều nhất là **px**. Tuy nhiên, đôi lúc ta có thể gặp những đơn vị khác, hình dưới đây sẽ giúp ích, khi ta gặp bối rối về cách quy đổi của chúng.
![Units](/images/units2.jpg)

## Đơn vị tương đối

**%** - Tỉ lệ phần trăm với phần tử cha.\
![Units](/images/percent.gif)

**vw và vh**\
**vw** - Tỉ lệ với kích thước chiều rộng khung nhìn. 1vw = 1% viewport width. Ví dụ: màn hình có chiều rộng 1000px thì 1vw = 10px.\
**vh** - Tỉ lệ với kích thước chiều cao khung nhìn. 1vw = 1% viewport height.\
![Units](/images/vwvh.gif)

**em và rem - hai đơn vị thường xuyên được sử dụng**\
Sử dụng khi ta cần điều chỉnh layout dựa trên font-size. Ví dụ khi font-size lớn hơn, ta muốn kích thước layout cũng tăng lên.

**em** - Tỉ lệ với thuộc tính font-size của chính nó (ưu tiên) hoặc phần tử cha.\
Ví dụ: 10em = 10 x font-size = 200px.\
![Units](/images/em1.png)\
Nếu không được chỉ định font-size, nó sẽ tìm kiếm font-size của cha, và tiếp tục cha tiếp theo, đến cuối cùng nếu vẫn không có thì sẽ sử dụng font-size mặc định của root là **16px** \
![Units](/images/em2.png)

1 lưu ý khác khi sử dụng **em** trên font-size, kích thước sẽ được tính dựa trên font-size của cha. Trong khi sử dụng trên các thuộc tính khác thì sẽ ưu tiên font-size của chính nó.\
![Units](/images/em3.png)

**rem** - Tỉ lệ với thuộc tính font-size của phần tử **root (html)**.

Vì font-size của root sẽ được cố định (mặc định là 16px nếu không thiết lập), nên ta sẽ dễ dàng tính toán hơn. Nhưng tính toán nhanh với **16** đôi lúc có chút khó khăn, nên ta có thể sử dụng trick dưới đây để tính toán được nhanh hơn.\
Ta set **html { font-size: 62.5% }**, vì mặc định font-size là 16px = 100%, 62,5% tức 10px, do đó, khi tính toán với **10** sẽ dễ dàng hơn.\
![Units](/images/rem.png)
Trong trường hợp font-size được thay đổi theo thiết bị hoặc cài đặt của người dùng, ta sẽ có layout được tự động điều chỉnh to nhỏ phù hợp.
![Units](/images/rem2.png)

## 1 số đơn vị đo khác

**vmin và vmax** - tương tự như vw và vh. Điểm khác biệt là nó sẽ không tỉ lệ theo 1 hướng mà là cả 2, tuỳ thuộc vào độ lớn của chiều cao và chiều rộng màn hình.\
1 vmin = 1 vw hoặc 1 vh (Lấy cái nhỏ hơn). VD: màn hình có kích thước là 840×640 thì 1 vmin = 6.4px, nếu màn hình là 360×480 thì 1 vmin = 3.6px.\
1 vmax = 1 vw hoặc 1 vh (Lấy cái lớn hơn). VD: màn hình có kích thước là 840×640 thì 1 vmin = 8.4px, nếu màn hình là 360×480 thì 1 vmin = 4.8px.

**ch** - là đơn vị được tính theo chiều rộng của ký tự “0”. Với những font chữ là monospace thì các ký tự đều có cùng 1 chiều rộng.

## Không có đơn vị đo nào là tốt nhất

Tuỳ thuộc vào mục đích, nhu cầu sử dụng và vấn đề cần giải quyết, ta cần linh hoạt sử dụng các đơn vị đo lường sao cho phù hợp.
