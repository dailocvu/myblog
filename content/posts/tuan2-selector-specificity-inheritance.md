---
title: "[Tuần 2] CSS Cơ Bản: Selectors - Cascade/Specificity - Inheritance"
date: 2022-01-24
description: "Sau khi tìm hiểu về Box Model, ta bắt đầu với các khái niệm của CSS, tìm hiểu về các Selectors, để có thể chọn được thẻ mà mình mong muốn, cũng như về hệ thống phân cấp, tính kế thừa của chúng."
---

> Sau khi tìm hiểu về Box Model, ta bắt đầu với các khái niệm của CSS, tìm hiểu về các Selectors, để có thể chọn được thẻ mà mình mong muốn, cũng như về hệ thống phân cấp, tính kế thừa của chúng.

## Selectors là gì?

Như bạn biết trong một file HTML, có rất nhiều thẻ, cũng như các ID, class cho các thẻ để phân biệt, vậy trong CSS khi ta muốn truy xuất tới các phần tử này để styling, ta cần sự trợ giúp của các Selectors.

Ta có thể chia CSS Selectors thành các loại sau:\
**- Selector cơ bản:** Dựa trên các thẻ, ID, class, thuộc tính,..\
**- Selector kết hợp:** Dựa trên mối liên hệ giữa các thẻ HTML.\
**- Selector nhóm:** Dựa trên sự giống nhau về style giữa các thẻ HTML.\
**- Pseudo Selector:** Các Selectors cho các thuộc tính đặc biệt.

### 1. Selector cơ bản

![Selector](/images/selector1.png)

### 2. Selector kết hợp

![Selector](/images/selector2.png)

### 3. Selector nhóm

![Selector](/images/selector3.png)

### 4. Pseudo Selector

**Pseudo-classes:** :link, :visited, :hover, :active, :focus,...\
**Pseudo-elements:** ::before, ::after,...
![Selector](/images/selector4.png)

## Cascade/Specificity trong CSS

### Specificity

Trong nhiều trường hợp, một thẻ HTML có thể được trỏ tới bởi các Selector khác nhau, đôi khi có thể gây xung đột trong việc styling. Vậy làm cách nào trình duyệt biết được cái nên được ưu tiên?

Selectors có thứ hạng cấp bậc các thành phần sẽ được ưu tiên. Nếu nhiều thuộc tính CSS xung đột với nhau, Selector ở cấp bậc cao hơn sẽ được áp dụng.\
**1. ID Selectors**\
**2. Class, Pseudo Class Selectors, Atribute Selectors**\
**3. Element Selector**
![Specific](/images/specific.png)

Vậy nếu có hai Selectors hạng tương đương nhau thì sao? **Selector được thiết lập sau sẽ được áp dụng (theo thứ tự)**
![Specific](/images/next.png)

Trong VS Code, khi ta hover vào một Selector, một bảng **Selector Specificity** sẽ được hiển thị, với 3 chữ số ngăn cách nhau bởi dấu phẩy. Ta có thể dùng nó để so sánh mức độ ưu tiên, tương tự như cách so sánh theo số học với hàng **trăm - chục - đơn vị**. Selectors nào có số lớn hơn - độ ưu tiên lớn hơn.\
![Specific](/images/info.png)

### Cascade

Như ta đã biết, CSS là viết tắt của **Cascading Style Sheets**, trong đó "Cascading" có nghĩa là "Xếp tầng". Nhờ cơ chế "Cascading" trong CSS, ta có thể xác định được mức độ quan trọng của các nguồn CSS mà ta sử dụng.

![Cascade](/images/cascade.webp)\
Có 3 nguồn của Style Sheets mà CSS quy định, được xếp theo thứ tự độ ưu tiên tăng dần:

**User Agent Styles:** Đây là những CSS mặc định mà các trình duyệt đặt sẵn, nếu như file HTML của bạn không được style bằng CSS, nó sẽ vẫn có một vài style mặc định\
**User Styles:** Một vài người dùng sẽ có các Style Custom được cài đặt cho cá nhân họ, những style này chỉ áp dụng cho bản thân người dùng đó và nó được cài dưới dạng local.\
**Author Styles:** Đây là CSS do chúng ta - những developer viết.

## Inheritance

Thêm một khái niệm quan trọng nữa trong CSS mà ta cần quan tâm, Inheritance, tức sự kế thừa.

Kế thừa trong CSS giúp giảm đáng kể thời gian và công sức cần thiết để tạo một trang web. Hãy tưởng tượng bạn sẽ phải viết bao nhiêu CSS để đặt màu trên tất cả các phần tử con của thẻ body. Điều này sẽ tốn thời gian, dễ xảy ra lỗi và khó bảo trì.

Một vài thuộc tính CSS sẽ mặc định được kế thừa tư thẻ cha mẹ của chúng.

**Style sẽ được kế thừa**\
Các thuộc tính CSS được kế thừa thường liên quan tới text styling. Ví dụ như font, color, size, text align,...\
Trường hợp dưới đây, thẻ **p** được kế thừa màu chữ từ thẻ **body**.\
![Inherit](/images/inherit1.png)

**Style sẽ không được kế thừa**\
Trong khi đó, các thuộc tính CSS không được kế thừa thường liên quan tới trang trí. Trong trường hợp bên dưới, thuộc tính **border** không thể kế thừa từ thẻ cha, tưởng tưởng bạn đặt **border** cho một thẻ và tất cả các thẻ con đều kế thừa thuộc tính này thì quả là không dễ chịu.

Nói chung, việc thuộc tính có thể kế thừa được hay không là do CSS quy định. Nhưng thay vào đó, tùy vào trường hợp sử dụng mà bạn muốn kế thừa một thuộc tính nào đó khác, ta vẫn có thể ép các thuộc tính này được kế thừa, nhờ sử dụng **inherit**
![Inherit](/images/inherit2.png)
