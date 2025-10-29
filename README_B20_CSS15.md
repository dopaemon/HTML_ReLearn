### CSS (15) - Mô hình cái hộp (2)

Bài trước: [CSS (14) - Mô hình cái hộp (1)](https://legiacong.blogspot.com/2023/08/css-14-mo-hinh-cai-hop-1.html)

-----

### 4.1.7       Thuộc tính Display

Nhắc lại một chút về hai kiểu hiển thị quen thuộc, một là kiểu block, hai là kiểu inline. Mặc định, phần tử kiểu block có chiều rộng chiếm trọn một hàng, chiều cao vừa đủ để chứa hết nội dung; phần tử kiểu inline nằm theo hàng, có chiều rộng và chiều cao vừa đủ để chứa hết nội dung. Chúng ta không thể thay đổi được kích thước (width và height) của phần tử kiểu inline.

Mỗi phần tử HTML sẽ có kiểu hiển thị mặc định. Tuy nhiên, chúng ta vẫn có thể thay đổi kiểu hiển thị của một phần tử bằng thuộc tính _display_.

Thuộc tính _display:_

– Giá trị: _inline | block | run-in | flex | grid | flow | flow-root | list-item | table  | table-row-group | table-header-group | table-footer-group | table-row | table-cell | table-column-group | table-column | table-caption | inline-block | inline-table | ruby | ruby-base | ruby-text | ruby-base-container | ruby-text-container | inline-flex | inline-grid | contents | none_

– Mặc định: _inline_

– Áp dụng: _mọi phần tử_

– Kế thừa: _có_

Thuộc tính _display_ sẽ xác định kiểu hiển thị của phần tử, ngoài hai kiểu quen thuộc là block và inline, còn có nhiều kiểu khác như _flex, grid_, _list-item_, _inline-block_, và các kiểu liên quan đến table.

Nói chung, tổ chức W3C không khuyến khích việc thay đổi kiểu hiển thị mặc định của các phần tử. Tuy nhiên, trong nhiều trường hợp, việc thay đổi kiểu hiển thị đã trở thành phổ biến. Ví dụ, kiểu hiển thị mặc định của phần tử _li_ là block, nhưng để tạo một menu ngang thì cần thiết lập kiểu hiển thị của _li_ là inline. Hoặc kiểu hiển thị mặc định của phần tử _a_ là inline, nhưng để có thể thiết lập chiều cao và chiều rộng cho nó thì cần thiết lập kiểu hiển thị là block. Ví dụ,

ul.navigation li { display: inline; }

ul.navigation li a { display: block; }

Lưu ý: việc thay đổi kiểu hiển thị chỉ có ý nghĩa làm thay đổi cách nó được trình bày trên giao diện, chứ không làm thay đổi bản chất kiểu phần tử (block hoặc inline) của nó. Vì vậy, sẽ không thể đặt một phần tử kiểu block vào trong một phần tử kiểu inline, dù đã đổi kiểu hiển thị bằng thuộc tính _display_.

Giá trị _none_ của thuộc tính _display_ được sử dụng khá phổ biến để cắt bỏ một nội dung nào đó trên giao diện (khi màn hình hiển thị có kích thước nhỏ), tất nhiên trong mã nguồn và khi in nội dung trang kết quả thì vẫn có phần nội dung này. Khác với cách dùng _display: none,_ nếu thiết lập một phần tử với _visibility: hidden_ thì nội dung không được hiển thị nhưng nó vẫn chiếm một vùng trắng trên giao diện.

Lưu ý: thiết lập _display: none_ cho một phần tử nghĩa là không cho hiển thị nội dung lên giao diện chứ không làm giảm dung lượng của mã nguồn, và do đó không thể tăng tốc độ tải trang về máy bằng cách này được.

### 4.1.8       Tạo bóng cho hộp

Ở phần định dạng văn bản, chúng ta đã biết cách tạo bóng cho văn bản bằng thuộc tính _text-shadow_. Để tạo bóng cho hộp (tính từ đường viền vào trong, không tính vùng margin) sẽ sử dụng thuộc tính _box-shadow_, cách làm việc của thuộc tính này khá giống với  thuộc tính _text-shadow_.

Thuộc tính _box-shadow_:

– Giá trị: _‘horizontal-offset’ ‘vertical-offset’ ‘blur distance’ ‘spread distance’ color inset | none_

– Mặc định: _none_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Trong đó,

– _horizontal offset_ là khoảng dịch của bóng sang phía phải so với hộp ban đầu, nếu giá trị này là âm, bóng sẽ được dịch sang phía trái

– _vertical offset_ là khoảng dịch của bóng xuống phía dưới so với hộp ban đầu, nếu giá trị này là âm, bóng sẽ được dịch lên phía trên

– _color_: màu của bóng, nếu bỏ qua giá trị này, bóng sẽ cùng màu với “màu mặt trước” (foreground color) của phần tử

– _blur distance_ là khoảng mờ của bóng, giá trị 0 là không có khoảng mờ, giá trị càng cao khoảng mờ càng lớn, đơn vị đo là px

– _spread distance_ là độ tràn (khoảng tràn) của bóng, giá trị dương là tràn ra ngoài, giá trị âm là thu gọn vào trong. Dùng để tăng hoặc giảm kích thước của bóng

– _inset_ là từ khóa, nếu được thiết lập, bóng sẽ đổ vào phía trong phần tử

Xem hình ví dụ dưới đây. Hình (A) là tạo bóng đơn giản, bóng sẽ dịch phải 5px, dịch xuống 10px so với hộp ban đầu. Hình (B) thêm khoảng mờ 4px. Hình (C) thêm độ tràn 8px. Hình (D) đổ bóng vào phía trong của hộp.

[![](https://blogger.googleusercontent.com/img/a/AVvXsEhVO_DG76bI8jG3TWvOWOcFwJsTHgMufhqp5HC_oBFnaYoueIoYIW8xxpqkprYcFlH-s5UhZcDbMUFsnPQ6aTQErgs511IhzO_7ODVx_ChQyDjkIld2-S0ZUhPtg3mulbcx338nR-KlxvHnYsruSs47C5xGNcz4bVXjhrJd2Df66SZKIYFzFG2MFvnal8c=w400-h278)](https://blogger.googleusercontent.com/img/a/AVvXsEhVO_DG76bI8jG3TWvOWOcFwJsTHgMufhqp5HC_oBFnaYoueIoYIW8xxpqkprYcFlH-s5UhZcDbMUFsnPQ6aTQErgs511IhzO_7ODVx_ChQyDjkIld2-S0ZUhPtg3mulbcx338nR-KlxvHnYsruSs47C5xGNcz4bVXjhrJd2Df66SZKIYFzFG2MFvnal8c)

  

Cũng như thuộc tính _text-shadow_, có thể tạo nhiều bóng cho hộp, mỗi chuỗi giá trị của một bóng ngăn cách bằng dấu phẩy (,), bóng được tạo bởi chuỗi giá trị nằm trước sẽ nằm phía trên của hộp, sau đó đến bóng của các chuỗi tiếp theo.

Ví dụ,

box-shadow: 5px 10px 4px 10px green inset, 5px 10px yellow;

Lưu ý: _text-shadow, box-shadow_, và _gradient_ sẽ đòi hỏi nhiều tài nguyên của CPU để xử lý, do đó, sẽ làm giảm tốc độ hiển thị kết quả của trình duyệt, vì vậy không nên lạm dụng quá nhiều các đặc tính này.


### 4.1.10       Bài tập và thực hành

Bài tập 1. Viết lại các đoạn mã trong phần lý thuyết.

Bài tập 2. Bạn có thể tham khảo mã nguồn, hình ảnh ở đây: [https://learningwebdesign.com/5e/materials/](https://learningwebdesign.com/5e/materials/) (vào thư mục con có tên là _ch14_).

Các bước thực hiện:

**Adding a little padding**

In this exercise, we’ll begin adding box properties to improve the appearance of a site for the fictional Black Goose Bakery.

Start by getting familiar with the source document. Open _bakery.html_ in a browser and a text editor to see what you’ve got to work with. The style sheet has been added with an @import rule in the style element. The document has been marked up with header (including a nav section), main, aside, and footer sections.

[_bakery.html_]
```html

<!doctype _html_>

<html>

<head>

  <meta _charset_="UTF-8">

  <title>Black Goose Bakery</title>

  <meta _name_="viewport" _content_="width=device-width, initial-scale=1">

  <link _href_="https://fonts.googleapis.com/css?family=Stint+Ultra+Expanded" _rel_="stylesheet">

  <style>

    @import **url**(bakery-styles.css);

  </style>

</head>

<body>

  <header>

    <nav>

      <ul>

        <li><a _href_="">Menu</a></li>

        <li><a _href_="">News</a></li>

        <li><a _href_="">About</a></li>

        <li><a _href_="">Contact</a></li>

      </ul>

    </nav>

    <h1><img _src_="images/bgb_logo.png" _alt_="Black Goose Bakery"></h1>

    <p>The delicious baked goods you love at Black Goose Bistro...now available to go!</p>

  </header>

  <main>

    <h2>Fresh from the Oven</h2>

    <h3>Breads</h3>

    <p><img _src_="images/bread.png" _alt_="round loaf of bread on cutting board"> Our breads are made daily from

      highest-quality whole grain flour, water, salt, and yeast or sourdough starter. Simply and naturally, and never

      any preservatives. Patience is key to achieving the proper level of fermentation and baking each loaf to

      perfection. Available in whole grain, sourdough, olive loaf, classic rye, and potato-onion.</p>

    <p _class_="more"><a _href_="">Learn more about our baking process...</a></p>

    <h3>Muffins</h3>

    <p><img _src_="images/muffin.png" _alt_="one chocolate chip muffin"> Every day, we offer a large selection of muffins,

      including blueberry, multi-berry, bran, corn, lemon-poppyseed, and chocolate. Our muffins are made from scratch

      each day. Stop by to see our seasonal muffin flavors!</p>

    <p _class_="more"><a _href_="">Learn more about how we make our muffins...</a></p>

  </main>

  <aside>

    <h2>Hours</h2>

    <p><span _class_="day">Monday:</span> 5am to 3pm</p>

    <p><span _class_="day">Tuesday:</span> 5am to 3pm</p>

    <p><span _class_="day">Wednesday:</span> 5am to 3pm</p>

    <p><span _class_="day">Thursday:</span> 5am to 3pm</p>

    <p><span _class_="day">Friday:</span> 5am to 3pm</p>

    <p><span _class_="day">Saturday:</span> 6am to 4pm</p>

    <p><span _class_="day">Sunday:</span> 6am to 4pm</p>

  </aside>

  <footer>

    <p>All content copyright &copy; 2017, Black Goose Bistro.</p>

  </footer>

</body>

</html>
```

Now take a look at _bakery-styles.css_ in your text editor. I used comments in the style sheet to organize the styles related to each section (bonus points for you if you keep the styles organized as you go along!). You will find styles for text formatting, colors, and backgrounds—all properties that we’ve covered so far in this book, so they should look familiar. Now let’s add some rules to _bakery-styles.css_ to add padding to the elements.

[_bakery-styles.css_]
```css
@charset "UTF-8";

body {

  font-family: Georgia, serif;

  font-size: 100%;

  background-color: white;

}

_/* link styles */_

a:link, a:visited { color: #DC6903; }

a:focus, a:hover, a:active { color: #F9AB33; }

_/* header styles */_

header {

  color: white;

  background:  **url**(images/croissants_banner.jpg) no-repeat center center;

  background-size: cover;

  text-align: center;

}

header p {

  font-style: italic;

  font-size: 1.2em;

}

_/* nav styles */_

nav, footer {

  font-family: verdana, sans-serif;

  background-color: #783F27;

}

nav ul li a:link, nav ul li a:visited {

  color: #F9AB33;

}

nav ul li a:focus, nav ul li a:hover, nav ul li a:active {

  color: #fff;

}

nav ul li {

  font-size: .8em;

  text-transform: uppercase;

  letter-spacing: .2em;

}

_/* main "products" styles */_

main {

  font-family: 'Stint Ultra Expanded', cursive;

  background-color: white;

  line-height: 1.8em;

  color: #555;

}

h3 {

  text-transform: uppercase;

  letter-spacing: .2em;

  color: #7A0002;

}

p.more {

  font-family: verdana, sans-serif;

  text-transform: uppercase;

  font-size: .8em;

}

_/* aside "hours" styles */_

aside {

  background: **url**(images/scallop.png) repeat-y left top;

  background-color: #F6F3ED;

}

_/* misc styles */_

footer {

  color: #EADDC4;

  text-align: center;

  font-size: .8em;

}

h2 {

  font-family: 'Stint Ultra Expanded', cursive;

}

.day {

  color: #783F27;

  font-family: verdana, sans-serif;

  font-size: .8em;

  text-transform: uppercase;

}
```

[_Before shot of the Black Goose Bakery site_]

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgSCNlNMsAzKDRPx9aMZyPFCqTq9ljLsE35Iw1yul4DpDb8EVfxW2w-TnHVPRd8U0bWIofqiwAG2RrKCZxw9vcskg-6Sn8WMIlAxmGWlCinqm2KrhaNocXx2fe3sqjsq4uFCyS4P62q1Sst3GxiU3rTXWt2GuAWj0dVFRcB7A_eCJK-5suNFy0BltvcffI/w369-h400/mo%20hinh%20cai%20hop.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgSCNlNMsAzKDRPx9aMZyPFCqTq9ljLsE35Iw1yul4DpDb8EVfxW2w-TnHVPRd8U0bWIofqiwAG2RrKCZxw9vcskg-6Sn8WMIlAxmGWlCinqm2KrhaNocXx2fe3sqjsq4uFCyS4P62q1Sst3GxiU3rTXWt2GuAWj0dVFRcB7A_eCJK-5suNFy0BltvcffI/s576/mo%20hinh%20cai%20hop.png)


### 4.1.11       Câu hỏi ôn tập

Câu 1. Trong CSS, các thành phần của box model gồm:

A. box, margin area, boder, padding area, inner edge, content area

B. outer edge, model, boder, padding area, inner edge, content area

C. outer edge, margin area, radius, padding area, inner edge, content area

**D. outer edge, margin area, boder, padding area, inner edge, content area**

Câu 2. Thứ tự các giá trị của padding hợp lý là:

A. padding: right top bottom left;

**B. padding: top right bottom left;**

C. padding: top bottom right left;

D. padding: left top right bottom;

Câu 3. Khi tạo bóng cho hộp bằng thuộc tính box-shadow, giá trị của …………….. là khoảng dịch của bóng sang phía phải so với hộp ban đầu, nếu giá trị này là âm, bóng sẽ được dịch sang phía trái.

A. vertical-offset

B. blur distance

C. spread distance

**D. horizontal-offset**

Câu 4. Trong CSS, giá trị nào không thể thiết lập cho thuộc tính display?

A. block

B. inline

C. flex

**D. hidden**

Đáp án: 1(D), 2(B), 3(D), 4(D)
