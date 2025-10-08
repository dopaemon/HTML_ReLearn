### CSS (11) - Bộ chọn theo trạng thái & thuộc tính

-----

3.2       Bộ chọn theo trạng thái & thuộc tính
----------------------------------------------

Như đã biết, trong CSS, các bộ chọn được chia thành 4 loại, gồm: Bộ chọn cơ bản (basic selector), Bộ chọn gộp (grouping selector), Bộ chọn tổ hợp (combinator) và Bộ chọn theo trạng thái (pseudo-class, pseudo-element).

Trong đó, Bộ chọn theo trạng thái gồm 2 loại:

– Bộ chọn lớp giả (pseudo class): chọn “lớp giả” là chọn theo các trạng thái của phần tử, ví dụ _a:visited{}_ sẽ chọn các phần tử _a_ đã được người dùng duyệt qua

– Bộ chọn phần tử giả (pseudo element): chọn "phần tử giả" là chọn các phần tử không tồn tại một cách tường minh trong tài liệu HTML, ví dụ _p::first-line{}_ chọn hàng đầu tiên của phần tử _p_

Phần này sẽ tìm hiểu kĩ hơn về Bộ chọn lớp giả và Bộ chọn phần tử giả. Ngoài ra, chúng ta cũng tìm hiểu thêm về Bộ chọn theo thuộc tính (thuộc Bộ chọn cơ bản).

### 3.2.1       Bộ chọn lớp giả (pseudo-class)

Để ý các liên kết (link) trên một trang web, nếu chưa được bấm chuột vào, chúng sẽ có màu xanh, ngược lại, nếu đã được bấm chuột vào, chúng sẽ có màu tím. Có hiện tượng này là do trình duyệt đã lưu lại trạng thái của các liên kết, cho biết chúng đã được bấm chuột hay chưa (clicked, visited).

Ngoài ra, trình duyệt cũng cung cấp một số thông tin trạng thái khác, như khi người dùng đang rê chuột lên một phần tử (hover), một phần tử có là cái đầu tiên của một loại, là con đầu tiên/cuối cùng của một phần tử cha; phần tử có được chọn không (checked) hay phần tử có bị vô hiệu không (disabled).

Trong CSS, chúng ta có thể định dạng phần tử dựa trên các trạng thái như vậy, bằng cách sử dụng bộ chọn pseudo-class.

Pseudo-class được gọi nôm na là “lớp giả”. Sao lại gọi là “lớp giả”? Như đã biết, thuộc tính _class_ được sử dụng để gán định danh cho phần tử, các phần tử có cùng giá trị _class_ (cùng định danh) sẽ được xem là cùng một lớp. Tuy nhiên, trạng thái của phần tử không được thể hiện tường minh trong mã nguồn, nghĩa là không có định danh, mà nó được xác định ngầm (dựa vào vị trí của phần tử trong mã nguồn hoặc tương tác của người dùng), các phần tử có cùng trạng thái cũng được xem là cùng một lớp, nhưng lớp này không tường minh, nên gọi là “lớp giả”.

Cú pháp của pseudo-class thường được bắt đầu bằng tên một phần tử, tiếp theo là dấu hai chấm (:), cuối cùng là tên của trạng thái, ví dụ: _li:first-child_.

Có rất nhiều loại bộ chọn pseudo-class_,_ ví dụ:

– Bộ chọn pseudo-class cho liên kết

– Bộ chọn pseudo-class dựa trên thao tác người dùng

– Bộ chọn pseudo-class dựa trên cấu trúc tài liệu HTML

– Bộ chọn pseudo-class cho các input của form

**Bộ chọn pseudo-class cho liên kết**

Bộ chọn pseudo-class cho liên kết được sử dụng để định dạng các liên kết dựa trên trạng thái của nó. Cụ thể,

_– :link_ dùng để định dạng cho liên kết chưa được người dùng bấm vào

_– :visited_ dùng để định dạng cho liên kết đã được người dùng bấm vào

Ví dụ: mặc định, liên kết người dùng chưa bấm vào sẽ có màu xanh, bấm vào rồi sẽ có màu tím. Tuy nhiên, chúng ta có thể sử dụng CSS để thay đổi màu mặc định của liên kết thành các màu khác,
```css
a:link {

color: maroon;

}

a:visited {

color: gray;

}
```
**Bộ chọn pseudo-class dựa trên thao tác người dùng**

Phần này sẽ tìm hiểu các bộ chọn pseudo-class dựa trên thao tác của người dùng, gồm ba bộ chọn sau:

_– :focus_ áp dụng khi người dùng chọn phần tử để nhập nội dung, phần tử được chọn sẽ nổi bật hơn so với các phần tử còn lại, bộ chọn này hay áp dụng cho các ô nhập liệu của form. Ví dụ, ô nhập liệu sau sẽ có nền màu vàng khi người dùng chọn,

input:focus { background-color: yellow; }

_– :hover_ áp dụng khi người dùng rê con trỏ chuột trên một phần tử, mặc dù có thể áp dụng trên mọi phần tử HTML, tuy nhiên, bộ chọn này hay được áp dụng trên các liên kết, nhằm gây chú ý cho người sử dụng. Ví dụ, liên kết sẽ đổi màu nền khi người dùng rê chuột lên,
```css
a:hover {

color: maroon;

background-color: #ffd9d9;

}
```
_– :active_ áp dụng khi một phần tử (nút hoặc liên kết) đang được bấm chuột. Ví dụ, liên kết sẽ đổi màu nền khi người dùng đang bấm chuột lên,
```css
a:active {

color: red;

background-color: # ffd9d9;

}
```
**CSS cho các trạng thái của một liên kết**

Nhà thiết kế web thường định dạng CSS cho tất cả các trạng thái của một liên kết, nhằm làm cho giao diện sinh động, cuốn hút hơn. Nói chung, tâm lý người dùng luôn muốn nhận lại một kết quả gì đó sau mỗi thao tác của họ, như cập nhật các liên kết họ đã ghé thăm, khi rê chuột lên một liên kết sẽ có hiệu ứng xuất hiện, hoặc khi bấm chuột vào liên kết nó sẽ chuyển màu để báo việc bấm chuột đã có tác dụng.

Chú ý: khi áp dụng các bộ chọn pseudo-class vừa tìm hiểu ở trên cho một liên kết, cần để ý đến thứ tự của các bộ chọn, nếu thứ tự không phù hợp sẽ dẫn đến chúng hoạt động không đúng. Ví dụ, nếu để hai bộ chọn _:link_ và _:visited_ sau cùng, nó sẽ làm mất tác dụng của các bộ chọn khác. Thứ tự của các bộ chọn nên theo là, _:link, :visited, :focus, :hover, :active_

Ví dụ,
```css
a { text-decoration: none; } /* bỏ dấu gạch chân */

a:link { color: maroon; }

a:visited { color: gray; }

a:focus { color: maroon; background-color: #ffd9d9; }

a:hover { color: maroon; background-color: #ffd9d9; }

a:active { color: red; background-color: #ffd9d9; }
```
**Bộ chọn pseudo-class dựa trên cấu trúc tài liệu HTML**

Chúng ta có thể sử dụng bộ chọn pseudo-class để chọn ra các phần tử dựa vào vị trí của nó trong cấu trúc tài liệu HTML. Dưới đây là một số bộ chọn,
```css
_:root_

_:empty_

_:first-child_

_:last-child_

_:only-child_

_:first-of-type_

_:last-of-type_

_:only-of-type_

_:nth-child()_

_:nth-last-child()_

_:nth-of-type()_

_:nth-last-of-type()_
```
Bạn có thể lên mạng để tìm hiểu thêm về các bộ chọn này, hoặc có thể đọc thêm ở đây: _https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#tree-structural_pseudo-classes_

Ví dụ: để chọn phần tử đầu tiên trong một nhóm các phần tử cùng cấp (anh em), chúng ta sử dụng _:first-child_.

[HTML]
```html
    <p>Một số nội dung cần học để làm web front-end</p>

    <ul>

        <li>HTML</li>

        <li>CSS</li>

        <li>JS</li>

        <li>React</li>

    </ul>
```
[CSS]
```css
    li:first-child { color: red; }
```
[Kết quả]

_Dòng chữ HTML có màu đỏ_

**Bộ chọn pseudo-class cho các input của form**

Bộ chọn pseudo-class cho các input của form sẽ chọn ra các phần tử dựa vào thuộc tính HTML và trạng thái của các input trước và sau khi tương tác. Ví dụ,
```css
:autofill

:enabled

:disabled

:read-only

:placeholder-show

_:default_

_:checked_

_:indeterminate_

_:blank_

_:valid_

_:invalid_

_:in-range_

_:out-of-range_

_:required_

_:optional_
```
Ví dụ:
[HTML]
```html
    <div>

        <input _type_="checkbox" _name_="my-checkbox" _id_="opt-in">

        <label _for_="opt-in">Chọn</label>

    </div>
```
[CSS]

    _/* Định dạng label khi người dùng đánh dấu chọn */_
```css
    input:checked + label {

        color: red;

    }
```
    _/* Định dạng ô chọn khi được chọn */_
```css
    input[type="checkbox"]:checked {

        box-shadow: 0 0 0 3px hotpink;

    }
```
**Các bộ chọn pseudo-class khác**

Ngoài 4 bộ chọn chúng ta đã tìm hiểu, còn có nhiều bộ chọn pseudo-class khác. Bạn có thể tìm hiểu thêm ở trên mạng hoặc tại đây: _https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes_
### 3.2.2       Bộ chọn phần tử giả (pseudo-element)
Trong CSS, không chỉ có bộ-chọn-lớp-giả (pseudo-class), mà nó còn có bộ-chọn-phần-tử-giả (pseudo-element). Bộ chọn pseudo-element không chọn các phần tử trong tài liệu HTML, cũng không chọn phần tử dựa vào trạng thái của nó, mà sẽ chọn các đối tượng “giả”, dựa vào vị trí hiển thị của các đối tượng trên cửa sổ trình duyệt. Có nhiều bộ chọn _pseudo-element,_ phần này chúng ta sẽ tìm hiểu một số bộ chọn gồm: _::first-line, ::first-letter, ::before_ và _::after_.
**Bộ chọn ::first-line**

Bộ chọn _::first-line_ được sử dụng để chọn hàng đầu tiên của một phần tử văn bản (khi văn bản hiển thị trên trình duyệt). Tuy nhiên, với bộ chọn này, chỉ có thể áp dụng được các thuộc tính sau,
```css
_color, font, background_
_word-spacing,  letter-spacing, text-decoration_
_vertical-align, text-transform, line-height_
```
Ví dụ,
```css
  p::first-line {
    color: red;
  }
```
**Bộ chọn ::first-letter**

Bộ chọn _::first-letter_ được sử dụng để chọn kí tự đầu tiên của một phần tử văn bản (khi văn bản hiển thị trên trình duyệt). Tuy nhiên, với bộ chọn này, chỉ có thể áp dụng được các thuộc tính sau,

_color, font, text-decoration_

_text-transform, vertical-align, padding_

_background, margin, line-height_

_border, float, letter-spacing, word-spacing_

Ví dụ, chúng ta sẽ làm nổi chữ cái đầu tiên của một đoạn (tạo drop cap):

[HTML]
```html
    <p>Ví dụ, chúng ta sẽ làm nổi chữ cái đầu tiên của một đoạn </p>
```
[CSS]
```css
    p::first-letter {
        color: white;
        background-color: #333;
        border-radius: 2px;
        font-size: 200%;
        box-shadow: 3px 3px 0 yellow;
        padding: 6px 3px;
        margin-right: 5px;
    }
```
**Bộ chọn ::before**

Bộ chọn _::before_ được sử dụng để chèn thêm nội dung vào trước một phần tử mà không cần chỉnh sửa mã nguồn HTML (cái này được gọi là thêm nội dung bằng CSS).

Ví dụ, đoạn mã CSS sau sẽ thêm cụm từ “Đọc thêm: ” vào trước phần tử _p_,
```css
  p::before {
    content: "Đọc thêm: ";
    color: red;
    font-weight: bold;
  }
```
**Bộ chọn ::after**

Bộ chọn _::after_ được sử dụng để chèn thêm nội dung vào sau một phần tử mà không cần chỉnh sửa mã nguồn HTML (cái này được gọi là thêm nội dung bằng CSS).

Ví dụ, đoạn mã CSS sau sẽ thêm cụm từ “(Kết thúc)” vào sau phần tử _p_,
```css
  p::after {
    content: "(Kết thúc)";
    color: red;
    font-weight: bold;
  }
```
### 3.2.3       Bộ chọn dựa vào thuộc tính

Chúng ta có thể tạo bộ chọn dựa vào tên và giá trị thuộc tính của phần tử. Cách làm này giúp tạo ra các bộ chọn rất linh hoạt mà không cần phải thêm thuộc tính _class_ hoặc _id_ vào các phần tử.

**element[attribute]**

Đây là bộ chọn đơn giản, nó sẽ chọn ra các phần tử với tên thuộc tính cụ thể, không quan tâm tới giá trị của thuộc tính.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, có thuộc tính _title_

`img[title] {border: 3px solid;}`

**element[attribute=“giá trị”]**

Bộ chọn này sẽ chọn ra các phần tử với tên và giá trị thuộc tính cụ thể. Vì giá trị có phân biệt chữ hoa/chữ thường nên cần xác định giá trị chính xác.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, có tên thuộc tính là _title_ và giá trị là _“con vịt”_,

`img[title="con vịt"] {border: 3px solid;}`

**element[attribute~=“giá trị”]**

Bộ chọn này sẽ chọn ra các phần tử với tên thuộc tính và một phần giá trị của thuộc tính.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, mà trong giá trị thuộc tính _title_ có chứa từ _“con”_, như vậy, các phần tử _img_ với _title_ có giá trị là _“con gà”_ hay _“ vịt con”_ đều được chọn.

`img[title~="con"] {border: 3px solid;}`

**element[attribute|=“giá trị”]**

Bộ chọn này sẽ chọn ra các phần tử với tên thuộc tính và giá trị thuộc tính sẽ bắt đầu bằng một từ cụ thể, sau đó là dấu gạch nối (hyphen) (-).

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, mà trong giá trị thuộc tính _title_ bắt đầu là từ _“con”_, sau đó là dấu (-), như vậy các phần tử _img_ với _title_ có giá trị là _“con-gà”_ hay _“con-vịt”_ đều được chọn.

`img[title|="con"] {border: 3px solid;}`

**element[attribute^=“phần đầu của giá trị”]**

Bộ chọn này sẽ chọn ra các phần tử, với tên thuộc tính và phần đầu của giá trị được xác định trước.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, mà trong giá trị thuộc tính _src_ bắt đầu là chuỗi _“/images/icons”_.

`img[src^="/images/icons"] {border: 3px solid;}`

**element[attribute$=“phần cuối của giá trị”]**

Bộ chọn này sẽ chọn ra các phần tử, với tên thuộc tính và phần cuối của giá trị được xác định trước.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, mà trong giá trị thuộc tính _src_ kết thúc là chuỗi _“.jpg”_.

`img[src^=".jpg"] {border: 3px solid;}`

**element[attribute*=“một phần giá trị bất kì”]**

Bộ chọn này sẽ chọn ra các phần tử, với tên thuộc tính và một phần bất kì trong giá trị thuộc tính.

Ví dụ, bộ chọn sau sẽ chọn ra tất cả các phần tử _img_, mà trong giá trị thuộc tính _title_ có chứa chuỗi _“on”._ Như vậy các phần tử _img_ với _title_ có giá trị là _“con-gà”_ hay _“con-vịt”_ hay _“anh-chon”_ đều được chọn.

`img[title*="on"] {border: 3px solid;}`
