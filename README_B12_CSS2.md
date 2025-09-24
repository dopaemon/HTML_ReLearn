# SỰ KẾ THỪA - XẾP LỚP

## 1.2 Sự kế thừa (Inheritance)

Trong CSS những gì chúng ta định dạng cho phần-tử-cha, thì mặc định, chúng cũng được định dạng cho các phần-tử-con. Tổng quát hơn, khi chúng ta định dạng CSS cho một phần tử, thì một số định dạng cũng áp dụng luôn cho các phần tử chứa trong nó.

VD:

```html
        p {

            font-size: 41px;

            color: red;

        }
```

```html <p>Cuối tuần đi đá banh, giúp thêm <em>năng lượng</em> để làm việc</p>```

Chúng ta chỉ định dạng cho phần tử p có cỡ chữ 41px và màu đỏ, chứ không định dạng cho phần tử em. Tuy nhiên, do em nằm trong p nên nội dung của em cũng có cỡ chữ 41px và màu đỏ.

**Cấu trúc của tài liệu**

![image](https://blogger.googleusercontent.com/img/a/AVvXsEiq71Z2Ujvbgg1zHEHdeahc9hisgkG3MZ2KiLRu3UlRCA1oBTi8HUJaU8jrTIG9Zz36llE4ftU8ZVHScKc-cUIJ5vfxoYUpRN5xgL4IptGVhCqhKyqucyfFcLvDTIvtY75SjYbaRY3N8OB4dkav8DTdJ_GNpwx6Ou3VKgnSIZUCM8w_r5PFjvyOzm81=w400-h235)

**Mối quan hệ giữa các nút trong cây-HTML**

- Mọi phần tử nằm trong một phần tử thì được gọi hậu duệ (descendants) của nó. Ví dụ, các phần tử h1, h2, p, em, img được gọi là hậu duệ của phần tử body
- Phần tử chứa trực tiếp phần tử khác được gọi là cha (parent), các phần tử được-chứa gọi là con (child). Ví dụ, phần tử p chứa em, nên p là cha, em là con
- Với một phần tử bất kì, mọi phần tử ở mức cao hơn mà có mối liên hệ nội tộc (…ông-cha-con-cháu…) thì được gọi là tổ tiên (ancestors) của nó. Ví dụ, tổ tiên của img là p, body, html
- Hai phần tử có cùng cha thì được gọi là anh em (siblings), Ví dụ, h1, h2, p là anh em, vì đều có cha là body

**Có thuộc tính được kế thừa, có thuộc tính không**

Sẽ có một số thuộc tính được kế thừa và có một số thuộc tính thì không.

![image](https://blogger.googleusercontent.com/img/a/AVvXsEh_Ndccaddnlx8dz30O2W4PxEWIVUQ9d0LtX3nnf1yVjdw9a-0xEO_wSi5hy4_7rq9oKduLR-TT3WnQ_XRAIZHq1G_BHZSJTMY02uJpjQJ3jeQXfK3hAX2uDJuJxK9d4fbuJWwBLo1XINre4n6_xigCZ_dX_015Tfegh7TanQ-YM8DaQD6zOtCKDhQL)

Các thuộc tính liên quan đến định dạng văn bản (ví dụ: font-size, color, style) thì sẽ được kế thừa, các thuộc tính liên quan đến borders, backgrounds, margins sẽ không được kế thừa.

## 1.3  Kĩ thuật xếp lớp (Cascading)

Kĩ thuật xếp lớp là cách sắp xếp thứ tự các định dạng CSS (chỉ-dẫn-CSS) lên một phần tử HTML. Mỗi chỉ-dẫn-CSS được đánh trọng số ưu tiên (weight) hay độ ưu tiên, chỉ-dẫn-CSS nào có độ ưu tiên thấp sẽ định dạng lên phần tử HTML trước; chỉ-dẫn-CSS có độ ưu tiên cao hơn sẽ định dạng đè lên (overwrite) chỉ-dẫn-CSS có độ ưu tiên thấp hơn.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjS84MAF24T1XzEs89FzEj9sdqgRsEnv8fYBgPXw1_aqhX_qdnTBU24NZoP6AuxPs9mR-oT5WZqMp55DmzB_tJfeeynndtPEk6wYH798Xcd4aij46YDTF8DL5JiXL_RJlzFiey3YrFKWfLj04DMIj5E5jA5u747WK5ZBgvn-ETKcYgaYBNAO7fxar10/w400-h201/ki%20thuat%20cascading.jpg)

Độ ưu tiên được xác định dựa trên 3 yếu tố:

- Chỉ-dẫn-CSS từ đâu đến (priority of style source)
- Tính rõ ràng, chính xác của chỉ-dẫn-CSS (specificity)
- Thứ tự thực thi chỉ-dẫn-CSS (rule order)

**Chỉ-dẫn-CSS từ đâu đến**

Nếu chúng ta không viết mã CSS để định dạng cho tài liệu HTML, thì trình duyệt sẽ lấy định dạng mặc định của nó để hiển thị trang web. W3C gọi kiểu định dạng này là user agent style sheet. Mỗi trình duyệt (ví dụ Chrome, Firefox) sẽ có bộ định dạng mặc định khác nhau. 

**CSS do người dùng tạo ra**

Trong quá trình duyệt web, người dùng có thể tự thiết lập chế độ hiển thị trang web theo ý của họ. Nói cách khác, họ tự CSS cho trang web (user style sheet). Các định dạng CSS này sẽ ghi đè lên kiểu định dạng mặc định của trình duyệt.

**CSS do lập trình viên tạo ra**

Nếu lập trình viên có viết mã CSS để định dạng cho tài liệu HTML (author style sheet), thì mã này sẽ có độ ưu tiên cao hơn mã CSS của người dùng và của trình duyệt.

Bảng sau cho biết độ ưu tiên của định dạng dựa trên nguồn CSS từ đâu đến? Thứ tự ưu tiên sẽ tăng dần từ trên xuống:

| Mức độ ưu tiên |
|----------------|
| CSS mặc định của trình duyệt |
| CSS do người duyệt web định nghĩa |
| CSS do lập trình viên định nghĩa |
| Các định dạng CSS  do lập trình viên đánh dấu là “!important” |
| Các định dạng CSS do người duyệt web đánh dấu là “!important” |

**Tính rõ ràng, chính xác của chỉ-dẫn-CSS**

Trong tình huống này, CSS quy định: khi hai (hay nhiều) chỉ dẫn trong một tài liệu CSS xung đột với nhau, thì sẽ dựa vào loại của bộ chọn (type of selector) để xác định độ ưu tiên. Bộ chọn nào càng rõ ràng, chính xác, và cụ thể (specificity) thì có độ ưu tiên cao hơn.

**Thứ tự thực thi chỉ-dẫn-CSS (rule order)**

CSS đưa ra quy tắc “cái nào gần đối tượng (HTML) cần định dạng hơn sẽ có độ ưu tiên cao hơn (cái cuối cùng sẽ có độ ưu tiên cao nhất)”.
