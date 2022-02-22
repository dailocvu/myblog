---
title: "CSS Cơ Bản: Grid Layout"
date: 2022-01-28
description: "Trong bài viết trước ta đã tìm hiểu về FlexBox, tuy nhiên ứng dụng web ngày nay giao diện ngày càng phức tạp nên việc chỉ sử dụng FlexBox thực sự vẫn chưa tối ưu, cần nhiều giải pháp hơn để tạo ra layout một cách nhanh và tối ưu nhất. Vì thế mà Grid Layout được sinh ra để giải quyết vấn đề này."
---

> Trong bài viết trước ta đã tìm hiểu về FlexBox, tuy nhiên ứng dụng web ngày nay giao diện ngày càng phức tạp nên việc chỉ sử dụng FlexBox thực sự vẫn chưa tối ưu, cần nhiều giải pháp hơn để tạo ra layout một cách nhanh và tối ưu nhất. Vì thế mà Grid Layout được sinh ra để giải quyết vấn đề này. Với Grid, ta có thể hiểu đơn giản là layout dưới dạng lưới.

![Grid](/images/grid1.png)

## Grid Layout là gì?

Ý tưởng chính đằng sau **Grid Layout** là chia trang web thành nhiều cột và hàng, cùng với khả năng chỉ định vị trí và kích thước của các building block element dựa trên kích thước, vị trí, và layer của hàng và cột ta đã tạo.

Một ví dụ đơn giản mà ta thường hay gặp là photo gallery, chứa nhiều bức ảnh bước sắp xếp dưới dạng lưới.
![Grid](/images/grid2.png)

Một ví dụ khác về layout của phần lớn các website hiện nay, ta cũng có thể nhận thấy chúng được hiển thị dưới dạng **Grid Layout**
![Grid](/images/grid3.png)

## Các thuật ngữ và thuộc tính quan trọng trong Grid Layout

### Định nghĩa một Grid

Để định nghĩa một **Grid**, đầu tiên ta cần một **container** và set cho nó **display: grid**, sau đó ta cần định nghĩa **số hàng** và **cột** mong muốn.
![Grid](/images/grid4.png)
Ví dụ, ta muốn tạo 1 **Grid** với kích thước **3x2**
![Grid](/images/grid5.png)
Ta có thể sử dụng **Inspect** và chọn tab **Layout** để xem thêm các tuỳ chọn hiển thị cho Grid và làm việc với chúng dễ dàng hơn.\
![Grid](/images/grid8.gif)\
Ta nhận thấy phần thông số các kích thước bị lặp lại, ta có thể sử dụng **repeat()** để tránh việc trùng lặp.
![Grid](/images/grid6.png)
Kết hợp với sử dụng shorthand.\
![Grid](/images/grid7.png)

### Căn chỉnh vị trí các Items

![Grid](/images/grid9.png)\
Các items ban đầu sẽ được căn chỉnh ở vị trí **top-left** trong ô của chúng. Nhưng ta có thể dễ dàng di chuyển chúng theo cách mình mong muốn, dọc theo trục ngang/dọc bằng cách sử dụng các thuộc tính: **justify-items** và **align-items**.
![Grid](/images/grid10.png)

### Justify Items

Căn chỉnh các items theo **trục ngang** (horizontal axis). Với nhiều các thuộc tính như: **start | center | end | flex-start | flex-end | baseline | stretch | ...** và nhiều những thuộc tính khác nữa, ta sẽ chỉ ví dụ một số trường hợp thường dùng.
![Grid](/images/grid11.png)

### Align Items

Tương tự như **justify-items**, nhưng **align-items** căn chỉnh các items theo **trục dọc** (vertical axis), với các thuộc tính tương tự.
![Grid](/images/grid12.png)

### Căn chỉnh vị trí Container

### Justify Content

Thuộc tính **justify-content** sẽ di chuyển toàn bộ khối **container** chứa các **items**, theo **trục ngang** (horizontal axis), với các thuộc tính như **start | center | end | stretch | space-around | space-between | space-evenly**.
![Grid](/images/grid13.png)

### Align Content

Thuộc tính **align-content** sẽ di chuyển toàn bộ khối **container** chứa các **items**, theo **trục dọc** (vertical axis), với các thuộc tính tương tự **justify-content**.
![Grid](/images/grid14.png)

### Đơn vị fr (fraction)

Trong một vài trường hợp, ta muốn kích thước của item tương ứng với tỉ lệ phần còn trống trong **container**, đó là lúc ta sử dụng đơn vị **fr**

Ta có ví dụ:
![Grid](/images/grid15.png)
Với đơn vị **fr**, các cột sẽ chiếm phần kích thước tương ứng **3 phần** và **7 phần** của khoảng không gian trống.\
Ta chú ý có đơn vị **auto**, khi ta thay đổi kích thước trình duyệt, hàng có kích thước **auto** sẽ tự động co giãn, trong khi các hàng vói kích thước tuyệt đối sẽ luôn cố định (100px).\
![Grid](/images/grid16.gif)

### Grid Gap

Thuộc tính này giúp chúng ta tạo khoảng cách giữa các phần tử với nhau theo cột và hàng. Bao gồm các thuộc tính: **row-gap | column gap | gap (shorthand)**.
![Grid](/images/grid17.png)
![Grid](/images/grid18.png)


### Placing Items

Bằng cách áp dụng các thuộc tính này cho các items, ta có thể kiểm soát chính xác vị trí nơi mà ta muốn đặt chúng.
![Grid](/images/grid19.png)
Giả sử ta có thuộc tính **grid-column** với giá trị **2** như bên dưới, ta chú ý thấy vị trí của **box-one** đã dịch chuyển qua vị trí thứ 2, và các items khác cũng tự động dịch chuyển sắp xếp theo chiều từ **top-left** đến **bottom-right**.
![Grid](/images/grid20.png)

Mặc định, item chỉ chiếm 1 cột, vậy nếu ta muốn item chiếm nhiều hơn 1 cột thì sao? Ta có thể dựa vào giá trị **line numbers** mà điều chỉnh kích thước mình mong muốn. Như trong ví dụ bên dưới, **box-one** được điều chỉnh kích thước chiếm hết hàng đầu, từ 1 - 3, hoặc dùng **span** để nêu rõ số lượng cụ thể. Hai cách dùng bên dưới tương đương nhau.
![Grid](/images/grid21.png)

Tương tự với **grid-row**
![Grid](/images/grid22.png)

### Bố cục Items dựa trên tên vị trí

Một cách cực kỳ hay và hữu ích cho phép chúng ta tạo bố cục layout một cách nhanh chóng, dễ dàng và đơn giản hơn nhiều, dựa vào cách đặt tên cho các vị trí.
![Grid](/images/grid23.png)
Như ví dụ bên dưới, ta set thuộc tính **grid-template-areas** cho **container** với các tên tuỳ chọn. Sau đó thiết lập **grid-area** cho các **items** tương ứng với tên mình mong muốn.
![Grid](/images/grid24.png)