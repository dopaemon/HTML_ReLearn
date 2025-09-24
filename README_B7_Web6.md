# Web front-end (6)

## 1.1 Hiển thị văn bản

Để hiển thị văn bản, bạn cần biết cách sử dụng phần tử HTML phù hợp (đặc biệt là về mặt ngữ nghĩa của phần tử) 
để hiển thị các đoạn văn bản, các đề mục, các danh sách, các kí tự đặc biệt, tổ chức trang nội dung.

Việc sử dụng phần tử một cách hợp lý sẽ giúp trang web có thứ hạng cao trong kết quả của các trang tìm kiếm (ví dụ google),
được nhiều người biết đến, và các phần mềm phân tích nội dung có thể tự động phân tích trang web với độ chính xác cao.

**Phần này sẽ đề cập đến các nội dung:**

– Đoạn văn bản và đề mục

– Danh sách

– Một số phần tử hiển thị nội dung khác

### 1.1.1 Đoạn văn bản và đề mục

**Đoạn văn bản**

đoạn văn bản (gọi tắt là đoạn) là tập hợp của nhiều câu, toàn bộ văn bản chính là tập hợp của các đoạn. Trong HTML,
đoạn là một chuỗi các từ có chiều dài bất kì. Để tạo một đoạn, sử dụng phần tử p, đây là phần tử cơ bản nhất
trong việc hiển thị văn bản. Chữ p là viết tắt của paragraph.

**Lưu ý:** tất cả nội dung văn bản đều phải được bọc lại bằng các phần tử, nếu không, phần văn bản đó sẽ không có ngữ nghĩa và 
người lập trình sẽ không thể kiểm soát được việc hiển thị.

Ở chế độ mặc định, phần tử p được hiển thị theo kiểu khối (block). Nghĩa là, nó sẽ luôn được hiển thị ở một hàng mới và sẽ 
chiếm toàn bộ chiều rộng khả dụng.

Phần tử p ngoài việc chứa văn bản (text), nó còn có thể chứa hình ảnh, các phần tử nội tuyến (inline); tuy nhiên,
nó không thể chứa phần tử đề mục (heading), danh sách (list), phân vùng (sectioning), và các phần tử kiểu khối khác.

**Đề mục**

Một văn bản không chỉ có các đoạn, hình ảnh, mà còn có hệ thống đề mục (hay hệ thống tiêu đề).

Đề mục (heading) là một từ, cụm từ, hoặc kí hiệu, giúp người đọc có thể tìm kiếm và định vị được thông tin.

Hệ thống đề mục thường gồm nhiều cấp khác nhau, thể hiện cấu trúc, bố cục, hay bộ khung (outline) của một văn bản. 
Để dễ hiểu, hãy liên tưởng tới hệ thống heading trong Microsoft Word.

Để tạo đề mục, có thể sử dụng các phần tử: h1, h2, h3, h4, h5, h6. Đây là sáu loại đề mục khác nhau. 
Trong đó, phần tử h1 sẽ tạo ra đề mục mức cao nhất (heading level 1 – đề mục mức 1), h2 sẽ tạo ra đề mục mức 2, h3 
sẽ tạo ra đề mục mức 3…

Khi có các đề mục, trình duyệt sẽ sử dụng chúng để tạo ra bố cục cho văn bản.

Phần mềm đọc văn bản tự động (screen reader) sẽ dựa vào các đề mục để tóm tắt nội dung và dễ dàng duyệt qua toàn bộ văn bản.
Các công cụ tìm kiếm cũng sử dụng hệ thống đề mục trong thuật toán tìm kiếm của chúng, các đề mục mức cao hơn sẽ có trọng số lớn hơn.

**Đánh đấu kết thúc chủ đề**

Để đánh dấu kết thúc một chủ đề/ý tưởng và chuyển sang chủ đề/ý tưởng khác, sử dụng phần tử hr, phần tử này sẽ tạo một đường 
kẻ ngang (horizontal rule) giữa hai chủ đề/ý tưởng.

Nếu bạn chỉ muốn tạo một đường kẻ ngang trên trang web thì bạn sẽ dùng border trong CSS chứ không nên sử dụng phần tử hr.

### 1.1.2 Danh sách

Trong khi trình bày một văn bản, bạn rất hay gặp phải tình huống cần phải liệt kê hàng loạt các đối tượng.

**HTML cung cấp ba loại danh sách:**

– Danh sách không có thứ tự (unordered list)

– Danh sách có thứ tự (ordered list)

– Danh sách mô tả (description list)

Mặc định, phần tử danh sách được hiển thị theo kiểu khối (block), tuy nhiên, có thể thay đổi kiểu hiển thị bằng CSS.

**Danh sách không có thứ tự**

Danh sách không có thứ tự là một dãy các mục (item), trong đó tính trước sau của mỗi mục là không quan trọng.

Mỗi mục thường được trình duyệt đánh dấu bằng một kí tự đầu dòng (dấu đầu dòng) (bullet). Trong thực tế, phần lớn các danh sách sẽ thuộc loại này.

Để tạo danh sách không có thứ tự, sử dụng phần tử ul, viết tắt của unordered list (danh sách không có thứ tự).

Để tạo mỗi mục của danh sách, sử dụng phần tử li, viết tắt của list item (mục của danh sách).

**Cú pháp là**
```html
<ul>

            <li>phần tử 1</li>

            <li>phần tử 2</li>

</ul>
```

Mặc định, mỗi mục sẽ được trình duyệt đánh dấu bằng dấu chấm tròn (trên mã nguồn thì không xuất hiện các dấu này), 
nếu muốn thay bằng dấu khác cần sử dụng CSS.

**Chú ý:** sau thẻ mở <ul> phải là một hoặc nhiều phần tử li, chứ không cho phép chèn văn bản hoặc các phần tử khác, 
tuy nhiên, trong phần tử li thì có thể chứa văn bản hoặc các phần tử bất kì. Ví dụ, đoạn mã dưới đây là không hợp lệ.

**danh sách có thứ tự**

Danh sách có thứ tự là một dãy các mục, trong đó tính trước sau của mỗi mục là quan trọng, 
ví dụ, danh sách các bước hướng dẫn để làm một công việc.

 Để thể hiện tính thứ tự của các mục, trình duyệt sẽ tự động sử dụng các số hoặc các chữ cái để gắn vào phía trước mỗi mục,
 giá trị của các số/chữ sẽ được tự động tăng cùng với các mục.

Để tạo danh sách có thứ tự, sử dụng phần tử ol, viết tắt của ordered list (danh sách có thứ tự).

Để tạo mỗi mục của danh sách, sử dụng phần tử li, viết tắt của list item (phần tử của danh sách).

**Cú pháp là**

<ol>

            <li>phần tử 1</li>

            <li>phần tử 2</li>

</ol>

Để ý là, mặc dù trong đoạn mã HTML không ghi các số 1, 2, 3, nhưng khi hiển thị ra màn hình lại thấy có các số. 
Như đã nói ở trên, trình duyệt đã tự đánh số thứ tự cho mỗi mục trong thẻ <ol>. Nếu không muốn đánh số thứ tự là 1, 2, 3,
mà muốn là a, b, c, hoặc I, II, III, thì sử dụng CSS.

Sau thẻ mở <ol> phải là một hoặc nhiều phần tử li, không cho phép chèn văn bản hoặc các phần tử khác, tuy nhiên,
trong phần tử li thì có thể chèn văn bản hoặc các phần tử bất kì trong đó.

Với danh sách có thứ tự, giá trị bắt đầu luôn là 1, I, i, A hoặc a. Để thay đổi giá trị bắt đầu, sử dụng thuộc tính start.

```html
<ol start="gia_tri_thay_doi">
```

| HTML   | Kết quả |
| -------- | ------- |
| ```html <ol type="i" start="4"> ```| Danh sách sẽ được đánh số bắt đầu từ iv   |
| ```html <ol type="I" start="4"> ```| Danh sách sẽ được đánh số bắt đầu từ IV   |
| ```html <ol type="A" start="4"> ```| Danh sách sẽ được đánh thứ tự từ chữ D    |
| ```html <ol type="a" start="4"> ```| Danh sách sẽ được đánh thứ tự từ chữ d    |

**Danh sách mô tả**

Danh sách mô tả **(description list, definition list)** là loại danh sách được sử dụng để biểu diễn dữ liệu theo kiểu từng cặp tên/giá trị (name/value)

**Để tạo danh sách kiểu mô tả, sử dụng ba phần tử sau:**

– dl để tạo danh sách, dl viết tắt của description list hoặc definition list

– dt để tạo một mục cho danh sách (tên), dt viết tắt của description term hoặc definition term

– dd để tạo phần định nghĩa/mô tả cho một mục (giá trị), dd viết tắt của describe a definition hoặc define a description.

**Cú pháp là**
```html
<dl>

            <dt>mục từ 1</dt>

            <dd>định nghĩa cho mục từ 1</dd>

<dt>mục từ 2</dt>

            <dd>định nghĩa cho mục từ 2</dd>

</dl>
```

**Chú ý:** phần tử dl chỉ chứa các phần tử dt và dd. Một mục tên (dt) có thể có nhiều giá trị (dd) hoặc ngược lại. Phần tử dt không thể chứa các phần tử Đề mục (heading), hoặc các phần tử nhóm nội dung (content-grouping element, ví dụ p) tuy nhiên, phần tử dd thì có thể chứa phần tử bất kì.

**Danh sách lồng nhau**

Một danh sách có thể chứa danh sách khác, miễn là danh sách con phải được đặt trong phần tử li của danh sách cha.

Thực tế, ngoài việc tạo ra các thông tin kiểu liệt kê, bạn có thể sử dụng phần tử danh sách (ol, ul) để tạo ra các thành phần khác của trang web, như menu, breadcrumb (một loại điều hướng, giúp người dùng xác định vị trí hiện tại của họ trong website).

### 1.1.3 Một số phần tử hiển thị nội dung khác

Ở các phần trước, đã đề cập tới một số phần tử cốt lõi để hiển thị văn bản như: đoạn, đề mục, danh sách. Phần này sẽ tìm hiểu thêm một số phần tử HTML để hiển thị văn bản nữa, gồm: blockquote, pre, figure, figcaption. Rất khó để xếp những phần tử này vào một loại nào đó, tuy nhiên, chúng đều có hai đặc điểm, một là được hiển thị kiểu khối (block) và hai là được sử dụng để nhóm nội dung (grouping content).

**Hiển thị một trích dẫn dài (long quotations)**

Để đánh dấu và hiển thị phần nội dung được trích dẫn dài (trích dẫn gồm nhiều hàng) từ nguồn khác, lời nhận xét của khách hàng **(testimonial)**, và phần sao chép từ nguồn khác, bạn sẽ sử dụng phần tử **blockquote**. *Nội dung bên trong phần tử **blockquote** nên được bọc lại bằng các phần tử HTML khác như p, heading, ol, ul, dl.*

**Hiển thị văn bản được định dạng sẵn**

Như đã biết, khi biên dịch mã HTML để hiển thị, trình duyệt sẽ bỏ qua các khoảng trắng và các kí tự xuống hàng dư thừa.

Vì vậy, với một số văn bản mà nhất thiết phải giữ các khoảng trắng, và các kí tự xuống hàng.

*Ví dụ:* như một đoạn mã chương trình, một bài thơ, thì hãy sử dụng phần tử pre.

Khi gặp phần tử pre, trình duyệt sẽ hiển thị ra đúng những gì đang có ở dạng mã nguồn.

Cả nội dung và hình thức trình bày, nghĩa là giữ nguyên tất cả các khoảng trắng và các kí tự xuống hàng.

Phần tử pre thuộc kiểu hiển thị khối, phông chữ mặc định được sử dụng là loại phông mà các kí tự có độ rộng bằng nhau, thường được gọi là monospace (ví dụ Courier). Pre là viết tắt của preformatted text.

**Phần tử figure và figcapion**

Phần tử figure là phần tử hiển thị kiểu khối, nó có thể chứa hình ảnh, đoạn mã, video, bảng, hoặc các loại dữ liệu khác, dùng để minh họa thêm cho nội dung được đề cập trong văn bản.

*Ví dụ:* sau khi trình bày về “cấu trúc của một tài liệu HTML gồm những thành phần nào”, để dễ hiểu bạn sẽ dùng phần tử figure để chèn thêm một cái hình, minh họa về cấu trúc của một tài liệu HTML. 

Nếu cần thêm chú thích cho: hình ảnh, đoạn mã, video hoặc bảng, nằm trong phần tử figure thì sử dụng phần tử figcaption.

Phần tử figcaption có thể nằm trước hoặc sau phần nội dung mà nó chú thích.

Caption có nghĩa là chú thích (từ comment cũng có nghĩa là chú thích, nhưng là chú thích cho đoạn mã). 

Từ figure có nghĩa là hình ảnh, hình minh họa (thường được đánh số) trong các cuốn sách. Ví dụ, xem minh họa trong hình 10 (figure 10).

### 1.1.5 BT

**Bài tập 1**

**Bài tập 2**

**Bài tập 3**

### 1.1.6 Câu hỏi ôn tập

**C1** Trong HTML, chữ "hr" trong phần tử hr là viết tắt của chữ nào ?

 Horizontal Rule

 **C2** Trong HTML, chữ “pre” trong phần tử pre là viết tắt của chữ nào?

 Preformatted text

 **C3** Trong HTML, chữ ‘dl” trong phần tử dl là viết tắt của chữ nào?

 Description list

 **C4** Trong HTML, chữ ‘ul” trong phần tử ul là viết tắt của chữ nào?

 unordered list

 **C5** Trong HTML, chữ ‘ol” trong phần tử ol là viết tắt của chữ nào?

 ordered list
 
