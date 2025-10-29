# Front-end 5

## 1.1 Hoàn thiện trang web đơn giản:

### 1.1.1 Phần tử rỗng:

<tên thẻ>nội dung</tên thẻ>

Trong đó, phần “nội dung” thường là văn bản hoặc phần tử HTML khác.
Tuy nhiên, có một số ít các phần tử không có phần nội dung, mà bản thân phần tử đó sẽ là một chỉ dẫn để thực hiện một hành động nào đó,
như xuống dòng, tạo một đường kẻ ngang, hiển thị một hình ảnh, các phần tử này được gọi là phần tử rỗng (empty element).

**Cú pháp của phần tử rỗng có dạng:**

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgLCukzrdoYgyXnAeaD9uRClDgts3gV-Ur7MNdBE5nbXZktiUR7ppPOQzsegY8_Kk2Y0KX1K7v8N6IE5TOZSuBajBH8l-xGLsYKx1q5fad9YsGWJ0Cx3La9Qwdl76ASus32Lxgy-w2nL3E/w400-h113/1_The+rong.jpg)

- Phần tử img, khi trình duyệt gặp phần tử này, nó sẽ tải hình ảnh về và hiển thị lên giao diện.

- Phần tử br, được sử dụng để ngắt dòng, xuống hàng (line break).

- Phần tử meta, được sử dụng để mô tả một số đặc tính của trang web.
Meta là viết rút gọn của metadata. Metadata là siêu dữ liệu, nghĩa là dữ liệu để mô tả dữ liệu.
Cụ thể ở đây là các thông tin để mô tả một số đặc tính của trang web.
Phần tử meta không được hiển thị ra trình duyệt. Trình duyệt, máy tìm kiếm và các dịch vụ web khác sẽ đọc và sử dụng các phần tử meta này.

### 1.1.2 Thuộc tính:

Như đã biết, phần tử img được sử dụng để chèn một hình ảnh vào trang web, tuy nhiên, vì là phần tử rỗng,
nên chỉ với cú pháp <img> thì trình duyệt sẽ không thể biết được là phải lấy hình ảnh nào, lấy ở đâu? Vì vậy,
cần phải sử dụng thêm thuộc tính (attribute) để cung cấp cho trình duyệt biết được tên và vị trí của hình ảnh.

**Minh họa cú pháp của thuộc tính**

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjo57nqt4A4w2szVAtu5fTx4m_qeIQpTTdssd4BlHHiG0JQOOljm5ATpRyGKLTNIB0tPy-xYAaa1QCC42fj0HgdFa9D3LomF098Jj5Jh99eGjL8mkN0vjXfxtjNhNbtJMapVxCxUhsg4Vs/w400-h163/2_Thuoc+tinh.jpg)

- Thuộc tính (attribute) là thành phần bổ sung của mỗi phần tử HTML. Thuộc tính được dùng để thay đổi chức năng mặc định của phần tử hoặc là một thành tố bắt buộc phải có, để một phần tử có thể thực hiện đúng chức năng.

- Thuộc tính luôn được đặt trong thẻ mở. Mỗi phần tử có thể chứa nhiều thuộc tính, mỗi thuộc tính cách nhau bởi một khoảng trắng, tính thứ tự trước sau của các thuộc tính là không quan trọng.

- Hầu hết các thuộc tính đều có giá trị đi kèm, giá trị của thuộc tính nằm sau dấu “=”. Tuy nhiên, trong một số trường hợp, thuộc tính được viết rút gọn chỉ gồm một từ mô tả, ví dụ thuộc tính checked.

- Giá trị của thuộc tính có thể là: văn bản, số, kí tự, URL, đơn vị đo.

- Giá trị của thuộc tính thường được bao lại bằng dấu nháy kép ("") hoặc nháy đơn ('). Mọi người hay sử dụng dấu nháy kép. Tuy nhiên, cũng có một số giá trị không cần phải bao lại bằng dấu nháy.

**Có bốn loại thuộc tính cơ bản gồm:**

- Thuộc tính bắt buộc (required attributes): Là thuộc tính bắt buộc phải có để phần tử thực hiện đúng chức năng của nó.
Ví dụ: thuộc tính href trong phần tử <a>, và <link>

- Thuộc tính tùy chọn (optional attributes): Là thuộc tính được sử dụng để thay đổi chức năng mặc định của một phần tử.
Ví dụ: thuộc tính maxlength trong phần tử <input>

- Thuộc tính chuẩn (standard attributes) hay thuộc tính phổ dụng (global attributes): Là thuộc tính có thể sử dụng được cho
nhiều loại phần tử. Ví dụ: thuộc tính id, class, title.

- Thuộc tính sự kiện (event attributes): Là thuộc tính được sử dụng để kích hoạt một hành động (script) trong các trường
hợp cụ thể. ví dụ: thuộc tính onclick, onload.

### 1.1.3 Hiển thị tiếng việt:

Sử dụng phần tử meta của HTML để khai báo bộ mã hóa kí tự sẽ dùng cho trang web.

Phần tử meta được sử dụng để cung cấp các siêu dữ liệu (metadata) về một trang web.

Siêu dữ liệu là dạng dữ liệu mô tả thông tin chi tiết về dữ liệu.

Để khai báo bộ mã hóa kí tự cho trang web, trong phần tử head thêm dòng mã sau:

<meta charset="utf-8">

**UTF-8**

UTF-8 là viết tắt của 8-bit Unicode Transformation Format (Định dạng chuyển đổi Unicode 8-bit).

UTF-8 là một bộ mã hóa kí tự với chiều rộng biến thiên dành cho Unicode. Tương tự như UTF-16 và UTF-32, UTF-8 có thể 
biểu diễn tất cả các chữ cái trong bộ kí tự Unicode, nhưng điểm khác biệt quan trọng nhất là nó có thể tương thích ngược 
với ASCII. Vì lý do này, UTF-8 nhanh chóng trở thành bộ mã hóa được sử dụng rộng rãi trong các tập tin, thư điện tử, 
trang web, và phần mềm xử lý văn bản.

* [**Hiển thị tiếng Việt**](https://dopaemon.github.io/HTML_ReLearn/Trang_Web_Dau_Tien2.html)

**Một số thông tin thêm về phần tử meta:**

- Phần tử meta phải đặt trong phần tử head.

- Thông tin trong meta không được hiển thị trên trình duyệt.

- Trình duyệt, cỗ máy tìm kiếm và các dịch vụ web khác sẽ sử dụng các thông tin trong meta.

- Meta thường dùng để mô tả trang web, từ khóa, tác giả, bộ mã hóa kí tự, thời gian cập nhật gần nhất, thiết lập khung nhìn,…

- Meta thường dùng để mô tả trang web, từ khóa, tác giả, bộ mã hóa kí tự, thời gian cập nhật gần nhất, thiết lập khung nhìn,…

### 1.1.4 Thêm CSS cho trang web:

Mặc định, khi chúng ta không viết mã định dạng (mã CSS) cho một trang web, thì trình duyệt sẽ lấy các định dạng có sẵn 
của trình duyệt (user agent style sheet) để định dạng cho từng phần tử HTML.

### 1.1.5 Kiểm tra tính hợp lệ của mã HTML

Trong cấu trúc của một tài liệu HTML, hàng đầu tiên là khai báo cho biết nội dung bên dưới sẽ được viết bằng 
HTML phiên bản nào. Dựa vào khai báo này, trình duyệt sẽ sử dụng đặc tả phiên bản HTML tương ứng để biên dịch và 
hiển thị kết quả.

**Bước 1:** Truy cập trang [validator](https://validator.w3.org/) 

**Bước 2:** Dán địa chỉ này vào https://dopaemon.github.io/HTML_ReLearn/Kiem_Tra_HTML.html rồi chọn check.

**Để làm một trang web đơn giản, cần những gì?**

Để làm một trang web đơn giản cần ba thứ sau: ngôn ngữ viết mã (code), công cụ để viết mã, và công cụ để xem kết quả.

- Ngôn ngữ để viết mã là HTML

- Công cụ để viết mã là chương trình soạn thảo văn bản thô (plain text).
Ví dụ: Notepad của Windows, TextEdit của Mac OS, Vi của Linux

- Công cụ để xem kết quả là trình duyệt, có thể sử dụng một trong các
trình duyệt sau: Chrome, Firefox, Safari, Opera, Microsoft Edge

Tóm lại, để làm một trang web đơn giản, chỉ cần sử dụng Notepad để viết mã HTML, lưu lại thành một tập tin 
có phần mở rộng là .html. Sau đó, dùng trình duyệt để mở tập tin, và xem trang web kết quả.

### 1.1.7 BT

**Bài Tập 1** 

* [**Hiển thị tiếng Việt**](https://dopaemon.github.io/HTML_ReLearn/Trang_Web_Dau_Tien2.html)

* [**Kiểm tra html**](https://dopaemon.github.io/HTML_ReLearn/Kiem_Tra_HTML.html)

**Bài Tập 2**

* [**BT2**](https://dopaemon.github.io/HTML_ReLearn/B6_W5_BT2.html)

**Bài Tập 3**

* [**BT3**](https://dopaemon.github.io/HTML_ReLearn/B6_W5_BT3.html)

**Bài Tập 4**

* [**BT4**](https://dopaemon.github.io/HTML_ReLearn/B6_W5_BT4.html)

  
### 1.1.8 Câu hỏi ôn tập

**C1** Trong UTF-8, UTF là viết tắt của các từ nào?

*Unicode Transformation Format*

**C2** Metadata is "data that provides ________about other data". In other words, it is "data about data".

*information*

**C3** Technically, an ________is the collection of start tag, its attributes, an end tag and everything in between. On the other hand an HTML tag (either opening or closing) is used to mark the start or end of an element.

*HTML element*

**C4** Indicate whether each of these filenames is not an acceptable name for a web document.

*cooking home page.html*

**C5** One of the following markup examples is incorrect. Which one?

*<em>Congratulations!<em>*

**C6** Trang web https://validator.w3.org/ dùng để làm gì?

*Để kiểm tra tính hợp lệ của mã HTML*
