### CSS (12) - Ảnh nền (1)

Bài trước: [CSS (11) - Bộ chọn theo trạng thái & thuộc tính](https://legiacong.blogspot.com/2023/06/css-11-bo-chon-theo-trang-thai-thuoc.html)

-----

3.3 Ảnh nền
-----------------

Để chèn hình ảnh vào trang web, chúng ta có 2 cách: một là chèn hình ảnh như là một phần của nội dung web (dùng phần tử img, picture), và hai là chèn ảnh dưới dạng nền (dùng CSS).

Phần này, chúng ta sẽ tìm hiểu các thuộc tính để chèn và thao tác với ảnh nền. Gồm các thuộc tính sau:

– background-image

– background-repeat

– background-position

– background-attachment

– background-size

– background-origin

– background-clip

– background

### 3.3.1       Chèn và thao tác với ảnh nền

Chúng ta sử dụng thuộc tính _background-image_ để thêm một ảnh nền cho phần tử HTML bất kì.

Thuộc tính _background-image_:

– Giá trị: _url (vị trí của tập tin ảnh) | none_

– Mặc định: _none_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Nơi chứa ảnh nền được xác định bằng một URL kiểu tương đối, xét theo vị trí của tập tin mã nguồn chứa thuộc tính background-image.

Nhắc lại một vài quy ước liên quan đến URL kiểu tương đối:

– Nếu tập tin ảnh cùng thư mục với tập tin chứa thuộc tính background-image, thì giá trị URL chỉ gồm tên tập tin. Ví dụ _url(star.png)_

– Nếu tập tin ảnh nằm trong thư mục, cùng cấp với tập tin chứa thuộc tính background-image, thì giá trị URL sẽ gồm tên thư mục và đường dẫn tới tên tập tin. Ví dụ: _url(img/star.png)_. Mỗi dấu / (gạch chéo, xuyệt xuôi – forward slash) tương ứng với một cấp của thư mục. Nếu tập tin ảnh nằm trong các thư mục con lồng nhau, thì chúng ta sẽ sử dụng các dấu xuyệt xuôi để dẫn tới tập tin ảnh. Ví dụ: _url(img/bgimg/star.png)._

– Nếu tập tin ảnh nằm trong thư mục cha (hoặc các cấp cao hơn trong cây thư mục) thì sử dụng kí hiệu “../” ứng với mỗi thư mục, để di chuyển con trỏ thư mục lên một cấp cao hơn. Ví dụ: nếu thuộc tính background-image nằm tại _css/style.css_, và thư mục _css_ cùng cấp với thư mục _img_, thì chúng ta có đường dẫn hình ảnh như sau: _url(../img/star.png)_

_–_ Có thể sử dụng dấu “/” để luôn bắt đầu đường dẫn tương đối từ thư mục gốc của website (web root). Ví dụ: _url(/img/star.png)._ Lưu ý: ở trường hợp này, bạn không thể chạy và kiểm tra trang web ở chế độ local, mà phải cấu hình máy tính của bạn thành một web server.

Ví dụ, dưới đây là đoạn mã CSS để thêm ảnh nền cho toàn bộ trang web (phần tử _body_) và cho phần tử _blockquote_,
```css
body {

background-image: url(star.png);

}

blockquote {

background-image: url(dot.png);

padding: 2em;

border: 4px dashed;

}
```
Để thực hành ví dụ trên, chúng ta sẽ tải 2 hình ảnh (_star.png_ và _dot.png_) từ trên mạng, lưu vào cùng thư mục với tập tin mã nguồn HTML. Kích thước ảnh khoảng 50x50px. Bạn có thể tải ảnh với kích thước bất kì, sau đó sử dụng các trang web để điều chỉnh kích thước ảnh theo ý muốn.

Xem hình kết quả:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEh5fBAWJwq2teVdhm_lUOgngO1xi0LV3eXBtybCylM-DRGG76D3Mk1UT4EzyTqcgnUU2UAP8uf7AEC-_3vUN80rJ7OA8RzW7WSkVfpTo8WahkXrfUL0c0U_bFvLBJ65V-pq4Bdin5R7kpj_HioIKAW2-w4KXi7RMyXbeRa-a6sbrxKxAQ2Qu9rAbHvSl3s=w400-h224)](https://blogger.googleusercontent.com/img/a/AVvXsEh5fBAWJwq2teVdhm_lUOgngO1xi0LV3eXBtybCylM-DRGG76D3Mk1UT4EzyTqcgnUU2UAP8uf7AEC-_3vUN80rJ7OA8RzW7WSkVfpTo8WahkXrfUL0c0U_bFvLBJ65V-pq4Bdin5R7kpj_HioIKAW2-w4KXi7RMyXbeRa-a6sbrxKxAQ2Qu9rAbHvSl3s)

  

Ở chế độ mặc định, nếu kích thước ảnh nền nhỏ hơn kích thước của phần tử, thì ảnh nền gốc sẽ được đặt ở góc trên bên trái, sau đó là các bản sao của ảnh nền. Các bản sao của ảnh nền được sắp xếp theo hàng, hết hàng trên tới hàng dưới, cho tới khi nào lấp đầy phần tử. Cũng giống như khi thiết lập màu nền, vùng được chèn ảnh nền bao gồm: vùng nội dung, vùng đệm phía trong đường viền (padding), và đường viền (border).

Nếu một phần tử được thiết lập cả màu nền (background-color) và ảnh nền (background-image) thì ảnh nền sẽ nằm phía trên của màu nền. Vì lý do này, nên thiết lập màu nền tương tự như màu chủ đạo của ảnh nền, đề phòng trường hợp không tải được ảnh nền thì vẫn có màu nền phù hợp, và không ảnh hưởng nhiều đến chất lượng trang web.

Khi thêm ảnh nền, cần chú ý một số điểm sau:

– Sử dụng ảnh nền phù hợp để dễ đọc phần nội dung (như ví dụ ở hình trên là không phù hợp, chữ màu đen, nền màu xanh làm cho người dùng rất khó đọc được nội dung)

– Luôn thiết lập màu nền dự phòng (background-color), chọn màu nền tương tự với màu chủ đạo của ảnh nền

– Đảm bảo kích thước của ảnh nền luôn ở mức nhỏ nhất có thể

**Nhân bản ảnh nền**

Như ở phần trên đã nói, ở chế độ mặc định, nếu ảnh nền nhỏ hơn phần tử thì ảnh nền sẽ được nhân bản thành nhiều ảnh và sắp xếp từ trái qua phải, từ trên xuống dưới, cho tới khi nào lấp đầy phần tử. Để thay đổi chế độ nhân bản ảnh nền, chúng ta sử dụng thuộc tính _background-repeat_.

Thuộc tính _background-repeat_:

– Giá trị: _repeat | repeat-x | repeat-y | no-repeat | space | round_

– Mặc định: _repeat_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Ví dụ, nếu chỉ muốn ảnh nền xuất hiện một lần, sử dụng giá trị _no-repeat_,
```css
body {
background-image: url(star.png);
background-repeat: no-repeat;
}
```
Ví dụ, nếu chỉ muốn ảnh nền lặp lại trên một hàng ngang, sử dụng giá trị _repeat-x_,
```css
body {
background-image: url(star.png);
background-repeat: repeat-x;
}
```
Ví dụ, nếu chỉ muốn ảnh nền lặp lại trên một hàng dọc, sử dụng giá trị _repeat-y_,
```css
body {
background-image: url(star.png);
background-repeat: repeat-y;
}
```
Nếu để ý, khi nhân bản ảnh nền, sẽ có nhiều trường hợp ảnh nhân bản bị cắt xén. Để tránh điều này, chúng ta sử dụng 2 giá trị space và round cho thuộc tính background-repeat. Với giá trị space, trình duyệt sẽ ước lượng số ảnh cần nhân bản và duy trì kích thước ban đầu của ảnh. Với giá trị round, cũng giống như giá trị space, tuy nhiên, trình duyệt sẽ thay đổi kích thước của ảnh (co dãn ảnh) để lấp đầy không gian trống của phần tử.

Xem hình minh họa các giá trị của thuộc tính background-repeat:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEitXGbnHe1rGtGJ3DxIDMFXoYL9o4fovxma3WbKDA-1nqHOtZ_rRbShH8VKK5tLK8eCdgBa7WlzpU4rfth_jlg4JH1pzz0yePKL04R6YUhk6dyBzbYapkF1v6MI_i1-c8DQ6GAt3clWPq5b9R-SHKTZVtkfiLouJJxy2Zjp2spY9ySirhb9nC2ZezWymrQ=w400-h390)](https://blogger.googleusercontent.com/img/a/AVvXsEitXGbnHe1rGtGJ3DxIDMFXoYL9o4fovxma3WbKDA-1nqHOtZ_rRbShH8VKK5tLK8eCdgBa7WlzpU4rfth_jlg4JH1pzz0yePKL04R6YUhk6dyBzbYapkF1v6MI_i1-c8DQ6GAt3clWPq5b9R-SHKTZVtkfiLouJJxy2Zjp2spY9ySirhb9nC2ZezWymrQ)

  

**Xác định vị trí đặt ảnh gốc**

Chúng ta sử dụng thuộc tính _background-position_ để xác định vị trí đặt ảnh gốc (origin image). Ảnh gốc là ảnh đầu tiên đặt vào nền, việc nhân bản các ảnh sau đó sẽ dựa vào ảnh gốc này.

Thuộc tính _background-position:_

– Giá trị: _đơn vị đo chiều dài | % | left | center | right | top | bottom_

– Mặc định: _0% 0% (tương đương với left top)_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Vị trí đặt ảnh gốc được xác định bằng 2 giá trị, thể hiện vị trí theo chiều ngang và chiều dọc của phần tử. Chúng ta có một số cách xác định vị trí như sau:

**_Dùng từ khóa_**

Các từ khóa _left, center, right, top, bottom_ là các vị trí tương đối, tính từ mép trong đường viền của phần tử. Ví dụ, nếu giá trị của background-position là _left_ thì sẽ đặt ảnh gốc ở sát mép đường viền trái của phần tử.

Vị trí mặc định để đặt ảnh gốc là bên trái, phía trên: `_left`, `top_`.

Các từ khóa này thường được sử dụng theo cặp, ví dụ,

`background-position: left bottom;`

`background-position: right center;`

Nếu chỉ cung cấp một từ khóa, thì trình duyệt sẽ ngầm hiểu từ khóa còn lại là _center_. Ví dụ, nếu khai báo là,

`background-position: left`

Thì cũng sẽ tương đương với khai báo,

`background-position: left center`

**_Dùng đơn vị đo_**

Chúng ta cũng có thể xác định vị trí của ảnh gốc dựa vào khoảng cách so với biên trái và biên trên của phần tử, sử dụng đơn vị đo là pixel, khoảng cách với biên trái được viết trước, biên trên viết sau.

Ví dụ,

`background-position: 200px 50px;`

**_Dùng %_**

Giá trị % cũng luôn được sử dụng theo cặp _ngang/dọc_, với 0% 0% sẽ tương ứng với bên trái góc trên; 100% 100% sẽ tương ứng với bên phải góc dưới. Lưu ý, giá trị % này sẽ áp dụng cho cả vùng nền (vùng canvas) và ảnh gốc, nghĩa là ảnh gốc sẽ không thể vượt ra khỏi vùng nền. Ví dụ, giá trị 100% 100% sẽ đặt phần _bên phải góc dưới_ của ảnh gốc vào _bên phải góc dưới_ của vùng nền. Nếu chỉ cung cấp một giá trị % thì giá trị còn lại sẽ được ngầm hiểu là 50% (_center_).

Hình sau là ví dụ đặt ảnh gốc ở các vị trí khác nhau,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEhRfSsqrqFmVGCaPKmqTweq7MYWNiVRfiS7IhC4IunIlCRFH4ZUqobmF6Zx4v-aFpDeptlwr3b4B_U5JPcATwEbw-seh3HoSgjyn-KVqGlzZi-UFGd7yOwNj1fxxKEmVLSuNzRlSYEacMMG-W_WwpZWXr_aqBGAeplwMb_N0UaHTfIqd7oUZiDT2m1Mi10=w400-h284)](https://blogger.googleusercontent.com/img/a/AVvXsEhRfSsqrqFmVGCaPKmqTweq7MYWNiVRfiS7IhC4IunIlCRFH4ZUqobmF6Zx4v-aFpDeptlwr3b4B_U5JPcATwEbw-seh3HoSgjyn-KVqGlzZi-UFGd7yOwNj1fxxKEmVLSuNzRlSYEacMMG-W_WwpZWXr_aqBGAeplwMb_N0UaHTfIqd7oUZiDT2m1Mi10)

  

**Cố định ảnh nền**

Mặc định, khi bạn cuộn nội dung trang web, ảnh nền sẽ bị cuộn theo phần nội dung. Tuy nhiên, chúng ta có thể sử dụng thuộc tính _background-attachment_ để cố định ảnh nền.

Thuộc tính _background-attachment_:

– Giá trị: _scroll | fixed | local_

– Mặc định: _scroll_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Với thuộc tính _background-attachment_, chúng ta có thể tùy chọn để ảnh nền cuộn theo nội dung (scroll), hoặc nằm cố định (fixed) so với cửa sổ trình duyệt (viewport), hoặc chỉ cuộn theo nội dung của một phần tử (local) chứ không theo thanh cuộn của cửa sổ trình duyệt.

**_Thuộc tính background-size_**

Các giá trị của thuộc tính _background-size: length | percentage | auto | contain | cover_

Thuộc tính _background-size_ được sử dụng để thiết lập lại kích thước của ảnh nền, gồm chiều rộng và chiều cao (ví dụ 100px 200px), nếu chỉ thiết lập một chiều thì chiều còn lại sẽ là _auto_. Nếu muốn ảnh nền nằm trọn trong phần tử chứa nó thì thiết lập giá trị là _contain_, trường hợp này có thể còn những chỗ không được phủ ảnh nền (ví dụ phần tử hình chữ nhật mà ảnh nền lại hình tròn). Nếu muốn ảnh nền phủ toàn bộ phần tử chứa nó thì thiết lập giá trị là _cover_, trường hợp này có thể có một phần của ảnh nền bị tràn ra khỏi phần tử chứa nó.

**_Thuộc tính background-origin_**

Các giá trị của thuộc tính _background-origin: border-box | padding-box | content-box_

Thuộc tính _background-origin_ được sử dụng để xác định cách tính vị trí cho thuộc tính _background-position_. Nghĩa là, vị trí bắt đầu được tính sẽ là mép ngoài đường viền (_border-box_) hay mép ngoài vùng padding (_padding-box_), hay mép ngoài nội dung (_content-box_).

**_Thuộc tính background-clip_**

Các giá trị của thuộc tính _background-clip: border-box | padding box | content-box_

Thuộc tính _background-clip_ được sử dụng để xác định phạm vi bao phủ của ảnh nền (xén bớt ảnh nền, từ clip nghĩa là xén bớt đi, cắt bớt đi). Mặc định ảnh nền sẽ được phủ vùng nội dung, vùng đệm phía trong đường viền, và nền của đường viền (_border-box_). Nếu chỉ muốn phủ vùng nội dung và vùng đệm phía trong đường viền thì thiết lập giá trị là _padding-box_ (cái hộp chứa hết phần padding). Nếu chỉ muốn phủ vùng nội dung thì thiết lập giá trị là _content-box_ (hộp chứa nội dung).

**Thuộc tính background**

Có thể sử dụng thuộc tính _background_ để thiết lập tất cả các định dạng liên quan đến ảnh nền trong một khai báo CSS.

Thuộc tính _background_:

– Giá trị: _background-color background-image background-repeat background-attachment_

_background-position | background-clip | background-origin | background-size_

– Mặc định: _tùy thuộc vào giá trị mặc định của mỗi thuộc tính_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Cũng giống như thuộc tính _font_, các giá trị của thuộc tính _background_ chính là giá trị của từng thuộc tính đã được liệt kê ở trên.

Ví dụ,

`_body { background: white url(star.png) no-repeat right top fixed; }_`

Chỉ dẫn CSS trên là viết rút gọn của các chỉ dẫn CSS sau:
```css
body {
background-color: white;
background-image: url(arlo.png);
background-repeat: no-repeat;
background-position: right top;
background-attachment: fixed;
}
`
Các giá trị trong thuộc tính _background_ đều là tùy chọn, và không cần theo thứ tự. Chỉ có một lưu ý là khi khai báo giá trị của thuộc tính _background-position_ thì phải khai báo giá trị chiều ngang (horizontal value) trước, ngay sau đó là giá trị chiều dọc. Nếu giá trị nào không khai báo trình duyệt sẽ sử dụng giá trị mặc định.

Cẩn thận khi sử dụng thuộc tính _background_ để tránh bị ghi đè. Quan sát ví dụ sau,

`h1, h2, h3 { background: red url(dots.gif) repeat-x;}`

`h3 {background: green;}`

Mục đích của chỉ dẫn CSS ở hàng thứ hai là muốn thay đổi màu nền dự phòng cho _h3_ từ _red_ sang _green_, tuy nhiên trong chỉ dẫn lại không khai báo giá trị _background-image_ cho phần tử _h3_, nên giá trị của nó sẽ được thiết lập là mặc định (_none_), điều này vô tình đã ghi đè lên giá trị _background-image_ ở hàng 1. Nghĩa là _h3_ sẽ không được thiết lập ảnh nền _star.png_. Vậy để ghi đè một thuộc tính cụ thể nào đó thì nên dùng tên thuộc tính dạng đầy đủ, chứ không nên sử dụng thuộc tính rút gọn. Chỉ dẫn ở hàng thứ hai nên viết lại là,

`h3 {background-color: green;}`

**Chèn nhiều ảnh nền**

CSS3 cho phép chèn nhiều ảnh nền cho một phần tử. Để thực hiện, sử dụng thuộc tính _background-image_, mỗi giá trị của thuộc tính này là một ảnh nền, được ngăn cách nhau bằng dấu phẩy. Các thuộc tính liên quan cũng được liệt kê thành một dãy, mỗi giá trị ngăn cách nhau bằng dấu phẩy, giá trị đầu tiên sẽ áp dụng cho ảnh đầu tiên, giá trị thứ hai sẽ áp dụng cho ảnh thứ hai, lần lượt cho đến hết. Ảnh được liệt kê trước trong thuộc tính _background-image_ sẽ nằm ở phía trên cùng của nền, sau đó lần lượt đến các ảnh tiếp theo.

Ví dụ,
```css
body {
background-image: url(image1.png), url(image2.png), url(image3.png);
background-position: left top, center center, right bottom;
background-repeat: no-repeat; no-repeat; no-repeat;
…
}
```
Lưu ý: mặc dù các chỉ dẫn của CSS hoạt động theo kiểu “cái nào áp dụng sau sẽ được ưu tiên”. Tuy nhiên, trong trường hợp chèn nhiều ảnh nền thì nó làm việc theo kiểu khác, cứ tưởng tượng, cái nền có thể xếp được nhiều ảnh, khi đó ảnh nào nằm cuối danh sách sẽ được đặt ở dưới cùng, sau đó là các ảnh tiếp theo, ảnh ở đầu danh sách sẽ nằm ở trên cùng.

Có thể sử dụng thuộc tính _background_ để viết các luật CSS được gọn hơn, ví dụ,
```css
body {
background:
url(image1.png) left top no-repeat,
url(image2.png) center center no-repeat,
url(image3.png) right bottom no-repeat;
…
}
```
Vì có một số phiên bản của trình duyệt IE không hỗ trợ chèn nhiều ảnh nền bằng thuộc tính _background_, nên để tăng khả năng tương thích của trang web, khi viết mã sẽ sử dụng thêm thuộc tính _background-image_ để dự phòng, sau đó là các hình ảnh của thuộc tính _background_. Nếu trình duyệt có hỗ trợ _background_, thì thuộc tính này sẽ đè thuộc tính _background-image_. Cuối cùng luôn dự phòng một màu nền bằng thuộc tính _background-color_. Ví dụ,
```css
body {
/* cho các trình duyệt không hỗ trợ nhiều giá trị trong thuộc tính background */
background-image: url(image_fallback.png) top left no-repeat;
background:
url(image1.png) left top no-repeat,
url(image2.png) center center no-repeat,
url(image3.png) right bottom no-repeat;
background-color: papayawhip; /* màu nền dự phòng */
}
```
