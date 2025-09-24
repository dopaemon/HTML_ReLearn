# Web front-end (7)

## 1.1 Bố cục một trang web

Cấu trúc cơ bản của một tài liệu HTML gồm các phần tử html, head, title và body. Trong đó, phần tử body chứa toàn bộ nội dung sẽ hiển thị ra màn hình, đó là phần nội dung các trang web. Trang web ở dạng mã nguồn được gọi là tài liệu HTML.

Nội dung của trang web rất đa dạng.

*Ví dụ:* có thể là một tờ báo, trang blog, trang thông tin của một công ty, giao diện game, các sản phẩm của một cửa hàng.

Phần này sẽ tập trung tìm hiểu cách tạo ra một trang web có bố cục cơ bản nhất. Dựa trên đó, bạn có thể tùy chỉnh cho từng trang web cụ thể.

### 1.1.1 Các phần tử tạo bố cục trang web

Trước khi HTML5 ra đời, để nhóm (grouping) các phần tử lại với nhau, nhằm tạo các vùng lớn hơn của một trang web, người ta thường sử dụng phần tử div.

Tuy nhiên, HTML5 đã cung cấp hàng loạt các phần tử, với ngữ nghĩa rõ ràng hơn, để chia (sectioning) nội dung thành các vùng (section) riêng biệt, phần này sẽ tìm hiểu các phần tử như: main, header, footer, section, article, nav, aside, address.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhvRI5MjxTNai5QbSWL9LygHK7iwmMjC2TCiqw9Aftd0GWhgXy_IEJB3E0dIDB8_eUS-o2XLx8tFXZB79dkq9O1f1sGveVGsxSSVTX5z8N4gR46we92H4acFeqH5UulKFPTAzmjO3VqaqJc3CeSCgkFBLdoihTQOM4xTYuIdEoKIZePDQMxBUNfv77L/w400-h289/Nhom_1.jpg)

Để dễ hiểu về các phần tử tạo bố cục trang web, phần này minh họa theo một bố cục hay cấu trúc (layout) của một trang web phổ biến. Trang web này được chia thành các vùng: Main content, Header, Sidebars, Footer.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizFAgO9XDyiDeCFbkqffIdeXYXuKFaYnQEyfc1uLny5FX8oyr9mz4HrI839Dx-HN1PzT6zjBblem4ZCbnjkRriX1qR0egSNNu1dyw-Hmh1lW4fxwr6HH-Pg0BHsfYrHuciHjGILhOIxQWW-Qxosj2CnfCFkxFDmK4Jewif7cZQnZfkgkpXRX1KxnDX/w400-h353/Nhom2.jpg)

**Vùng nội dung chính (main content)**

Trong một website, nội dung các vùng tiêu đề (masthead, header), khung nội dung bổ trợ (sidebar), vùng quảng cáo (ads), và vùng cuối/chân trang (footer) thường xuất hiện nhiều lần, trong nhiều trang web (web page).

*Riêng vùng nội dung chính (main) chỉ xuất hiện một lần.*

Trong HTML, sử dụng phần tử main để tạo vùng Main.

Các phần tử header, sidebar, và các phần tử xuất hiện ở nhiều trang, thì không nên để trong phần tử main.

Phần tử main không nên lồng trong các phần tử article, aside, header, footer và nav.

**Phần đầu và phần chân (headers và footers)**

Đây là hai phần tử được đặt ở đầu và cuối của một vùng nội dung, nhằm tạo ra cấu trúc rõ ràng cho vùng nội dung đó.

**Phần đầu (headers)**

Phần tử header thường dùng để chứa nội dung giới thiệu, tuy nhiên, trong thực tế nó có thể chứa mọi thứ, miễn là liên quan đến mục đích giới thiệu.

*Ví dụ:* logo, tiêu đề, khẩu hiệu, thanh điều hướng. Phần tử này thường được đặt ở đầu của trang web, hoặc phía trên cùng của một vùng (section) hoặc một bài viết (article).

*Ví dụ:* sử dụng phần tử header để chứa logo, tiêu đề của trang web và thanh điều hướng.

```html
<header>
            <img src="/images/logo.png">
            <h1>Trang blog của Tèo</h1>
            <nav>
                        <ul>
                                    <li><a href="">Home</a></li>
                                    <li><a href="">Blog</a></li>
                                    <li><a href="">About</a></li>
                        </ul>
            </nav>
</header>
```

Trong một article, phần tử header thường được dùng để chứa: tiêu đề, tác giả, và ngày xuất bản của bài viết.

```html
<article>
            <header>
                        <h1>Tiêu đề bài viết</h1>
                        <p>người viết Nguyễn Văn Tèo</p>
                        <p>ngày xuất bản: 11/11/2022</p>
            </header>
            <p>...phần nội dung bài viết…</p>
</article>
```

**Phần chân (footers)**

Phần tử footer dùng để chứa các thông tin ở cuối một trang web, cuối một vùng (section) hoặc cuối một bài viết (article).

Phần tử footer thường chứa tên tác giả, thông tin bản quyền (copyright), các tài liệu liên quan, hoặc các điều hướng (navigation).

Phần tử footer đặt ở cuối trang thì sẽ là thông tin kết thúc của toàn trang.

Nó cũng có thể được đặt ở cuối một section, article, nav, hoặc aside và sẽ là thông tin kết thúc của chính phần tử chứa nó. 

*Ví dụ:* phần chân của một bài viết trên blog.

```html
<article>
            <header>
                        <h1>Tiêu đề bài viết</h1>
                        <p>người viết Nguyễn Văn Tèo</p>
                        <p>ngày xuất bản: 11/11/2018</p>
            </header>
            <p>...phần nội dung bài viết…</p>
            <footer>
                        <p><small>Copyright &copy;2018 Tèo.</small></p>
                        <nav>
                                    <ul>
                                                <li><a href="">Previous</a></li>
                                                <li><a href="">Next</a></li>
                                    </ul>
                        </nav>
            </footer>
</article>
```

**Phân vùng (section)**

Với một tài liệu dài, bạn nên chia nhỏ nó ra thành nhiều phần thì sẽ dễ hiển thị và dễ đọc hơn.

Giả sử nội dung của trang web là một cuốn sách, thì việc chia nội dung thành nhiều chương sẽ giúp bạn làm việc với nó thuận tiện và chuyên nghiệp hơn; hoặc một trang báo với nhiều tin tức thì việc chia thành các chuyên mục cũng giúp nó trở nên chuyên nghiệp, dễ đọc. Để thực hiện việc chia này, bạn sử dụng phần tử section.

Phần tử section dùng để chia nội dung thành các vùng theo các chủ đề khác nhau.

Mỗi phần tử section thường bao gồm heading (h1-h6) và phần nội dung.

**Cú pháp**

```html
<section>
                        <h1>Tên chủ đề</h1>
                        <p>Nội dung của chủ đề</p>
            </section>      
```

*Ví dụ:*

```html
<section>
                        <h1>Chương 1</h1>
                        <p>Nội dung của chương 1</p>
            </section>
            <section>
                        <h1>Chương 2</h1>
                        <p>Nội dung của chương 2</p>
            </section>      
```

*Ví dụ về phần tử section, lấy từ W3Schools*

```html
<section>
  <h1>WWF</h1>
  <p>The World Wide Fund for Nature (WWF) is an international organization working on issues regarding the conservation, research and restoration of the environment, formerly named the World Wildlife Fund. WWF was founded in 1961.</p>
</section>
<section>
  <h1>WWF's Panda symbol</h1>
  <p>The Panda has become the symbol of WWF. The well-known panda logo of WWF originated from a panda named Chi Chi that was transferred from the Beijing Zoo to the London Zoo in the same year of the establishment of WWF.</p>
</section>
```

*Ví dụ, sử dụng phần tử section để liệt kê các bài viết trên blog*

```html
 <section>
    <h2>Tiêu đề bài viết 1</h2>
    <p>Trích đoạn của bài viết 1</p>
  </section>
  <section>
    <h2>Tiêu đề bài viết 2</h2>
    <p>Trích đoạn của bài viết 2</p>
  </section>
<section>
    <h2>Tiêu đề bài viết 3</h2>
    <p>Trích đoạn của bài viết 3</p>
  </section>
```

*Tuy nhiên, nếu chỉ đơn thuần chia nội dung trang web thành các vùng để định dạng, trang trí, xử lý tương tác, thì nên sử dụng phần tử div thay vì section.*

**Bài viết (article)**

Phần tử article cũng có chức năng chia nội dung thành các vùng như phần tử section.

Có một điều khác là phần nội dung nằm trong phần tử article có thể tồn tại độc lập (không liên quan đến các nội dung khác), và có thể được sử dụng lại ở nơi khác.

Phần tử article thường dùng để chứa một bài viết trên diễn đàn, báo điện tử, tạp chí, blog, hoặc chứa một bình luận của người dùng.

*Ví dụ, sử dụng phần tử article để tạo một bài viết trên blog*

```html
<article>
  <h1>Tiêu đề của bài viết</h1>
    <ul>
      <li>Tên tác giả</li>
      <li>Thuộc thể loại: Bài viết mới</li>
    </ul>
   <p>
    Phần nội dung của bài viết
  </p>
 </article>
```

**Bài viết gồm nhiều phần (article chứa section)**

Nếu một article gồm nhiều nội dung, có thể chia nội dung thành các section.

*Ví dụ:*

```html
<article>
                        <h1>Tiêu đề của bài viết</h1>
                        <ul>
                                    <li>Tên tác giả</li>
                                    <li>Thuộc thể loại: Bài viết mới</li>
                        </ul>
                        <section>
                                    <h2>Mở đầu</h2>
                                    <p>Nội dung của phần mở đầu</p>
                        </section>
                        <section>
                                    <h2>Nội dung 1</h2>
                                    <p>Nội dung 1 của bài viết</p>
                        </section>
<section>
                                    <h2>Nội dung 2</h2>
                                    <p>Nội dung 2 của bài viết</p>
                        </section>
                        <section>
                                    <h2>Kết luận</h2>
                                    <p>Nội dung của phần kết luận</p>
                        </section>
            </article>
```

**Một vùng chứa nhiều bài viết (section chứa article)**

Ngược lại, một section cũng có thể chứa nhiều article.

*Ví dụ:*

```html
<section>
<h2>Các bài viết mới</h2>
<article>
  <h1>Tiêu đề của bài viết 1</h1>
    <ul>
      <li>Tên tác giả 1</li>
      <li>Thuộc thể loại: Bài viết mới</li>
    </ul>
   <p>
    Phần nội dung của bài viết 1
  </p>
 </article>

<article>
  <h1>Tiêu đề của bài viết 2</h1>
    <ul>
      <li>Tên tác giả 1</li>
      <li>Thuộc thể loại: Bài viết mới</li>
    </ul>
   <p>
    Phần nội dung của bài viết 2
  </p>
 </article>
</section>
```

**Thông tin bổ trợ (aside)**

Phần tử aside được sử dụng để chứa các thông tin có liên quan đến nội dung chính.

Được đặt bên cạnh nội dung chính (trên, dưới, trái, phải).

Aside có nghĩa là bổ sung thêm.

 Về mặt trực quan có thể hình dung phần tử aside giống với sidebar (thanh bên) trên giao diện web. Tuy nhiên, hai cái này không phải là một.

Aside mang tính bổ trợ về mặt ngữ nghĩa, trong khi sidebar có nghĩa là đặt ở bên cạnh khi hiển thị.

Trong thực tế, phần tử aside thường được dùng để chứa trích dẫn (quote), thông tin thêm (background information), danh sách các liên kết, phát biểu (callouts), hoặc bất cứ thứ gì liên quan (mà không quan trọng) đến tài liệu.

*Ví dụ, sử dụng phần tử aside để liệt kê các liên kết liên quan tới phần nội dung*

```html
<h1>Một số kĩ năng sinh viên nên chuẩn bị</h1>
<p>Trong thời gian học tại trường Đại học, các bạn nên trang bị cho mình những thứ sau, để khi ra trường có thể tự tin làm việc, và hạnh phúc trong công việc.</p>
<p>Những thứ các bạn nên để ý là: kiến thức chuyên môn và cuộc sống, kĩ năng làm nghề, kĩ năng làm việc, kĩ năng sống; thái độ trong giao tiếp, trong công việc và thái độ với nghề mà mình đang theo đuổi.</p>
<aside>
<h2>Một số cuốn sách về định hướng nên đọc</h2>
<ul>
<li>Khuyến học</li>
<li>Cà phê cùng Tony</li>
<li>Khởi hành</li>
<li>Đúng việc</li>
<li>Trên đường băng</li>
<li>Code dạo ký sự</li>
</ul>
</aside>
```

**Điều hướng (navigation)**

Phần tử nav được sử dụng để chứa các liên kết (link) điều hướng, thường được sử dụng để tạo trình đơn (menu) ngang, dọc.

**Lưu ý:** không phải mọi liên kết đều phải đặt trong phần từ nav. Nav là viết rút gọn của navigation.

*Ví dụ:*

```html
<nav>
<a href="#">Home</a> |    
<a href="#">About</a> |
<a href="#">Blog</a> |
<a href="#">Sign in</a>
</nav>
```

**Thông tin liên hệ (address)**

Phần tử address được sử dụng để chứa các thông tin liên lạc với tác giả của bài viết hoặc người đăng bài viết. 

Phần tử này thường được để ở cuối của tài liệu, cuối vùng hoặc cuối bài viết.

Phần tử address nên đặt trong phần tử footer.

**Lưu ý:** nội dung trong phần tử address thường là liên kết tới một email, trang thông tin tác giả, hoặc một website khác, chứ rất hiếm khi là một địa chỉ cư trú, hoặc địa chỉ văn phòng.

*Ví dụ:*

```html
<address>
Đóng góp bởi <a href="../authors/teo/">Văn Tèo</a>,
<a href="http://www.nhaxuatban.com/">Nhà Xuất Bản</a>
</address>
```

### 1.1.3 BT

**Bài tập 1**

**Bài tập 2**

**Bài tập 3**

### 1.1.4 Câu hỏi ôn tập

**C1** The content inside the **main** element should be unique to the document. It should not contain any content that is repeated across documents such as sidebars, navigation links, copyright information, site logos, and search forms.

**C2** The **header** element represents a container for introductory content or a set of navigational links.

**C3** The **article** element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable (e.g., in syndication).

**C4** The **aside**  element identifies content that is separate from, but tangentially related to, the surrounding content. In print, its equivalent is a sidebar, but it couldn’t be called “sidebar” because putting something on the “side” is a presentational description, not semantic.

**C5** The **address** element is used to create an area for contact information for the author or maintainer of the document. It is generally placed at the end of the document or in a section or article within a document.
