  

### CSS (10) - Định dạng màu
\-----

3         Định dạng màu & nền
=============================

Trong phần này, chúng ta sẽ tìm hiểu các kiến thức, thuộc tính liên quan đến định dạng màu sắc (color) và định dạng nền (background) cho một trang web. Đồng thời, tìm hiểu thêm một số bộ chọn mới.

3.1       Định dạng màu
-----------------------

### 3.1.1       Xác định màu

Có hai cách phổ biến để xác định một màu, một là dùng các tên màu định sẵn và hai là dùng giá trị số (mỗi màu có một giá trị số tương ứng).

**Tên màu**

Cách trực quan nhất để xác định một màu là dùng tên của nó. Tất nhiên, lập trình viên không thể sử dụng các tên màu tùy ý, mà chỉ được sử dụng các tên màu đã được đặc tả sẵn trong CSS. CSS3 hỗ trợ 140 tên màu.

Ví dụ, một chỉ dẫn CSS có dùng tên màu:

p { color: gray; } /\* văn bản trong p sẽ có màu xám \*/

Xem hình minh họa một số tên màu:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEjzKIfi8qd6ud4Ak87F2x6I504LwNYWy9dsrqwN9lIQAFW60HxFOCrPcnIuynZQptE74FgYa7j7rIEDVPR_vXQbmRWVqbKAdlNkwtMBj2y7rIqdxyYBzmc87orL1OIcU1MIC8Uxkpj5rwNy5yPZk7D1szxV07njpYNvATvT8kofMqZNeoDzUggu2iYx=w400-h245)](https://blogger.googleusercontent.com/img/a/AVvXsEjzKIfi8qd6ud4Ak87F2x6I504LwNYWy9dsrqwN9lIQAFW60HxFOCrPcnIuynZQptE74FgYa7j7rIEDVPR_vXQbmRWVqbKAdlNkwtMBj2y7rIqdxyYBzmc87orL1OIcU1MIC8Uxkpj5rwNy5yPZk7D1szxV07njpYNvATvT8kofMqZNeoDzUggu2iYx)

  

Xem thêm các tên màu tại địa chỉ: [https://www.w3schools.com/colors/colors\_names.asp](https://www.w3schools.com/colors/colors_names.asp)

**Giá trị số**

Xác định màu bằng tên tuy đơn giản nhưng lại bị giới hạn về số lượng. Vì vậy, mọi người hay sử dụng giá trị số để xác định một màu, đó là giá trị RGB. Với RGB, chúng ta có thể xác định hàng triệu màu khác nhau.

Ngoài hệ màu RGB, CSS cũng hỗ trợ hệ màu HSL. Tuy nhiên, do tính phổ biến và được trình duyệt hỗ trợ tốt hơn, nên phần này sẽ chỉ tập trung tìm hiểu hệ màu RGB.

**_Hệ màu RGB_**

Máy tính tạo ra các màu khác nhau bằng cách kết hợp ba màu cơ bản (với tỉ lệ nhất định) là: đỏ (red), xanh lá cây (green) và xanh da trời (blue). Tên gọi RGB là viết tắt của ba chữ Red, Green và Blue.

Mỗi chỉ số trong tổ hợp RGB có giá trị nằm trong khoảng từ 0 tới 255. Nếu ba chỉ số có giá trị là 0, chúng ta sẽ có màu đen (black). Nếu ba chỉ số đều có giá trị là 255, chúng ta sẽ có màu trắng (white).

Như vậy, mọi điểm màu trên màn hình đều được mô tả bằng bộ ba giá trị RGB, ví dụ màu lavender sẽ có bộ ba giá trị là (200, 178, 230).

Xem hình minh họa về hệ màu RGB,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEgzD4Pw0giFgIXQeyunG1-YnkRGSCCQUdhlMLK-NkSFQn4q8KuRW3hrmyiFsV86PmR8XLg7qzunpY7N5VInaQPgfC3MLaalsgk5ZG6Jv5nZzPQUk7gyY3xT9tH2zAW4D5EWOwgs271CXrCiThi8w2_H_P8YIiGRr_scheV6xqy_4bl97RsVljpvDpqm=w400-h168)](https://blogger.googleusercontent.com/img/a/AVvXsEgzD4Pw0giFgIXQeyunG1-YnkRGSCCQUdhlMLK-NkSFQn4q8KuRW3hrmyiFsV86PmR8XLg7qzunpY7N5VInaQPgfC3MLaalsgk5ZG6Jv5nZzPQUk7gyY3xT9tH2zAW4D5EWOwgs271CXrCiThi8w2_H_P8YIiGRr_scheV6xqy_4bl97RsVljpvDpqm)

  

**Lấy màu**

\[Cách 1\] Cách dễ nhất để lấy được giá trị RGB của một màu là dùng công cụ có tên là Color Picker. Bạn hãy vào trang Google, tìm kiếm và học cách sử dụng công cụ này.

\[Cách 2\] Cách khác để lấy giá trị màu là dùng Developer tools.

Nếu chúng ta muốn lấy một màu có sẵn trên một trang web nào đó (sao chép màu), ví dụ lấy màu của các chữ cái google, thì làm như sau:

– Mở trang google.com

– Mở công cụ Developer tools của trình duyệt

[![](https://blogger.googleusercontent.com/img/a/AVvXsEj4eDDtstVAb8gxrqWOtknRpFT-KWsuCx8JmRmTewW0xHCQYYvDt_8jSC74KSOb6pyvBXaztFhrXD1F7OjYPKJgW4uFQk70Qxridp0XY0KK4UHidt0RAXSClCWg23YGmtL6S5_ugL2om4KIVNqlvyXZ58W9AqIwqQVsjEKm1x3Tq7NCEdAyqXdpDwuf=w400-h274)](https://blogger.googleusercontent.com/img/a/AVvXsEj4eDDtstVAb8gxrqWOtknRpFT-KWsuCx8JmRmTewW0xHCQYYvDt_8jSC74KSOb6pyvBXaztFhrXD1F7OjYPKJgW4uFQk70Qxridp0XY0KK4UHidt0RAXSClCWg23YGmtL6S5_ugL2om4KIVNqlvyXZ58W9AqIwqQVsjEKm1x3Tq7NCEdAyqXdpDwuf)

  

– Trong tab Elements/Styles \[1\], nhập một chỉ dẫn CSS có thuộc tính color, giá trị là một màu bất kì, ví dụ _color: red \[2\],_ bấm chuột trái vào ô vuông màu đỏ sau chữ _color_

– Bấm chuột vào công cụ soi màu (eye droper) \[3\]

– Di chuyển công cụ soi màu vào vùng màu cần lấy \[4\], bấm chuột trái để lấy màu

– Lấy giá trị màu dạng HEX \[5\], dạng RGB \[6\]

Ngoài ra, chúng ta có thể sử dụng các công cụ xử lý ảnh để lấy màu, như Photoshop, Illustrator.  

**Cách viết giá trị màu RGB**

Có ba cách để viết giá trị màu RGB trong CSS, một là dùng giá trị hệ 10, hai là dùng %, ba là dùng giá trị hệ 16.

**_Dùng giá trị hệ 10_**

Bắt đầu là kí hiệu _rgb_, sau đó là ba giá trị hệ 10 của ba màu cơ bản (RGB), mỗi giá trị nằm trong khoảng từ 0 tới 255, ví dụ,

color: rgb(200, 178, 230);

**_Dùng giá trị %,_**

Bắt đầu là kí hiệu _rgb_, sau đó là ba giá trị % của ba màu cơ bản, giá trị % được tính bằng cách lấy “giá trị hệ 10”/255\*100%, ví dụ,

color: rgb(78%, 70%, 90%);

**_Dùng giá trị hệ 16_**

Bắt đầu là kí hiệu #, sau đó là ba giá trị hệ 16 của ba màu cơ bản, mỗi giá trị màu được biểu diễn bằng hai kí số hệ 16, ví dụ,

color: #C8B2E6;

Trong trường hợp giá trị của mỗi màu cơ bản là hai kí số giống nhau thì có thể viết rút gọn, ví dụ,

color: #FFCC00 hoặc color: #993366

thì có thể viết rút gọn thành,

color: #FC0 hoặc color: #936

Xem hình minh họa về giá trị màu hệ 16,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEgXEuYmV8MZQHaeRg6AMtpd3KIXQGmX5rY4rZ5T67AlhnCcNV5IIEFFuOjB1mi9uyWZ_fP2_9gATSDPYBTLZBDavlJw4HWiTY-gcYw78-f2UAeGOxnvsbGW9qAcEOl5xHFVjqGxxv4edNgK9tnakHbS0E7aUxsn5Mrf7lAmuWKqI8_nfkRrmWMEiQW1=w400-h214)](https://blogger.googleusercontent.com/img/a/AVvXsEgXEuYmV8MZQHaeRg6AMtpd3KIXQGmX5rY4rZ5T67AlhnCcNV5IIEFFuOjB1mi9uyWZ_fP2_9gATSDPYBTLZBDavlJw4HWiTY-gcYw78-f2UAeGOxnvsbGW9qAcEOl5xHFVjqGxxv4edNgK9tnakHbS0E7aUxsn5Mrf7lAmuWKqI8_nfkRrmWMEiQW1)

  

**Màu RGBa**

Màu _RGBa_ cho phép xác lập một màu bất kì cùng với độ mờ của màu. Chữ _a_ là viết tắt của _alpha_, được sử dụng để thiết lập độ mờ của màu, nếu _a_ có giá trị 0: tương ứng với màu trong suốt hay mờ nhiều nhất (transparent), nếu _a_ có giá trị 1: tương ứng với màu ít mờ nhất hay đậm đặc nhất (opaque).

Ví dụ, xem hình minh họa,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEhbtwjawFjny_0HaIo_Ff0pVutYNr1gCUYK3yar9hmBUjxOPbDyUpjzqp-rA4_mVM62qKy5ciQonmM-_8kw9Ij786BQM1QZgDbSpBvcWB7hT6lSlaN5YVEkPgStBPJne_n1TF7OSpNd1fW0Bo27iPU_rnOHaWur1YrsKr0vssIVS2Y0QAaAetjawNl6=w400-h140)](https://blogger.googleusercontent.com/img/a/AVvXsEhbtwjawFjny_0HaIo_Ff0pVutYNr1gCUYK3yar9hmBUjxOPbDyUpjzqp-rA4_mVM62qKy5ciQonmM-_8kw9Ij786BQM1QZgDbSpBvcWB7hT6lSlaN5YVEkPgStBPJne_n1TF7OSpNd1fW0Bo27iPU_rnOHaWur1YrsKr0vssIVS2Y0QAaAetjawNl6)

  

### 3.1.2       Màu chữ & màu nền

**Màu chữ**

Chúng ta có thể thiết lập màu chữ (foreground color) cho mọi phần tử HTML. Khi thiết lập màu chữ, màu đường viền (border) cũng được thiết lập. Để thiết lập màu chữ, sử dụng thuộc tính _color_.

Thuộc tính co_lor_:

– Giá trị: _giá trị màu (tên hoặc số)_

– Mặc định: _tùy trình duyệt và thiết lập của người dùng_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _có_

Ví dụ, chỉ dẫn CSS sau sẽ thiết lập màu chữ xanh nhạt cho phần tử _blockquote_, với các giá trị R:80, G:140 và B:25, đổi giá trị này sang hệ 16 sẽ là #508C19. Hai phần tử _p_ và _em_ là hậu duệ của phần tử _blockquote_ nên cũng được kế thừa màu vừa thiết lập.

```html

<blockquote>

  <p>Đây là ví dụ về màu chữ <em>(foreground color)</em></p>

</blockquote>
```
```css

  blockquote {

      border: 4px dashed;

      color: #508C19;

    }
```
\[Kết quả\]

[![](https://blogger.googleusercontent.com/img/a/AVvXsEh54can7DB7dVYbM_kgLu7_1pnWuCMJa8BMwsXQV0_-9hXS4_wItc5CRyZceBfbWh2NSfmZeXr62VOZLTulIKdrUBE7GAK4nAdWX6uzcVOXHDpM_09e_gKzKpQtZpIXk84WnM2ci0EcAiqCkVRhhWlEnbdSuzxg1MzTZh0FVQMXzFMh-B5wGJi2aOAB=w400-h103)](https://blogger.googleusercontent.com/img/a/AVvXsEh54can7DB7dVYbM_kgLu7_1pnWuCMJa8BMwsXQV0_-9hXS4_wItc5CRyZceBfbWh2NSfmZeXr62VOZLTulIKdrUBE7GAK4nAdWX6uzcVOXHDpM_09e_gKzKpQtZpIXk84WnM2ci0EcAiqCkVRhhWlEnbdSuzxg1MzTZh0FVQMXzFMh-B5wGJi2aOAB)

  

Nếu thuộc tính _border-color_ cũng được thiết lập thì nó sẽ thay thế màu của đường viền đang được thiết lập bằng thuộc tính _color_. Nghĩa là thuộc tính _border-color_ có độ ưu tiên cao hơn thuộc tính _color_.

**Màu nền**

Sử dụng thuộc tính _background-color_ để thiết lập màu nền cho các phần tử HTML.

Thuộc tính _background-color_:

– Giá trị: _giá trị màu (tên hoặc số) | transparent_

– Mặc định: _transparent (trong suốt)_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Khung nền (background, hoặc canvas) bao gồm: vùng chứa nội dung, khoảng đệm phía trong đường viền (padding), nền chứa đường viền, không bao gồm vùng đệm phía ngoài đường viền (margin).

Mặc định, thuộc tính _background-color_ sẽ đổ màu cho toàn bộ phần khung nền, hay được gọi tắt là nền.

Ví dụ, định dạng màu nền cho phần tử _blockquote_,
```css
    blockquote {

      border: 4px dashed;

      color: #508C19;

      background-color: #B4BDE6;

    }
```
\[Kết quả\]

[![](https://blogger.googleusercontent.com/img/a/AVvXsEht5S-kbVJn8EZ4swG-mycpsE0372mgrEzli2W9G-orknGsTW9zfRGbumFkolfB2YDzHNVwTcjG6P_sXxPlmyHB65qHMZ4HGnAY7TzZl80Ikk8huKlWt_V4SlDy8q_TA7fFcaG9X-mtOg17ZW2Zrh9b21JRze4hYkZ7TqgTbnMMcpUI2jlIceqAaA1t=w400-h94)](https://blogger.googleusercontent.com/img/a/AVvXsEht5S-kbVJn8EZ4swG-mycpsE0372mgrEzli2W9G-orknGsTW9zfRGbumFkolfB2YDzHNVwTcjG6P_sXxPlmyHB65qHMZ4HGnAY7TzZl80Ikk8huKlWt_V4SlDy8q_TA7fFcaG9X-mtOg17ZW2Zrh9b21JRze4hYkZ7TqgTbnMMcpUI2jlIceqAaA1t)

  

Mặc dù màu nền không được kế thừa xuống các hậu duệ, tuy nhiên, do màu nền mặc định của các phần tử là trong suốt (transparent), nên màu nền của phần-tử-cha cũng được xem như là màu nền của các phần tử hậu duệ. Ví dụ, chúng ta có thể thiết lập màu nền cho toàn bộ trang web bằng cách thiết lập màu nền cho phần tử _body_. Sau đó, chúng ta cũng có thể thay đổi màu nền cho từng phần tử trong một trang web, dù là phần tử kiểu block hay kiểu inline.

**Giới hạn vùng nền**

Như đã biết, vùng nền (background) mặc định của một phần tử sẽ được tính từ viền ngoài của đường biên (border). Tuy nhiên, chúng ta có thể sử dụng thuộc tính _background-clip_ để giới hạn vùng nền theo các tiêu chí khác nhau.

Thuộc tính _background-clip_:

– Giá trị: _border-box | padding-box | content-box_

– Mặc định: _border-box_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Ngoài giá trị mặc định, nếu giá trị là _padding-box_, vùng nền được tính từ viền ngoài của vùng padding. Nếu giá trị là _content-box_, vùng nền được tính từ viền ngoài của vùng nội dung.

Ví dụ:

```html

    <blockquote\>

        <p\>Đây là ví dụ về background-clip</p\>

      </blockquote\>
```
```css

     blockquote {

      border: 4px dashed;

      padding: 10px;

      color: #043527;

      background-color:#7ccfaf;

      background-clip: content-box;

    }
```
[![](https://blogger.googleusercontent.com/img/a/AVvXsEhaxtD9_aX37Ev7ewpbpb5tWoJ7FEAovPZK0Mid1Ts827tgGNkgVcRPPCzg7CfTTxOPDhfzdGevLxRLBsazioZiSM1bCRclHcTzuexgg7UwG-n_OQ0EXO2GCXxxPoQ6jfvQA-Oj3oPcTwurKl3vFoUOma-Fg79t5nAZSXKhg32JirUzQ0knkhIo580R=w400-h225)](https://blogger.googleusercontent.com/img/a/AVvXsEhaxtD9_aX37Ev7ewpbpb5tWoJ7FEAovPZK0Mid1Ts827tgGNkgVcRPPCzg7CfTTxOPDhfzdGevLxRLBsazioZiSM1bCRclHcTzuexgg7UwG-n_OQ0EXO2GCXxxPoQ6jfvQA-Oj3oPcTwurKl3vFoUOma-Fg79t5nAZSXKhg32JirUzQ0knkhIo580R)

  

### 3.1.3       Làm mờ một phần tử

Ở phần trước, chúng ta đã tìm hiểu cách làm mờ một phần tử bằng định dạng màu _RGBa_. Phần này giới thiệu một cách khác để làm mờ phần tử bằng thuộc tính _opacity_. Opacity có nghĩa là độ mờ.

Thuộc tính _opacity:_

– Giá trị: _giá trị số (trong khoảng từ 0 đến 1)_

– Mặc định: _1_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Giá trị của thuộc tính _opacity_ càng nhỏ thì phần tử càng mờ, giá trị 0 là mờ nhất, giá trị 1 là rõ nhất.

Ví dụ,
```css
    body {

      background-color: #333333;

    }

    h1 {

        color: #00FF00;

        background-color: #FFFFFF;

        opacity: .25;

    }
```
Hình dưới đây là một số ví dụ sử dụng thuộc tính _opacity_,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEjp5QJlOghoe5mnmbEKVLLc5rGVdQv2yC06cWZayVi5BudmlrEoXqzq8Mn3Bt6daOoMgaa5l_zMDm33MJ0cQZlcC3qtiWEUv7eXqSt_UWVapQIzsQpjXW1DxN8HvMXUUaIxYVOnXRMX2ElkwltTIVGwKtkiGSJe5wFIqwcN4MVdhdCQe3IGSaua9IMZ=w400-h185)](https://blogger.googleusercontent.com/img/a/AVvXsEjp5QJlOghoe5mnmbEKVLLc5rGVdQv2yC06cWZayVi5BudmlrEoXqzq8Mn3Bt6daOoMgaa5l_zMDm33MJ0cQZlcC3qtiWEUv7eXqSt_UWVapQIzsQpjXW1DxN8HvMXUUaIxYVOnXRMX2ElkwltTIVGwKtkiGSJe5wFIqwcN4MVdhdCQe3IGSaua9IMZ)

  

### 3.1.4       Xem và đọc thêm

– \[1\] _Jenifer Niederst Robbins, **Learning Web Design**, O’Reilly, 2018, trang 303 - 315_

### 3.1.5       Bài tập và thực hành

Bài tập 3.1a. Viết lại các đoạn mã trong phần lý thuyết.

Bài tập 3.1b. Định dạng màu cho chữ Google, giống như trong trang google.com

\[Gợi ý làm bài tập\]

Bài tập 3.1b.

– Tạo thư mục dự án, tên Google, tạo tập tin index.html

– Kiểm tra trên trang google.com, thấy chữ Google là một ảnh, vì vậy chúng ta không thể xem được mã nguồn HTML và CSS để bắt chước theo. Vậy là phải tự sáng tạo ra cách làm.

– Sử dụng phần tử _p_ để tạo chữ Google, vì các chữ có màu khác nhau nên sẽ sử dụng phần tử _span_ để tách từng chữ, gán cho mỗi màu một class.

\[index.html\]
```html
    <p\><span _class_\="blue"\>G</span\>

    <span _class_\="red"\>o</span\>

    <span _class_\="yellow"\>o</span\>

    <span _class_\="blue"\>g</span\>

    <span _class_\="green"\>l</span\>

    <span _class_\="red"\>e</span\></p\>
```
\[CSS\]
– Chọn phông chữ, tìm trên mạng biết được phông chữ mà google đang dùng là Product Sans, tải phông chữ này về máy. Ví dụ, tải từ đây: [https://www.dafontfree.io/google-logo-font/](https://www.dafontfree.io/google-logo-font/). Giải nén, lưu vào trong thư mục fonts của dự án, xem hình:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEj-avGBVEukNJwc-n2DIKrcFyaespKFZjOk1tVd0ffzS7E8_PIzKovfiDY0dZL3eGkUV0V-y0FLHumD9ei9ZJf2UYXmb2XYpltrJKmA6fIYc1a-3u_WtoKxZiELthzhKy8Xdf6A5nlHvo5jmB_R6NB8ug3OjBEyA9YkJ3ddFEr72RG6EiRorIlyx2wg=w400-h200)](https://blogger.googleusercontent.com/img/a/AVvXsEj-avGBVEukNJwc-n2DIKrcFyaespKFZjOk1tVd0ffzS7E8_PIzKovfiDY0dZL3eGkUV0V-y0FLHumD9ei9ZJf2UYXmb2XYpltrJKmA6fIYc1a-3u_WtoKxZiELthzhKy8Xdf6A5nlHvo5jmB_R6NB8ug3OjBEyA9YkJ3ddFEr72RG6EiRorIlyx2wg)

  

– Khai báo để dùng được phông chữ Product Sans
```css
    @font-face {

        font-family: "Product Sans";

        src: **url**('fonts/product-sans/Product Sans Bold.ttf');

    }

    p {

        font-family: "Product Sans", sans-serif;

    }
```
– Thiết lập font-size cho chữ Google, có thể đặt chữ Google do chúng ta tạo ra bên cạnh chữ Google mẫu, khi nào kích thước chúng bằng nhau thì đó là font-size. Hoặc chuyên nghiệp hơn thì dùng các phần mềm xử lý ảnh để đo, ví dụ dùng photoshop online: [https://photoshoponlinemienphi.com/](https://photoshoponlinemienphi.com/).
```css
font-size: 90px;
```
– Thu nhỏ khoảng cách giữa các kí tự, căn giữa dòng chữ
```css
      letter-spacing: \-11px;

      text-align: center;
```
– Dùng công cụ Developer tools để lấy màu của mỗi kí tự, viết mã CSS cho mỗi class.

Mã nguồn tham khảo:

\[index.html\]
```html
<!DOCTYPE _html_ >

<html\>

<head\>

<meta _charset_\="utf-8"\>

<title\>Google</title\>

<style\>

    @font-face {

        font-family: "Product Sans";

        src: **url**('fonts/product-sans/Product Sans Bold.ttf');

    }

    p {

        font-family: "Product Sans", sans-serif;

        font-size: 90px;

        letter-spacing: \-11px;

        text-align: center;

    }

    .blue { color: #4285f4; }

    .red { color: #ea4335; }

    .yellow { color: #fbbc05; }

    .green { color: #34a853; }

</style\>

</head\>

<body\>

    <p\><span _class_\="blue"\>G</span\>

    <span _class_\="red"\>o</span\>

    <span _class_\="yellow"\>o</span\>

    <span _class_\="blue"\>g</span\>

    <span _class_\="green"\>l</span\>

    <span _class_\="red"\>e</span\></p\>

</body\>

</html\>
```
