# TỔNG QUAN CSS

## 1 Tổng quan về CSS

### 1.1 CSS là gì?

CSS (Cascading Style Sheets) là mã định dạng theo kĩ thuật xếp lớp.

CSS là một ngôn ngữ định kiểu, được sử dụng để mô tả kiểu hiển thị (presentation) cho các phần tử trong tài liệu HTML hoặc XML. CSS chỉ dẫn một phần tử HTML sẽ được hiển thị như thế nào trên màn hình, trên giấy hoặc các phương tiện hiển thị khác.

Hiểu đơn giản, chúng ta dùng HTML để tạo ra phần thô của một căn nhà, sau đó dùng CSS để sơn và trang trí cho ngôi nhà.

**Để CSS cho trang web, chúng ta cần thực hiện ba bước sau:**

- Có sẵn tài liệu HTML, nếu chưa có thì chúng ta cần tạo ra tài liệu HTML
- Viết các chỉ dẫn định dạng (style rule, gọi tắt là chỉ dẫn) để mô tả cách thức hiển thị cho các phần tử HTML, bạn muốn phần tử sẽ hiển thị ra trình duyệt như thế nào thì mô tả trong các chỉ dẫn. Ví dụ mô tả về màu sắc, kích thước, vị trí của phần tử.
- Gắn, hay áp các chỉ dẫn vào tài liệu HTML. Khi trình duyệt hiển thị trang web, nó sẽ dựa vào các chỉ dẫn để định dạng các phần tử HTML.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg9J5l-ixKbmwcmdKjGGPKSVwra1OFKYCBsYQ2q5tuafDMZBfVlIrImccyNpTiAc_p3ZkWkFuuxTsYzirpqLj1Nnp25Tw_OjtLxODJvfI3vz47gvdMRwdu3dHpPWtf-13F_1xRP3OGDuZ6tFrdaXRlmuNCO4UReIZvIMrgJGmyd_Km5OUnKjvUMEtBc/w400-h203/ChiDanCSs.jpg)

**Bộ chọn**

*selector* được gọi là bộ chọn dựa theo loại phần tử (element type), là kiểu bộ chọn cơ bản nhất. Nội dung trong phần khai báo của mỗi chỉ dẫn sẽ tác động lên tất cả các phần tử p trong tài liệu HTML. Ở phần sau sẽ tìm hiểu thêm các bộ chọn phức tạp hơn. Trong CSS, việc xác định đúng bộ chọn và sử dụng bộ chọn một cách hợp lý là một kĩ năng quan trọng cần để ý.

**Khai báo**

*declaration* Vì CSS không quan tâm tới các khoảng trắng và dấu xuống hàng dư thừa, vì vậy với khai báo gồm nhiều cặp “thuộc tính: giá trị” thì nên viết mỗi cặp trên một hàng để dễ quan sát mã nguồn.

Viết chỉ dẫn trên một hàng, không có khoảng trắng, chương trình chạy vẫn đúng, nhưng rất khó quan sát mã nguồn.

VD: ```html p{color:red;font-size:54px;}```

Nên viết:

```html
p {

color: red;

font-size: 54px;

}
```

**Thuộc tính**

Thuộc tính (property) chính là tất cả các yếu tố liên quan đến việc định dạng một phần tử HTML, ví dụ màu chữ, màu nền, kích thước phông chữ, vị trí hiển thị…v.v. Tên các thuộc tính được quy định sẵn trong đặc tả của CSS. Chúng ta cần phải học để biết ý nghĩa của mỗi thuộc tính đối với mỗi phần tử HTML. Ví dụ: thuộc tính color dùng để thiết lập màu của chữ, thuộc tính font-size dùng để thiết lập kích cỡ của chữ.  

**Giá trị**

Với mỗi thuộc tính sẽ có các giá trị tương ứng đi kèm.

Ví dụ thuộc tính color sẽ có các giá trị là tên của các màu (ví dụ red, green, blue), thuộc tính font-size sẽ có giá trị là kích thước của chữ được tính bằng px.

 Điều quan trọng chúng ta cần biết là với một thuộc tính thì có thể sử dụng giá trị gì.

*Tóm lại:* với mỗi loại bộ chọn sẽ có các thuộc tính chuẩn đi kèm, và với mỗi thuộc tính sẽ có những giá trị phù hợp, các phần sau sẽ làm quen với một số thuộc tính và giá trị này, đồng thời học cách để sử dụng chúng một cách chính xác và hiệu quả.

**Gắn CSS vào tài liệu HTML**

Gắn CSS vào tài liệu HTML chính là việc chỉ cho trình duyệt biết mã CSS đang được để ở đâu? Để khi biên dịch, trình duyệt có thể tìm được mã CSS để định dạng nội dung hiển thị.

 *Có thể viết mã CSS ở 3 nơi khác nhau:*

- Viết mã CSS ở trong tài liệu HTML
- Viết mã CSS ở ngoài tài liệu HTML
- Viết mã CSS ở trong phần tử HTML

**Viết mã CSS ở trong tài liệu HTML**

Viết mã CSS ở trong tài liệu HTML (embedded style sheets).

Chúng ta đã viết mã CSS trong tài liệu HTML, cụ thể là trong tập tin index.html.

Và dùng phần tử <style> để báo cho trình duyệt biết: mã CSS sẽ đặt ở trong phần tử này. Phần tử <style> phải được đặt trong phần tử <head>. Bằng cách này, mã CSS chỉ áp dụng được cho chính tài liệu HTML chứa nó.

**Viết mã CSS ở ngoài tài liệu HTML**

Viết mã CSS ở ngoài tài liệu HTML (external style sheets) là phương pháp được sử dụng nhiều nhất và có nhiều ưu điểm.

Mã CSS sẽ được viết trong một tập tin riêng, có phần mở rộng là .css, tập tin này được liên kết tới một hoặc nhiều tài liệu HTML bằng phần tử link. Bằng cách này, với một tập tin CSS có thể áp dụng cho nhiều tài liệu HTML khác nhau.

**Viết mã CSS ở trong phần tử HTML**

Viết mã CSS ở trong phần tử HTML (inline style) được thực hiện bằng cách thêm thuộc tính style vào thẻ mở (open tag), nội dung mã CSS chính là giá trị của thuộc tính. Với cách này, mã CSS chỉ áp dụng được cho chính phần tử HTML chứa nó.

Nên tránh sử dụng cách này, trừ một số trường hợp đặc biệt cần phải ghi đè mã CSS của hai phương pháp trên. Vì việc đưa mã định dạng vào trong phần tử HTML sẽ gây ra rất nhiều khó khăn khi cần thay đổi việc hiển thị của toàn bộ trang web.
