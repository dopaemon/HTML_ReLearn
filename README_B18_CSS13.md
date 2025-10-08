### 3.3.2 Tạo nền chuyển sắc
Trong CSS, gradient là một dải màu, hay dải màu chuyển sắc. Chúng ta có thể sử dụng dải màu này để làm nền cho một phần tử HTML. Chúng ta gọi cái nền này là nền chuyển sắc.
Trước đây, để tạo một nền chuyển sắc cần sử dụng phần mềm xử lý ảnh (ví dụ Photoshop), lưu lại thành một hình ảnh, rồi chèn vào trang web. Tuy nhiên, hiện nay, CSS cho phép sử dụng chỉ dẫn để tạo nền chuyển sắc, trình duyệt sẽ dựa vào chỉ dẫn này để tạo ra nó. Nền chuyển sắc thực tế cũng là một hình ảnh. Một số thuộc tính có thể sử dụng để tạo nền chuyển sắc, như _background-image, border-image, list-style-image_. Chúng ta không thể thiết lập kích thước của nền chuyển sắc, mà nó tùy thuộc vào kích thước của phần tử HTML.
Có hai loại nền chuyển sắc:

– Nền chuyển sắc tuyến tính (linear gradient) là dải màu biến đổi theo đường thẳng

– Nền chuyển sắc tỏa tròn (radial gradient) là dải màu biến đổi theo hình tròn hoặc elip.

**Nền chuyển sắc tuyến tính**

Sử dụng từ khóa _linear-gradient()_ để tạo một nền chuyển sắc tuyến tính. Cần cung cấp ít nhất ba thông tin: thông tin đầu tiên là hướng chuyển màu, hướng này được xác định bằng góc quay (deg) hoặc từ khóa. Về góc quay, cả mặt phẳng sẽ là 360 độ, góc quay theo chiều kim đồng hồ sẽ có giá trị dương, và ngược chiều kim đồng hồ có giá trị âm. Ví dụ, 0deg ứng với hướng lên, 90deg ứng với hướng sang phải, 180deg ứng với hướng xuống dưới. Thông tin thứ hai và thứ ba là hai màu chặn (color stop), gồm màu chặn đầu và màu chặn cuối. Giá trị của màu chặn có thể là tên màu hoặc giá trị.

Ví dụ,
```css
_p {_
    _width: 300px;    height: 100px;    padding: 20px;_
    _background-image: linear-gradient(90deg, yellow, green);_
  _}_
```
Với một số góc đặc biệt của hướng chuyển màu, có thể dùng từ khóa để thay thế, ví dụ _to top_ (ứng với 0deg)_, to right_ (ứng với 90deg)_, to bottom_ (ứng với 180deg)_, to left_ (ứng với 270deg).

Ví dụ,

    `background-image: linear-gradient(to right, yellow, green);`

Ví dụ sau là một nền chuyển sắc từ trái qua phải, gồm ba màu chặn, màu thứ hai nằm ở vị trí 50% của đường thẳng (lưu ý: vị trí của màu được viết ngay sau tên màu), nếu màu chặn tại vị trí 0% và 100% thì không cần khai báo vị trí,
```css
_p {_
    _width: 300px;    height: 100px;    padding: 20px;_
    _background-image: linear-gradient(to right, yellow, red 50%, green);_
  _}_
```
Ví dụ, tạo nền chuyển sắc 3-D,
```css
p {
    width: 300px;    height: 100px;    padding: 20px;
    background-image: linear-gradient(to bottom, #e2e2e2 0%, #dbdbdb 50%, #d1d1d1 51%, #fefefe 100%);
  }
```
Hình sau là một số nền chuyển sắc theo đường thẳng,

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQSJfvugq91d4W3DlMJKh5tg6VMWKz92EYrNmv6wSZnVYEgjczXflKQGI4gT7d6ylXZ_rB2BD83XomV5ro9f-ghGWsLw48604-LHhnUG3G4Jr_-USBs_ADh0_O1RnHRUwE09l6PPFmU72c82-qBNY8uKiGUfcsEbrYbGcQ1TG-tyh_wPlu95OsnRhKFQ4/w400-h315/tao%20nen%20chuyen%20sac.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQSJfvugq91d4W3DlMJKh5tg6VMWKz92EYrNmv6wSZnVYEgjczXflKQGI4gT7d6ylXZ_rB2BD83XomV5ro9f-ghGWsLw48604-LHhnUG3G4Jr_-USBs_ADh0_O1RnHRUwE09l6PPFmU72c82-qBNY8uKiGUfcsEbrYbGcQ1TG-tyh_wPlu95OsnRhKFQ4/s647/tao%20nen%20chuyen%20sac.jpg)

  

**Nền chuyển sắc tỏa tròn**

Như ở phần trên đã đề cập, nền chuyển sắc tỏa tròn là một dải màu biến đổi theo hình tròn hoặc hình elip. Để hiểu rõ về cách CSS tạo ra dải màu này, chúng ta cùng quan sát các thành phần của một nền chuyển sắc tỏa tròn ở hình sau:

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7cjpsIJmGgL3mGU2yByBPoglFw5ArlWkcoUi0am3E4IoKo4xxgExnbgYDaRsLHkEE8JQQ3OZrxinhefAlP6odMjLA4LZYVa-nT-x2UEOG5oRFT4Bxk0QyVb5iCB4dVzOZ7k3dJNH-hHRKL-h8Sl4e7794bLC1eiBkioWoOLwi9lNBiTaUYGvogWIJxfM/w400-h236/chuyen%20sac%20toa%20tron.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7cjpsIJmGgL3mGU2yByBPoglFw5ArlWkcoUi0am3E4IoKo4xxgExnbgYDaRsLHkEE8JQQ3OZrxinhefAlP6odMjLA4LZYVa-nT-x2UEOG5oRFT4Bxk0QyVb5iCB4dVzOZ7k3dJNH-hHRKL-h8Sl4e7794bLC1eiBkioWoOLwi9lNBiTaUYGvogWIJxfM/s701/chuyen%20sac%20toa%20tron.jpg)

Một nền chuyển sắc tỏa tròn được tạo ra bằng các thành phần sau: một điểm làm tâm (Tâm điểm - center point), một Đường giới hạn của vùng chuyển sắc (ending shape) và hai hoặc nhiều Màu chặn cùng với vị trí của nó (color-stop point).

Để tạo ra một nền chuyển sắc tỏa tròn, trình duyệt sẽ vẽ hàng loạt các đường tròn đồng tâm, với màu thay đổi từ Tâm điểm ra tới Đường giới hạn (cũng có thể vượt ra khỏi đường này). Đường giới hạn có hai loại, là đường tròn (circle) và đường elip (elipse).

Các vị trí của Màu chặn sẽ được đặt trên Tia chuyển sắc ảo (virtual gradient ray), đây là một tia nằm ngang có gốc là Tâm điểm, hướng từ trái sang phải. Giá trị của các vị trí được tính theo %, với 0% là Tâm điểm, 100% là giao điểm của Đường giới hạn và Tia chuyển sắc ảo.

Trong CSS, sử dụng từ khóa _radial-gradient()_ để tạo một nền chuyển sắc tỏa tròn.

Đây là cú pháp:

`_radial-gradient(shape size_ at _position, start color, …, last color)_`

Ví dụ một chỉ dẫn CSS có sử dụng _radial-gradient_ dạng đơn giản nhất, chỉ gồm 2 màu chặn:
```css
  p {
    width: 300px; height: 100px; padding: 20px;
    background-image: radial-gradient(yellow, green);
  }
```
Chúng ta cùng tìm hiểu về các tham số trong cú pháp của _radial-gradient_:

– _shape_: loại Đường giới hạn, là đường tròn hoặc đường elip, mặc định là đường elip

Ví dụ, Đường giới hạn là đường tròn,

`background-image: radial-gradient(circle, yellow, green);`

– _position_: vị trí của Tâm điểm, nếu không khai báo tường minh, mặc định là ở giữa (center), tuy nhiên, có thể thay đổi bằng các giá trị giống như thuộc tính _background-position_,

Ví dụ, thiết lập giá trị Tâm điểm là 80%, 20%, (để ý: có thêm từ khóa _at_)

_`background-image: radial-gradient(circle at 80% 20%, yellow, green)`_

– _size_: khi đã có Tâm điểm, giá trị _size_ sẽ xác định kích thước vùng chuyển sắc dựa vào tương quan giữa Đường giới hạn và Đường viền của đối tượng chứa nó, giá trị _size_ là các từ khóa sau:

_closest-side_: tạo ra vùng chuyển sắc, sao cho đường Giới hạn sẽ tiếp xúc với Đường viền gần nhất của phần tử chứa nó

_closest-corner_: tạo ra vùng chuyển sắc, sao cho đường Giới hạn sẽ tiếp xúc với góc gần nhất của phần tử chứa nó

_farthest-side_: tạo ra vùng chuyển sắc, sao cho đường Giới hạn sẽ tiếp xúc với Đường viền xa nhất của phần tử chứa nó

_farthest-corner_: tạo ra vùng chuyển sắc, sao cho đường Giới hạn sẽ tiếp xúc với góc xa nhất của phần tử chứa nó

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgs6hHf6XQHJ5VHmSZ-FnQSqcuh2NILctgxQlU3DrED0jynBVPKCY6NfA9TYq9gFOVw_GwWRFabyrynxBtTs7yIrUOk_SeJ5LMl4VIHIeKVBpj1ie7p_1l45gStyZKA8tnzteqXP2HzNc0gSCXLG7i6HMmcrhzrlI-ZWFzHT8zPL-VNvBVuF56g_JO2Dis/w400-h294/gia%20tri%20size.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgs6hHf6XQHJ5VHmSZ-FnQSqcuh2NILctgxQlU3DrED0jynBVPKCY6NfA9TYq9gFOVw_GwWRFabyrynxBtTs7yIrUOk_SeJ5LMl4VIHIeKVBpj1ie7p_1l45gStyZKA8tnzteqXP2HzNc0gSCXLG7i6HMmcrhzrlI-ZWFzHT8zPL-VNvBVuF56g_JO2Dis/s701/gia%20tri%20size.jpg)

– _các màu chặn_ (start color, last color): các màu chặn được viết theo thứ tự từ Tâm điểm trở ra, đi sau các màu chặn có thể bao gồm giá trị cho biết độ dày của dải màu

Ví dụ, dải màu vàng dày 10%,

  p {

    width: 300px; height: 100px; padding: 20px;

    background-image: radial-gradient(circle, yellow 10%, green)

  }

Ví dụ, dải màu vàng dày 50%,

p {

    width: 300px; height: 100px; padding: 20px;

    background-image: radial-gradient(circle, yellow 50%, green)

  }

Xem hình minh họa,

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjy3d032NF1JSuv0dpXpBr5jw86lHXFGkqjeLRV8pnR6gOkTc-PFpML4rEk3Oq39c_cYDi6K_i9RCVCbf17JFugunG214HyN2OguUYirSec0NPCM2kgWVWcUb6Txq7N9iOjRdP4ssL8ktFwDbi0frjkG2PquftW_aj8GCFXFzTO86ZCoTKQFiB0D3i8nEA/w400-h219/dai%20mau.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjy3d032NF1JSuv0dpXpBr5jw86lHXFGkqjeLRV8pnR6gOkTc-PFpML4rEk3Oq39c_cYDi6K_i9RCVCbf17JFugunG214HyN2OguUYirSec0NPCM2kgWVWcUb6Txq7N9iOjRdP4ssL8ktFwDbi0frjkG2PquftW_aj8GCFXFzTO86ZCoTKQFiB0D3i8nEA/s700/dai%20mau.jpg)

Nếu bạn muốn lặp lại nền chuyển sắc, sử dụng thêm từ “repeating-…” như sau:

_repeating-linear-gradient(to bottom, white, silver 30px);_

### 3.3.3      Tương thích với các trình duyệt

Ở phần trên, chúng ta đã tìm hiểu về tạo nền chuyển sắc, tuy nhiên, đó là các đặc tả của CSS. Thực tế, trước khi có một đặc tả thống nhất, các trình duyệt đã tự tạo ra các xử lý riêng cho chức năng này. Vì vậy, để có được nền chuyển sắc tốt nhất trên các trình duyệt khác nhau, nên sử dụng thêm các tiếp đầu ngữ (prefix) để chỉ ra đoạn mã đó là của trình duyệt nào.

Bảng sau là một số tiếp đầu ngữ ứng với mỗi trình duyệt,

**_Tiếp đầu ngữ_**

**_Công ty/Tổ chức_**

**_Trình duyệt_**

-ms-

Microsoft

Internet Explorer

-moz-

Mozilla Foundation

Firefox, Camino, Seamonkey

-o-

Opera Software

Opera, Opera Mini, Opera Mobile

-webkit-

Apple, mã nguồn mở

Safari, Chrome, Android, Silk, Blackberry, WebOS,…

Khi có thêm tiếp đầu ngữ, việc viết mã sẽ vất vả hơn. Ví dụ sau đây là đoạn mã để tạo ra một nền chuyển sắc có tính tương thích với nhiều trình duyệt:
```css
background: #ffff00; /* Old browsers */
background: -moz-linear-gradient(top, #ffff00 0%, #00ff00 100%);
/* FF3.6+ */
background: -webkit-gradient(linear, left top, left bottom, colorstop(
0%,#ffff00), color-stop(100%,#00ff00));
/* Chrome,Safari4+ */
background: -webkit-linear-gradient(top, #ffff00 0%,#00ff00 100%);
/* Chrome10+,Safari5.1+ */
background: -o-linear-gradient(top, #ffff00 0%,#00ff00 100%);
/* Opera 11.10+ */
background: -ms-linear-gradient(top, #ffff00 0%,#00ff00 100%);
/* IE10+ */
background: linear-gradient(to bottom, #ffff00 0%,#00ff00 100%);
/* W3C */
filter: progid:DXImageTransform.Microsoft.gradient(
startColorstr=’#ffff00’, endColorstr=’#00ff00’,GradientType=0 );
/* IE6-9 */
```
Để viết đoạn mã trên quả là phức tạp, và mất nhiều thời gian, rất may là trên mạng hiện nay cũng có những công cụ giúp tự động tạo ra các đoạn mã như vậy. Có thể sử dụng trang web sau:

[http://www.colorzilla.com/gradient-editor/](http://www.colorzilla.com/gradient-editor/)

### 3.3.4       Viết CSS ở tập tin riêng

Như đã biết, có ba cách để gắn (hay áp) các chỉ dẫn CSS vào tài liệu HTML, gồm: gắn bằng thuộc tính _style_, gắn bằng phần tử _style_ và gắn bằng phần tử _link_; tương ứng với ba vị trí đặt mã CSS, đặt ở trong phần tử HTML, đặt trong tài liệu HTML và đặt ngoài tài liệu HTML. Các phần trước, chúng ta đã tìm hiểu hai cách đầu, phần này sẽ tìm hiểu cách thứ ba, đó là viết CSS ở ngoài tài liệu HTML, hay nói cách khác là viết CSS ở tập tin riêng.

Viết CSS ở tập tin riêng được khuyến khích sử dụng vì nó có nhiều ưu điểm. Ví dụ, nhờ viết mã định dạng cho trang web ở một nơi duy nhất, nên để thay đổi định dạng cho toàn bộ trang web, chỉ cần thực hiện ở một nơi; ngoài ra, do mã CSS tách biệt với mã HTML nên mã nguồn của trang web sẽ rõ ràng, dễ đọc, dễ bảo trì; tăng tốc độ hiển thị nội dung trang web.

Mã CSS là một tài liệu chứa văn bản thô (plain text), trong đó phải có ít nhất một chỉ dẫn CSS, không chứa mã HTML, có thể chứa các chú thích theo cú pháp của CSS. Tập tin chứa mã CSS có phần mở rộng là _.css_.

Để chú thích trong CSS, sử dụng kí hiệu: _/* nội dung của chú thích */_

Xem hình minh họa một đoạn mã CSS, để ý cách viết khoảng trắng, xuống hàng, dấu ngoặc,

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhverSKnMp3Dz8WD-n8At2yjh_MmkjdxKe_jQ-khqTbwvsx7KCefXihBWofDCEaFczoms9-VILZbz1oJBjNsQF-ips62Jwlua3e08C-hYdGU3HBILw_-HHq6IF2IbZOkX8DFM_ydd3636Q7P8-MPV_YIL5-GwrVGWRdRTpWU7sR7eQAy9k6B0KHKKBOuHE/w400-h269/ma%20css.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhverSKnMp3Dz8WD-n8At2yjh_MmkjdxKe_jQ-khqTbwvsx7KCefXihBWofDCEaFczoms9-VILZbz1oJBjNsQF-ips62Jwlua3e08C-hYdGU3HBILw_-HHq6IF2IbZOkX8DFM_ydd3636Q7P8-MPV_YIL5-GwrVGWRdRTpWU7sR7eQAy9k6B0KHKKBOuHE/s703/ma%20css.jpg)

Do mã CSS được viết ở tập tin riêng, vì vậy để mã CSS có thể tác động lên mã HTML thì phải tạo liên kết giữa tài liệu HTML và mã CSS. Có hai cách để tạo liên kết này, một là sử dụng phần tử _link_ của HTML, hai là sử dụng chỉ dẫn _import_ của CSS.

**Sử dụng phần tử link**

Trong tài liệu HTML, để tạo liên kết tới tập tin _.css_, sử dụng phần tử _link_ trong _head_. Đây là phương pháp được sử dụng phổ biến nhất.

 Ví dụ,
```html
<head>

<title>Titles are required</title>

<link rel="stylesheet" type="text/css" href="/path/stylesheet.css">

</head>
```
Ý nghĩa các thuộc tính của phần tử _link_,
– _rel="stylesheet"_: cho biết mối liên hệ giữa tài liệu hiện tại (HTML) và tài liệu được liên kết đến (CSS), _rel_ là viết tắt của relationship, mối liên hệ ở đây là “mã định dạng” (stylesheet).
– _type="text/css"_: cho biết loại tài liệu được liên kết đến, ở đây là một tài liệu CSS
– _href="/path/stylesheet.css"_: đường dẫn tới tập tin _.css_, đường dẫn được bắt đầu từ thư mục gốc của website (“/”).
Trong một tài liệu HTML, có thể sử dụng nhiều phần tử _link_ để liên kết tới nhiều tập tin ._css_ khác nhau, khi đó tất cả các chỉ dẫn trong các tập tin _.css_ đều được áp dụng, nếu có xung đột, chỉ dẫn nào nằm trong tập tin _.css_ được liên kết sau sẽ có quyền ưu tiên cao hơn.
**Sử dụng chỉ dẫn import**
Đây là cách thứ hai để tạo sự kiên kết giữa tài liệu HTML và CSS. Vì _import_ là một chỉ dẫn của CSS nên nó phải được đặt trong phần tử _style_, hoặc đặt trong một tập tin _.css_.
Ví dụ, đặt trong phần tử style,
```html
<head>
<style>
@import url("/path/stylesheet.css");
p { font-face: Verdana;}
</style>
<title>Titles are required.</title>
</head>
```
Lưu ý: chỉ dẫn _import_ phải nằm trước mọi bộ chọn CSS, có thể sử dụng nhiều chỉ dẫn _import_ để liên kết tới nhiều tập tin _.css_, tập tin _.css_ được _import_ sau sẽ có độ ưu tiêu cao hơn.

**Chia nhỏ mã CSS vào nhiều tập tin**

Vì có thể kết hợp mã CSS ở nhiều tập tin khác nhau bằng chỉ dẫn _import_, hoặc liên kết tới nhiều tập tin _.css_ bằng phần tử _link_, nên chúng ta có thể tách mã CSS thành nhiều tập tin để có thể sử dụng lại. Ví dụ, lập trình viên có thể tách mã CSS theo chức năng như sau: CSS về trình bày văn bản (typography), CSS về bố cục (layout), CSS về form.

Ví dụ, khi muốn sử dụng lại, chúng ta sẽ sử dụng chỉ dẫn import,

Nội dung của tập tin _clientsite.css:_
```css
/* basic typography */
@import url("type.css");
/* form inputs */
@import url("forms.css");
/* navigation */
@import url("list-nav.css");
/* site-specific styles */
body { background: orange; }
```

…các chỉ dẫn CSS khác…
