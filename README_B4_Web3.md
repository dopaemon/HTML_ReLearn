# Front-end 3

## 1.1 URL, siêu liên kết và siêu văn bản:

Web là không gian thông tin toàn cầu. Không gian thông tin này được tạo bởi một mạng lưới gồm nhiều tài nguyên kết nối với nhau.
Mỗi một tài nguyên được định vị bằng một địa chỉ duy nhất, gọi là URL.

### 1.1.1 URL

URL(Uniform Resource Locator),  “bộ định vị tài nguyên thống nhất”, hiểu nôm na là “địa chỉ của một tài nguyên web”, hay địa chỉ web (web address).

URL là một tham chiếu tới tài nguyên web, 
cho biết một tài nguyên web nằm ở đâu trên hệ thống mạng 
và dùng giao thức (hay phương thức) gì để lấy (hay truy cập) được tài nguyên đó.

Một số giao thức có sử dụng URL như HTTP để truy cập web,
FTP để truyền tập tin, mailto để gửi email, JDBC để truy cập cơ sở dữ liệu.

URL cũng xuất hiện trong các thẻ của HTML, như các thẻ: <a href=URL>, <img src=URL>, <script src=URL>, <link href=URL>.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRmzNxBTrylqOwoQnfI3GQ-dM5NVu8LpZnd2NVQySzKNnBrlVMNDPHqkQlyJ8WkGPe1y5B9nEcWjXcEq4EjfU_BD6ALUOG-Vg1l7YXuM2k-34NLKIH2Jr04M2SEKApIDj7BaLQmclTV38/w400-h84/Dinh+dang+cua+URL+1.jpg)

- Scheme là giao thức được sử dụng để trao đổi thông tin giữa client và server. 
Một số scheme phổ biến: http, https, ftp, file, mailto, data, irc. 
Scheme được ngăn cách với các thành phần phía sau bằng dấu “://”.

- Domain (hay domain name) là tên miền của máy server, cũng được gọi là hostname.  
Máy tính của người dùng sẽ đổi tên miền này thành địa chỉ IP để nó có thể tìm thấy và giao tiếp với máy server.

- Port là cổng, được sử dụng để giao tiếp giữa client và server.
Trong giao thức HTTP nếu không chỉ định rõ, thì giá trị của port sẽ được ngầm hiểu là 80, giao thức HTTPS là 443.

- Path là đường dẫn (đường dẫn thư mục, đường dẫn tuyệt đối) của tài nguyên web trên máy server.
Đường dẫn luôn bắt đầu bằng dấu xuyệt (slash) (/),
có nghĩa là thư mục gốc, mỗi thư mục ngăn cách nhau bằng một dấu “/”.

- URL cũng có thể chứa chuỗi truy vấn hoặc một định danh.
Chuỗi truy vấn (query string) là chuỗi chứa các cặp key=value, nằm ngay sau dấu ?,
 Định danh vùng nội dung (fragment_id) là một vị trí trên một trang web,
 được đánh dấu bằng một cái tên cụ thể, ví dụ một vùng trên trang web có tên là #noi-dung.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj5rhcl0AmAOB6JEIEfnA85OAJLR_X06W4EVdj4skbAwGxnTsrLTHdqrrjm7HSUjurIQ7TCRtkJBAbhImd75agr0_5lWuwujGws_RUVPFfZuOBGskVVnYf7qDegLgcIOmxY7lXFESPUrzQ/w400-h171/Vi+du+URL+2.jpg)

URL là tập con của URI, cộng đồng đang có xu hướng chuyển qua sử dụng URI thay cho URL. 
URI chính xác và tổng quát hơn URL. 
Tuy nhiên, nhiều người vẫn thích sử dụng khái niệm URL hơn. Bạn có thể sử dụng URL và URI thay thế cho nhau.

### 1.1.2 Giao thức File:

Vì URL là một tham chiếu tới tài nguyên web, trong trường hợp này là tham chiếu tới một trang web. URL cho biết vị trí của trang web trên hệ thống mạng và để lấy được trang web đó thì cần sử dụng giao thức gì. Vậy ở đây, trình duyệt đã không dùng giao thức HTTP, hoặc HTTPS để lấy nội dung trang web mà dùng giao thức File.

Giao thức File có tên đầy đủ là giao thức File URI, được đặc tả trong RFC 1630 và RFC 1738, sử dụng để truy cập và lấy về nội dung của thư mục hoặc tập tin bất kì.

**Cú pháp của giao thức File có dạng:**

file://host/path

**Trong đó:**

- host là tên của máy tính dạng FQDN (tên miền dạng đầy đủ)
- path là đường dẫn thư mục

Nếu tham số host không được cung cấp, giao thức File sẽ ngầm hiểu là truy cập tại máy tính cục bộ (“localhost”).

### 1.1.3 Siêu liên kết:

Siêu liên kết (hyperlink) hay liên kết (links) là một tham chiếu đến tài liệu, hoặc tài nguyên web, người dùng có thể bấm vào các liên kết này để mở nội dung được liên kết. Một liên kết có thể trỏ đến tài liệu khác hoặc một vị trí cụ thể bên trong tài liệu.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhFl4fpzxGgyTD-G08H-LCO-4ihb1aMKhZxu6Q1ur6zBKW4ZbcLRcZ0mkwWpJKejonHETFFCekM1QzmcKehD8JQVyHO6yqRlwHau4xrRDryy0Fv4q1Sw3o0eA_-e3HNDTYBdTNSOisFGeA/w400-h204/Sieu+lien+ket+3.jpg)

### 1.1.4 Siêu văn bản:

Siêu văn bản (hypertext) là văn bản, được hiển thị trên màn hình máy tính hoặc các thiết bị điện tử khác, có chứa tham chiếu (liên kết) tới các văn bản khác.

Với văn bản thông thường, nội dung của văn bản được tổ chức theo kiểu tuần tự, nghĩa là bạn cần đọc theo thứ tự từ trước đến sau. Tuy nhiên, với siêu văn bản, nhờ các siêu liên kết bạn có thể đọc các nội dung không theo trình tự.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg8UcR3T8PF-dzAaeyTOtTzT1CTmHfFK9wpXMFnChF-V4Nnqzt-k01xr0ffDzKNu05UPSe0qlOfi_VtoQ4SVkp-vb3esKqwJfW9Bg3ztq79C9o_1EKaMVzdv96_S-Ku_dEkfwEXhGX4FKY/w400-h259/Sieu+van+ban+4.jpg)

### 1.1.6 BT

* [**Bài tập 3**](https://girrint.github.io/Hoc_thiet_ke_Web/B4_W3_BT3.html)

### 1.1.7 Câu hỏi ôn tập

**C1** A Uniform Resource Locator (URL) is a reference to a web resource that specifies its location on a computer network and a _______ for retrieving it.

*mechanism*

**C2** Các thành phần thường có trong một URL gồm?

*scheme, fragment_id, query_string, path, port, domain*

**C3** Khi mở tập tin C:\index.html bằng trình duyệt, giao thức trình duyệt đã sử dụng trong URL là?

*file*

**C4** Khi mở tập tin C:\index.html bằng trình duyệt, tại sao lại có ba dấu xuyệt (///) liền nhau?

*Do lược bỏ tên của máy tính (localhost)*

**C5** In computing, a hyperlink, or simply a link, is a ___________ to data that the user can follow by clicking or tapping. A hyperlink points to a whole document or to a specific element within a document.

*reference*

**C6** Hypertext is _______displayed on a computer display or other electronic devices with references (hyperlinks) to other text that the reader can immediately access. Hypertext documents are interconnected by hyperlinks, which are typically activated by a mouse click, keypress set, or screen touch. Apart from text, the term "hypertext" is also sometimes used to describe tables, images, and other presentational content formats with integrated hyperlinks.

*text*
