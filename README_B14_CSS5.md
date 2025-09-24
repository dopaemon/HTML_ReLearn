# ĐỊNH DẠNG VĂN BẢN (PHÔNG CHỮ)

## 2 Định dạng văn bản

Chức năng của CSS là định dạng, trang trí cho trang web. Chúng ta sẽ viết các chỉ dẫn định dạng (style rule) để mô tả cách hiển thị của mỗi phần tử HTML.

Do các phần tử HTML có cấu trúc phân cấp (hierarchy), nên có nhiều định dạng CSS sẽ được kế thừa từ phần tử cha xuống phần tử con.

Vì chúng ta có thể viết mã CSS ở nhiều nơi khác nhau, cộng với tính kế thừa, sẽ dẫn tới tình trạng một phần tử HTML có thể nhận nhiều định dạng CSS cùng lúc. Do vậy, chúng ta cần phải nắm được kĩ thuật Xếp lớp trong định dạng. Cụ thể là biết được cách CSS xác định độ ưu tiên của mỗi chỉ dẫn.

Trước khi CSS cho một trang web, thì nên chuyển định dạng của một số phần tử HTML về trạng thái chuẩn, để nó hiển thị đồng nhất trên các trình duyệt khác nhau.

Mỗi phần tử HTML sẽ có một hình chữ nhật tương ứng gọi là mô hình cái hộp (box model)

Sử dụng các đơn vị đo một cách hợp lý, chuyên nghiệp

Để trình bày văn bản, chúng ta sẽ tìm hiểu các chủ đề sau:

- Phông chữ
- Cỡ chữ
- Màu chữ

### 2.1 Phông chữ

#### Phông chữ là gì?

Phông chữ (font), là tập hợp các kí tự có cùng kiểu chữ (typeface, font-family). Bạn có thể dùng 3 thuật ngữ font, typeface và font-family thay thế cho nhau.

| Với mỗi thuộc tính trong tài liệu này sẽ được mô tả theo cú pháp sau: |
|-----------------------------------------------------------------------|
| - Giá trị (values): các giá trị hợp lệ cho thuộc tính |
| - Giá trị mặc định (default): giá trị mặc định sử dụng cho thuộc tính (trong trường hợp giá trị không được xác lập một cách tường minh). Giá trị mặc định trên các trình duyệt khác nhau thì khác nhau |
| - Phạm vi áp dụng (applies to): một số thuộc tính chỉ áp dụng trên một vài loại phần tử cụ thể, chứ không áp dụng trên mọi phần tử. |
| - Kế thừa: cho biết thuộc tính này có được kế thừa xuống các hậu duệ của nó (descendants) hay không |

Để chọn phông chữ, sử dụng thuộc tính font-family:

- Giá trị: tên của một hoặc nhiều phông chữ hoặc loại phông chữ (generic name, hay generic font families).
- Giá trị mặc định: tùy theo trình duyệt.
- Phạm vi áp dụng: cho mọi phần tử HTML.
- Kế thừa: có.

VD: chọn phông chữ là Arial để áp dụng cho phần tử body.

```html
    <style>
        body {
            font-family: Arial;
        }
    </style>

</head>

<body>
    <p>Học về phông chữ</p>
</body>
```

Trên máy tính chạy Windows, các phông chữ được để ở thư mục C:\Windows\fonts.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEge9y11reUPYPQIGKREei1EmgcW2En5lVU_wdWpL07VhyzF-zuWUkvEYIzTBhMEz7RG4ygulWmhkg52Cvc6ctf4kwflCW4lV9lyqDSloRyQaMHKW_ukU1rQJ-hvzSdYSstZUx-2cTMsQ5ItSIxmUrzlBhmEY2qgk3Bx0Tk1Sq_k-Fq6O5aqfSyS1lLG=w400-h263)

Như vậy, nếu lập trình viên sử dụng phông chữ mà trên máy người dùng không có, thì trình duyệt sẽ lấy phông chữ mặc định của nó để sử dụng.

Để tránh trường hợp, máy tính không có phông chữ như mong muốn, bạn nên khai báo một dãy các phông chữ tương đồng, và cuối dãy luôn là loại phông.

```html font-family: Verdana, Arial, Helvetica, sans-serif;```

Trình duyệt sẽ tìm các phông chữ theo thứ tự (ưu tiên) từ trái sang phải. Theo đó, phông chữ Verdana được ưu tiên cao nhất, nếu không có sẽ tìm phông chữ Arial, theo sau là Helvetica, nếu trên máy người dùng vẫn không có, thì tìm một phông chữ bất kì (miễn là cùng loại sans-serif).

Một vài lưu ý khi liệt kê các phông chữ:

- Tên phông chữ phải viết hoa chữ cái đầu tiên (ví dụ: Verdana); loại phông thì viết thường (ví dụ: sans-serif).
- Nếu tên phông gồm nhiều chữ thì bao lại bằng dấu nháy kép (""), ví dụ "Times New Roman".
- Sử dụng dấu phẩy (,) để ngăn cách giữa các tên phông chữ.

##### Một số loại phông chữ phổ biến

Trong CSS, có năm loại phông chữ (generic font family) phổ biến, gồm: serif, sans-serif, monospace, cursive và  fantasy.

**serif**

Serif có nghĩa là những nét nhỏ được thêm vào các chữ.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEjv_UXBCzW921I2dF9C0irAFVeX4ZWsg2VAY507PXdn8L1Fb5NR7vRb8oa5Gj4cnZ5-lBcENEhFQESmtzx2trhDk_NE5YOBz5ra4fxU0L6pXgRrgfT_csql9nDFQgVKcr8ns5xco9NZ-fr8jOrA7YqjIwkgOrk2SPA8YebqbhcR79sYnDqzDdk5EtcZ)

**sans-serif**

Ngược lại với serif, sans-serif là loại chữ “không có chân”

![image](https://blogger.googleusercontent.com/img/a/AVvXsEjk65w9aYpytR3-O8vvhmCVos4Fu8kJt14tScR8MbclOjOHPRYBOb9NWTvcqsBPfBfoQcbTiHBOPc80U7rtu5KP7wVdMT8t8UXxRu32P2NhURVQekSbEQAoLG3SGiL2rZ_fIHHET0OY7alS5IbcDSyBU9oS79VtcjeAwqnmydMB9oSga9owmnYBOX9v=w400-h111)

**monospace**

Monospace là loại chữ mà các kí tự có độ rộng bằng nhau (constant width). Mono nghĩa là duy nhất, đơn nhất; space nghĩa là khoảng rộng.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEh_XxlY4pAymk7HyXO18FT17LzadeN_-ZU9IcRgdauWX6gDdQeVmCX0Q9pTx4QuGH_0BggZcIOpyyfxhXrfzkJbrWOiIGmAnobtyTigWD_SM9PDGiHcXhGH1utYHr_NnBdgH54Z6bVYHCbS5Z-qS1_KHUyss8Of4-4Lywd0MIudCj0DrmnaTk7t6W4r=w400-h113)

**cursive**

Cursive là loại chữ viết tay (script, handwritten).

![image](https://blogger.googleusercontent.com/img/a/AVvXsEg3Sauu3fkkRenFjRJaFtIKSLJ1IKh6uRyGr2WolAawZGNYH4Wds7U1WN22P4_0Oajmiap4gPyKSvOFh0SwUmAFUKSJ2Mzh9Cu_tPnF4ltKg6QncbMGV4GI85c20GDV_FqOvpZgOWvXiUNKqkucp_ZUtEF_-FYh7oAOvIm-WTv-C0-3IcSOFjK2TsLB=w400-h75)

**fantasy**

Fantasy là loại chữ dùng nhiều trong thiết kế trang trí, tạo tiêu đề.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEiEM4ZYuFmUCQv0Z2p-JxYpVHL4_FEh-aQ_lFt0RZ9Ohnv2feFVVVaNcXPi3dfJnuyTKg4K147Rf6dEDcSKZ24pE4GQ067O9PreyUnNdnV0VMoF6tBTVwDPl0CBPzwgRlqbCjttToXII4ceZ6vk6V8LU1cOanGjeA5ygBq5EHOgh7JMbcMOiBwJYQBk=w400-h83)
