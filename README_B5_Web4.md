# Front-end 4

## 1.HTML

### 1.1 Tạo một trang web đơn giản:

**HTML là gì?**

HTML (*HyperText Markup Language*) là ngôn ngữ đánh dấu siêu văn bản (không phải ngôn ngữ lập trình) dùng để tạo nội dung cho môi trường web.

**Tài liệu HTML là gì?**

HTML document là tập tin chứa mã HTML, là trang web ở dạng mã nguồn.<br>

#### 1.1.1 Trang web tĩnh:

Trang web tĩnh (static web page, flag page, stationary page): 
là trang web chứa nội dung cố định, 
nội dung giống nhau với mọi người dùng,
mọi ngữ cảnh.

Mã nguồn của trang web tĩnh thường là tài liệu HTML, 
lưu dưới dạng tập tin.

Mã nguồn của trang web tĩnh có thể được lưu trong cơ sở dữ liệu,
thậm chí bao gồm các trang web được tạo ra bằng mẫu có sẵn (template) và được phân phối thông qua một server ứng dụng,
miễn là các trang kết quả không thể thay đổi.

#### 1.1.2 Chuẩn bị nội dung cho trang web:

**Những thứ trình duyệt bỏ qua khi hiển thị một văn bản**

Chuỗi khoảng trắng (spaces): 
khi gặp một chuỗi khoảng trắng,
trình duyệt chỉ ghi nhận khoảng trắng đầu tiên,
các khoảng trắng sau đó sẽ bị bỏ.

Kí hiệu xuống hàng (line break, carriage return):
Khi gặp 1 hay nhiều kí tự xuống hàng liên tiếp,
trình duyệt sẽ chuyển thành một khoảng trắng.

Các tab cũng được chuyển thành khoảng trắng.

Vì đặc tính bỏ qua chuỗi khonagr trắng,
kí hiệu xuống hàng và tab,
nên phần văn bản hoặc các phần tử nội tuyến (inline element) khác sẽ được đặt cạnh nhau, liên tục, 
và chỉ bị ngắt dòng khi gặp một phần tử khối (block element).

Các thẻ (tag) mà trình duyệt không hiểu cũng bị bỏ qua.
Tuy nhiên trình duyệt sẽ xem nội dung của các thẻ mà nó không nhận ra là dạng văn bản thông thường và trình duyệt sẽ hiển thị nội dung ra giao diện.

Phần chú thích (comment) sẽ bị bỏ qua, không hiển thị.

**Văn bản là gì?**

Văn bản (text) là những thứ có thể đọc được. Văn bản chính là tập hợp các kí tự (letter) hoặc các từ (word) có ngữ nghĩa.

Trong thông tin và truyền thông, văn bản là từ, là câu, là đoạn, không bao gồm thông tin định dạng và được lưu dưới dạng mã ASCII (để máy tính có thể hiểu và xử lý được).

Những thứ không phải là văn bản bao gồm: các đối tượng đồ họa (graphic), các số (không ở dạng ASCII), và mã chương trình (dạng nhị phân).

#### 1.1.3 Cấu trúc cơ bản của một tài liệu HTML

**Phần tử HTML**

Phần tử HTML (HTML element) là một thùng chứa (container), nó được sử dụng để chứa văn bản, và chứa các phần tử HTML khác.

Thùng chứa được tạo ra bằng cách dùng các thẻ HTML. Tên của thẻ sẽ quy định nội dung chứa bên trong mang ý nghĩa gì khi hiển thị.

**Thẻ HTML**

Thẻ HTML (HTML tag) là các từ khóa (keyword), được sử dụng để báo cho trình duyệt biết cách định dạng và hiển thị các nội dung.
Trình duyệt sẽ không hiển thị các từ khóa này ra ngoài giao diện.

*Thẻ HTML thường gồm 2 phần:*

Phần mở thẻ gọi là thẻ mở (opening tag, start tag).

Phần đóng thẻ gọi là thẻ đóng (closing tag, end tag).

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg387_FiMuzl_43ZYdvKCcEjstmarc22ifjVBMwmp761lOsO-ESTVu6SKNpjFaTC5zCJPOvaX8xdfdYT-3rC7AWpnfuvWDJ6tYnRbPWkhPmDLjZvuBdmIMj9E8aDRfMyD9mmWxVk1lgYGs/s698/html1.jpg)

Cũng có thể hiểu nôm na, HTML sẽ sử dụng các thẻ (tag) để “đánh dấu” chỗ này là tiêu đề, chỗ khác là một đoạn văn bản, chỗ này sẽ hiển thị hình ảnh, 
chỗ khác sẽ hiển thị một video. Đây chính là ý nghĩa của chữ “đánh dấu” (markup) trong khái niệm HTML.

Dưới đây là cú pháp một phần tử HTML thông thường (gọi là phần tử HTML thông thường vì còn có các phần tử HTML đặc biệt).

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgPxwmZ-9lpbVqko8FdwA4w8stYJJKBUCgCqDfGk4Epm5M-YoDVPPn-tzqV6YiOYG95arQDG8EZ0RCKa1_m4Vsqh3lEJ9YyFF99XzqmhssTkXmVgjYA_wTZEWNzdODGT8t4BuEclL_-xOo/w400-h140/html2.jpg)

Như vậy, một phần tử HTML sẽ bắt đầu là thẻ mở, tới phần nội dung, và cuối cùng là thẻ đóng.

Thẻ HTML (HTML tag) và phần tử HTML (HTML element) là hai khái niệm khác nhau.

Tuy nhiên, thẻ HTML là thành phần để tạo ra phần tử HTML.

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjCQmRvnlS5YD3D6d702cLcYdfWgL0QxPhB4Z-KPbqD496d-r2PEKQ5_HgFk8FiIFHt4S8fWfx55nBEQLfzPqtM_0Fk5hdjTdVGsbFJpLhTHbYU848o_OLPa1K-wo4Oywbajj71ryz3N3k/w400-h364/html3.jpg)

Một tài liệu HTML luôn được bắt đầu bằng dòng khai báo, mục đích là để cho trình duyệt biết được tài liệu bên dưới được viết bằng HTML phiên bản bao nhiêu. Từ đó, trình duyệt sẽ dùng đặc tả (specification) tương ứng để biên dịch mã HTML. Từ khóa để khai báo là <!DOCTYPE>, đây không phải là một thẻ HTML, bạn có để ý thấy dấu "!" không? các thẻ HTML sẽ không có dấu "!" này.

**Văn bản thô**

Văn bản thô (plain text hay unformatted text) là văn bản ở dạng tự nhiên nhất, không bao gồm thông tin định dạng. Tài liệu word là văn bản đã bao gồm thông tin định dạng, do vậy đó không phải là văn bản thô.

Văn bản thô chính là nguyên liệu để tạo ra mã nguồn các trang web (tài liệu HTML).

**Tài liệu**

Tài liệu (document) là vật mang tin, được hình thành trong quá trình hoạt động của cơ quan, tổ chức, cá nhân.

Các loại tài liệu: văn bản, dự án, bản vẽ thiết kế, bản đồ, công trình nghiên cứu, sổ sách, biểu thống kê; âm bản, dương bản phim, ảnh, vi phim; băng, đĩa ghi âm, ghi hình; tài liệu điện tử; bản thảo tác phẩm văn học, nghệ thuật; sổ công tác, nhật ký, hồi ký, bút tích, tài liệu viết tay; tranh vẽ hoặc in; ấn phẩm và vật mang tin khác.

#### 1.1.4 Thêm cấu trúc và ngữ nghĩa cho nội dung:

HTML có hai chức năng chính, một là tạo ra bố cục hay cấu trúc (structure) cho trang web, hai là tạo ngữ nghĩa (meaning, semantic) cho nội dung.

Tạo bố cục chính là tạo ra phần nội dung cho trang web.

Tạo ra ngữ nghĩa cho nội dung chính là ý nghĩa của các thẻ bạn sử dụng.

Việc sắp xếp vị trí của các nội dung, chia cột, tạo màu sắc, hiệu ứng là chức năng của CSS chứ không phải  của HTML.

**Trang trí nội dung bằng HTML**

Ban đầu, HTML được tạo ra để giúp các nhà khoa học chia sẻ thông tin với nhau, do vậy, chức năng chủ yếu của nó là trình bày văn bản có cấu trúc, dễ đọc.

Tuy nhiên, sau đó, HTML đã được mở rộng, được bổ sung thêm khả năng về định dạng, trang trí, cho phép người lập trình thay đổi phông chữ, màu sắc, căn lề.

Hiện nay, HTML đang được trả lại đúng vai trò ban đầu của nó, nghĩa là HTML chỉ tập trung vào việc biểu diễn nội dung có cấu trúc và có ngữ nghĩa.

#### 1.1.5 Phần tử kiểu block và inline:

phần tử body sẽ chứa toàn bộ nội dung được hiển thị ra màn hình. Phần tử body sẽ chứa tất cả các phần tử tạo ra nội dung trang web. vậy, phần tử body là phần tử cha, trong nó sẽ có các phần tử con.

Ở chế độ mặc định, mỗi phần tử HTML sẽ thuộc một trong hai kiểu hiển thị là block (kiểu khối) hoặc inline (kiểu nội tuyến, trong hàng).

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjdzwURldwbAuqp8fWSGvGLkxKHQDiNToTFiUE9W0a0Yf6jD6gyXB3qwgUdm73VTWYB85ZlE1j3u6PeEQmS6oghFrf7XayofRqGsvEGO_ZETWbbXK310oIjCwdJGV3qltfgNm2dHdW6Xe8/w400-h194/html4.jpg)

**Hiển thị kiểu block**

Một phần tử có kiểu hiển thị là block (block-level) sẽ luôn được hiển thị ở một hàng mới và nó sẽ chiếm toàn bộ chiều rộng khả dụng (nghĩa là chiếm toàn bộ chiều rộng của phần tử cha nó).

**Hiển thị kiểu inline**

Một phần tử có kiểu hiển thị là inline (inline-level) sẽ không yêu cầu một hàng mới khi hiển thị và sẽ chiếm độ rộng vừa đủ để chứa hết phần nội dung của nó.

#### 1.1.7 BT

* [**Bài Tập 1**](https://girrint.github.io/Hoc_thiet_ke_Web/Trang_Web_Dau_Tien.html)

* [**Bài Tập 2**](https://girrint.github.io/Hoc_thiet_ke_Web/B5_W4_BT2.html)

* [**Bài Tập 3**](https://girrint.github.io/Hoc_thiet_ke_Web/B5_W4_BT3.html)

* [**Bài Tập 4**](https://girrint.github.io/Hoc_thiet_ke_Web/B5_W4_BT4.html)

#### 1.1.8 Câu hỏi ôn tập

**C1** A static web page (sometimes called a flat page or a stationary page) is a web page that is delivered to the user's web browser exactly as stored, in contrast to __________ which are generated by a web application.

*dynamic web pages*

**C2** Một phần tử HTML (thông thường) gồm các thành phần sau:

*thẻ mở, nội dung, thẻ đóng*

**C3** Cấu trúc cơ bản của một tài liệu HTML gồm:

*Phần khai báo (doctype), phần tử html, phần tử head, phần tử title, phần tử body*

**C4** Phát biểu nào sau đây là hợp lý:

A. HTML tạo ra cấu trúc và ngữ nghĩa cho phần nội dung trang web

B. HTML thực hiện việc trang trí cho trang web

C. HTML xử lý các tương tác của người dùng trên giao diện web

D. HTML vừa tạo ra phần nội dung vừa thực hiện trang trí cho trang web

*Đáp án: A*

**C5** Phát biểu nào đúng khi nói về “<!DOCTYPE html>”?

*Là một khai báo trong tài liệu HTML*
