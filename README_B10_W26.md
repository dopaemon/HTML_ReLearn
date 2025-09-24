# Tập làm dự án DA1 (Lập trình tiếp)

## Viết mã nguồn cho trang thoiGianMoCua.html
Vì giao diện của trang thoiGianMoCua.html có phần header và footer giống với trang index.html. Nên chúng ta chỉ cần viết mã cho vùng main
```html
    <h3>Thời gian mở cửa</h3>
    <dl>
        <dt>Thứ 2 > Thứ 6</dt>
        <dd>Từ 8h:00 > 19h:00</dd>
        <dt>Thứ 7</dt>
        <dd>Từ 8h:00 > 17h:00</dd>
        <dt>Chủ nhật</dt>
        <dd>Nghỉ</dd>
    </dl>
    <p>
        <a href="#">Trở về đầu trang</a>
    </p>
```

Tuy nhiên, chúng ta phải điều chỉnh một chút mã nguồn của menu,
```html
    <li>
        <a href="index.html#gt-ve-tiem-sach">Giới thiệu về tiệm sách</a>
    </li>
    <li>
        <a href="index.html#danh-muc-sach">Các loại sách đang bán</a>
    </li>
    <li>
        <a href="#">Thời gian mở cửa</a>
    </li>
```

## Viết mã nguồn cho trang lienHe.html
Giao diện của trang lienHe.html có phần header và footer giống với trang index.html. Nên chúng ta chỉ cần viết mã cho vùng main:

### Tạo một header
```html
<h2>Liên hệ với tiệm sách</h2>
```

Tạo form để người dùng có thể liên hệ với tiệm sách. Vì chưa học tới phần web back-end, front-end, trước tiên, dùng [**HttpBin**](http://httpbin.org/get).
```html
<h2>Liên hệ với tiệm sách</h2>
        <form action="http://httpbin.org/get" method="get">
            <fieldset>
                <legend>Liên hệ với tiệm sách</legend>
                <p>
                    <label for="ten">Tên:</label>
                    <input type="text" name="ten" id="ten" placeholder="Tên của bạn" required>
                </p>
                <p>
                    <label for="email">Email:</label>
                    <input type="text" name="email" id="email" placeholder="Email của bạn" required>
                </p>
                <p>
                    <label for="dien-thoai">Điện thoại:</label>
                    <input type="tel" name="dien-thoai" id="dien-thoai" placeholder="Điện thoại của bạn">
                </p>
                <p>
                    <label for="loi-nhan">Lời nhắn:</label>
                    <br>
                    <textarea name="loi-nhan" id="loi-nhan" cols="30" rows="10" placeholder="Để lại lời nhắn ở đây"></textarea>
                </p>
            </fieldset>
            <button type="submit">Gửi</button>
            <button type="reset">Xóa</button>
        </form>
        <p>
            <a href="#">Trở về đầu trang</a>
        </p>
```
