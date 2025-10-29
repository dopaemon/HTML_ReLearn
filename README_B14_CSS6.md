# ĐỊNH DẠNG VĂN BẢN

## 2.1.2 Web fonts

Có một nguồn khác để lấy được phông chữ là từ trên mạng. Người ta gọi các phông chữ này là web fonts. Theo đó, bạn có thể lấy phông chữ từ một máy server chuyên cung cấp phông, hoặc lưu luôn các phông chữ trong thư mục của website để chủ động khi sử dụng.

**Lấy phông chữ từ server dịch vụ**

Chúng ta cùng sử dụng web font miễn phí của Google:

- Vào dịch vụ phông chữ của Google (https://fonts.google.com/).

- Chọn 2 phông chữ mà bạn muốn dùng. Ví dụ: Dongle và Ubuntu.

- Với mỗi phông chữ, bạn sẽ chọn cụ thể các cỡ chữ khác nhau. Ví dụ, sau khi chọn phông chữ Dongle, một cửa sổ mới sẽ mở ra để bạn chọn các cỡ chữ. Bạn có thể bấm vào nút Select Light 300 (ở phía phải) để chọn cỡ chữ.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEiEDzGaQ2ZJJlUBDN2T3ILvAcI8l-Aug8iJAXIW5vF8Vg9SeUgLQBtYmsImGyDKm2--Z9nosyNdr7uV0Cu96-8JGcWXwGW-vgsFJRbkclL8cxmsbtGdOlHolltfyXd7vjtv0n17BS4oqSDw0WQF91QFDv94YXhTWpsHr7jxBIb4b4ZAo6b7t-dMHiX4=w400-h133)

Bạn bấm vào nút View selected families (góc trên cùng, phía phải) để xem các phông đã được chọn.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEg1qP_NUAB9zp4vEU6WbfknefdaHgl2NmR9ouhPgGZmXh9u-8QBlXX2-hTdrm0VjF-UjwuTXRqWoJm3PFtW03GFGGZQHeNFj2TNeYg1CGD6R9IkO7UEtof5fOwZZIb1mTjCdRmuaFN-bIBOYNh8d_zB3lucolkaTFOq-t4PcFQ-2iq9Q8Heq5q38J-v=w335-h400)

- Chúng ta sẽ chép đoạn mã dưới nút <link>, dán vào vùng head của mã HTML.

```html

<head>

    <meta charset="UTF-8">
    <title>Web fonts</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Dongle:wght@300;400;700&display=swap" rel="stylesheet">

```

- Vậy là chúng ta đã có thể khai báo thuộc tính font-family để sử dụng web font có sẵn trên mạng.

```html

    <style>
        body {
            font-family: Dongle, sans-serif;
        }
    </style>

```

**Lưu phông chữ trong website**

Để sử dụng web font một cách chủ động, thay vì sử dụng dịch vụ phông chữ từ các server trên mạng, chúng ta sẽ tải luôn các web font về thư mục website.

*Các bước thực hiện:*

- Tìm phông chữ phù hợp.
-  Chọn phông chữ.
-  Tạo thư mục fonts trong dự án, giải nén phông chữ vừa tải về vào thư mục fonts.
-   Vậy là chúng ta đã tải được phông chữ về máy và lưu trong thư mục của website. Công việc tiếp theo là khai báo cho CSS biết tên và vị trí của tập tin chứa phông chữ.
-   Sử dụng chỉ dẫn @font-face để khai báo tên và chỉ ra đường dẫn của tập tin chứa phông chữ:

```html

<style>
        @font-face {
            font-family: acherusgrotesque;
            src: url('fonts\Demo-Acherus Grotesque\Demo_Fonts\Fontspring-DEMO-acherusgrotesque-black.otf');
        }
```

- Giờ thì chúng ta có thể sử dụng phông chữ acherusgrotesque để định dạng cho các văn bản của trang web, sử dụng thuộc tính font-family:

```html

        body {
            font-family: acherusgrotesque, sans-serif;
        }

```

-  Lưu lại mã nguồn và quan sát kết quả trên trình duyệt, bạn sẽ thấy phông chữ acherusgrotesque đã được áp dụng cho văn bản.

**Một số kinh nghiệm khi làm việc với phông chữ**

