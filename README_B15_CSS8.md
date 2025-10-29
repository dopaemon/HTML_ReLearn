# BỘ CHỌN

## 2.3 Bộ chọn

### 2.3.1 Các loại bộ chọn

- Bộ chọn cơ bản (basic selector).
- Bộ chọn gộp (grouping selector).
- Bộ chọn tổ hợp (combinator).
- Bộ chọn theo trạng thái (pseudo-class, pseudo-element).

**Bộ chọn cơ bản**

|**Bộ chọn**|**Cú pháp**|
|-----------|-----------|
|Bộ chọn phổ quát (universal selector): chọn mọi phần tử| `* {}` ` ns \| * {}` `* \| * {}`|
|Bộ chọn theo tên phần tử (type selector, element selector): chọn các phần tử theo tên.|`elementname {}`|
|Bộ chọn theo class: chọn các phần tử theo giá trị của thuộc tính class|`.classname{}`|
|Bộ chọn theo ID: chọn phần tử theo giá trị của thuộc tính ID|`#idname{}`|
|Bộ chọn theo thuộc tính (attribute): chọn các phần tử theo tên, hoặc giá trị của thuộc tính|`[attr]  [attr=value]  [attr~=value]  [attr\|=value]  [attr^=value]  [attr$=value] [attr*=value]`|

**Bộ chọn gộp**

Trường hợp cần định dạng giống nhau cho nhiều phần tử HTML giúp dễ đọc và rút gọn mã nguồn. Sử dụng dấu phẩy (,) để ngăn cách giữa các bộ chọn.

*VD:*

`p, h1, div { color: red; }`

**Bộ chọn tổ hợp**

|**Bộ chọn**|**Cú pháp**|
|-----------|-----------|
|Bộ chọn theo hậu duệ (descendant combinator): chọn các phần tử là hậu duệ (con, cháu, chắt,…v.v) của một phần tử|`A B{}`|
|Bộ chọn gồm các con trực tiếp (child combinator)|`A > B{}`|
|Bộ chọn gồm các “phần tử em” (general sibling combinator): chọn các phần tử cùng cha, nằm bên phải một phần tử|`A ~ B{}`|
|Bộ chọn gồm một "phần tử em" (adjacent sibling combinator)|`A + B{}`|

**Bộ chọn theo trạng thái**

- Bộ chọn lớp giả (pseudo class): chọn “lớp giả” là các trạng thái của phần tử, ví dụ a:visited{} sẽ chọn các phần tử a đã được người dùng duyệt qua
- Bộ chọn phần tử giả (pseudo element): chọn các "phần tử giả", là các phần tử không tồn tại trong tài liệu HTML, ví dụ p::first-line{} chọn hàng đầu tiên của phần tử p

### 2.3.2 Cú pháp của bộ chọn

- Bộ chọn đơn (simple selector): là các bộ chọn chỉ gồm một thành phần. Ví dụ: các bộ chọn cơ bản, bộ chọn theo trạng thái.
- Bộ chọn hỗn hợp (compound selector): là bộ chọn gồm một dãy liên tục (không có khoảng trắng) các bộ chọn đơn. Ví dụ a#selected {} // chọn các phần tử có tên là a và có thuộc tính id="selected"
- Bộ chọn phức (complex selector): là bộ chọn gồm một hoặc nhiều bộ chọn đơn/bộ chọn hỗn hợp, ngăn cách nhau bằng các dấu tổ hợp. Ví dụ: a#selected > .icon {},  .box h2 + p {}
- Bộ chọn gộp (gộp các bộ chọn): là một dãy các bộ chọn, ngăn cách nhau bằng dấu phẩy (,). Ví dụ: #main, article.heading {}.

