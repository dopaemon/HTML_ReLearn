### CSS (14) - Mô hình cái hộp (1)


4         Định dạng bố cục
==========================

4.1       Mô hình cái hộp
-------------------------

### 4.1.1       Định nghĩa

Như trong phần _Tổng quan về CSS_ đã đề cập. Trong việc định dạng hiển thị, chúng ta sẽ phải đặt các phần tử HTML ở một ví trí cụ thể trên giao diện, với chiều rộng, chiều dài xác định; hoặc đổ màu nền. Để tiện lợi cho việc này, CSS đưa ra khái niệm _mô hình cái hộp_ (box model).

Mô hình cái hộp là công cụ CSS sử dụng để hiển thị các phần tử HTML. CSS quy ước: mỗi phần tử HTML sẽ có một hình chữ nhật tương ứng. Hình chữ nhật này gồm vị trí hiển thị (tọa độ x, y), chiều rộng, chiều dài, đường viền (border), căn lề (margin), dãn biên (padding), màu nền…v.v. Một tài liệu HTML có bao nhiêu phần tử thì có bấy nhiêu cái hộp (trừ các phần tử trong vùng _head_), không phân biệt là phần tử kiểu inline hay block. Cấu trúc cha-con của tài liệu HTML cũng được thể hiện trong mô hình cái hộp, cụ thể hộp-cha (của phần tử cha) sẽ chứa hộp-con (của phần tử con).

Ví dụ, đoạn mã sau minh họa hình ảnh của box model, gồm 5 cái hộp, với cấu trúc lồng nhau.

```html

   <style>

        body { border: 1px solid red; }

        h1 { border: 1px solid red; }

        div { border: 1px solid red; }

        p { border: 1px solid red; }

        em { border: 1px solid red; }

        * { padding: 3px}

    </style>

</head>

<body>

    <h1 _id_="tieu-de">Hi bac Teo!</h1>

    <div>

        <p>Mô hình cái hộp là cách thức tổ

            chức của CSS để <em>hiển thị</em> các phần tử ra giao diện.</p>

    </div>

```

Qua quan sát, bạn sẽ thấy các hộp của phần tử kiểu block có chiều rộng chiếm hết màn hình, trong khi các hộp của phần tử kiểu inline có kích thước vừa đủ để chứa nội dung bên trong.

Chúng ta cũng có thể sử dụng Developer tools để quan sát box model một cách trực quan. Như hình sau:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEhWxE_WmJHIOpOAQFIq1pFyB95j0HqqIXMyAgFJ6Ha3orgEi41IxV-I9Aic6o4OOSf9349w_t56E4XnczKFxZmgK1HTejRaTyFy2bnKuSPUr6QAI7y4hphBIgggV_44JR0B2Vrfk2z-4FKMvKJQhDSaUWEr7PxTbC_2auuh8JnOEZCQv_4htkEI3eCvIvA=w400-h236)](https://blogger.googleusercontent.com/img/a/AVvXsEhWxE_WmJHIOpOAQFIq1pFyB95j0HqqIXMyAgFJ6Ha3orgEi41IxV-I9Aic6o4OOSf9349w_t56E4XnczKFxZmgK1HTejRaTyFy2bnKuSPUr6QAI7y4hphBIgggV_44JR0B2Vrfk2z-4FKMvKJQhDSaUWEr7PxTbC_2auuh8JnOEZCQv_4htkEI3eCvIvA)

  

Chúng ta có thể sử dụng Developer tools để điều chỉnh các thông số của cái hộp. Trong cửa sổ Styles, bấm đúp chuột vào giá trị, điền giá trị mới, hoặc dùng mũi tên lên-xuống của bàn phím để điều chỉnh. Kết quả sẽ được thay đổi ngay lập tức trên giao diện. Tuy nhiên, các điều chỉnh trong Developer tools không ảnh hưởng tới tập tin mã nguồn. Do vậy, khi giao diện đã theo ý muốn, bạn có thể chép các giá trị đã điều chỉnh vào tập tin mã nguồn. Đây cũng là một phương pháp hay để viết mã CSS.

Trong phần này, chúng ta sẽ tìm hiểu chi tiết các thuộc tính liên quan đến cái hộp.

### 4.1.2       Các thành phần của một hộp

Một phần tử HTML, dù là kiểu block hay inline đều có cái hộp của riêng nó, hình chữ nhật, gồm nhiều thành phần. Xem hình minh họa,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEisnqrZY2xJ6K_WyF2EDmOHHnkITt64BndrIa0vMzuOghwBjNOl2LFv6F2HhhA7WN6myQ6yS9H8ms86z3YIBZQW12VOouq-GSmNVl5hCjRyu9UWuDL5IhfSJZDE3xbkyOmrP7q5zOFjJVFpXRQwS147JNNKUl-1SDaq0RD6hcJg3vDQMT21GzboayYng5M=w400-h253)](https://blogger.googleusercontent.com/img/a/AVvXsEisnqrZY2xJ6K_WyF2EDmOHHnkITt64BndrIa0vMzuOghwBjNOl2LFv6F2HhhA7WN6myQ6yS9H8ms86z3YIBZQW12VOouq-GSmNVl5hCjRyu9UWuDL5IhfSJZDE3xbkyOmrP7q5zOFjJVFpXRQwS147JNNKUl-1SDaq0RD6hcJg3vDQMT21GzboayYng5M)

Giải thích các thành phần của hộp,

_(Lưu ý: để dễ hiểu, chúng ta sẽ dịch các thành phần của cái hộp sang tiếng Việt, Tuy nhiên, khi làm việc hoặc khi đã hiểu rồi thì nên sử dụng từ tiếng Anh cho ngắn gọn, dễ trao đổi với mọi người.)_

– Vùng nội dung (content area): là vùng trong cùng của hộp, chứa nội dung của phần tử. Vùng màu trắng chứa văn bản ở hình trên

– Cạnh trong (inner edge): là cạnh của Vùng nội dung, nó là đường phân cách giữa Vùng nội dung và Vùng đệm trong (padding area). Đường này không được hiển thị trên trang web

– Vùng đệm trong (padding area, dãn biên): là khoảng không nằm giữa Vùng nội dung và Đường viền. Vùng đệm trong là tùy chọn (có thể có hoặc không). Ở hình trên, Vùng đệm trong có màu cam vàng

– Đường viền (border): là đường bao quanh phần “nhìn thấy trên giao diện” của phần tử và Vùng đệm trong (nếu có thiết lập). Đường viền là tùy chọn. Đường màu đen ở hình trên

– Vùng đệm ngoài (margin area, căn lề): là khoảng không thêm vào phía ngoài của Đường viền. Ở hình trên, Vùng đệm ngoài có màu xanh lợt. Tuy nhiên, thực tế, Vùng đệm ngoài luôn trong suốt, do vậy phần nhìn thấy sẽ là màu nền của phần tử cha

– Cạnh ngoài (outer edge): là cạnh của Vùng đệm ngoài, đây chính là cạnh giới hạn toàn bộ không gian của một phần tử trên trang web. Ở hình trên, Cạnh ngoài là đường nét đứt, thực tế, đường này không được hiển thị trên trang web. Như vậy, kích thước một phần tử sẽ bao gồm kích thước của Vùng nội dung, Vùng đệm trong, Đường viền, và Vùng đệm ngoài.

### 4.1.3       Xác định kích thước hộp

Mặc định, kích thước (chiều rộng và chiều cao) của phần tử kiểu block được trình duyệt tự động xác lập (auto). Nó sẽ bằng chiều rộng của cửa sổ trình duyệt, hoặc của phần tử chứa nó; chiều cao sẽ vừa đủ để chứa hết nội dung. Tuy nhiên, có thể sử dụng hai thuộc tính _width_ và _height_ để thiết lập chiều rộng và chiều cao tùy ý.

Như ở các phần trước đã tìm hiểu, hộp của phần tử gồm nhiều thành phần, do vậy việc xác định kích thước cho phần tử không đơn giản là thiết lập giá trị cho hai thuộc tính _width_ và _height_, mà cần xác định xem giá trị vừa được thiết lập đã bao gồm các thành phần nào.

CSS cung cấp hai cách để xác định kích thước của một phần tử. Một là, giá trị _width_ và _height_ sẽ chỉ được tính cho Vùng nội dung (content), như vậy, kích thước của hộp sẽ phải cộng thêm giá trị của Vùng đệm trong (padding) và Đường viền (border). Đây là cách tính mặc định, CSS gọi cách này là _content-box_. Cách thứ hai là, giá trị _width_ và _height_ sẽ bao gồm kích thước của Vùng nội dung, Vùng đệm trong và Đường viền, CSS gọi cách này là _border-box_.

Lưu ý, cả hai cách xác định kích thước trên đều chỉ áp dụng cho các phần tử kiểu block và phần tử kiểu inline không chứa văn bản (non-text inline) (ví dụ phần tử ảnh). Nếu chúng ta thiết lập kích thước cho phần tử kiểu inline chứa văn bản, thì trình duyệt sẽ bỏ qua việc thiết lập này.

Để lựa chọn cách thiết lập kích thước cho phần tử, sử dụng thuộc tính _box-sizing_.

Thuộc tính _box-sizing_:

– Giá trị: _content-box | border-box_

– Mặc định: _content-box_

– Áp dụng: _cho mọi phần tử_

– Kế thừa: _không_

Thuộc tính _width_:

– Giá trị: _giá trị đo kích thước | % | auto_

– Mặc định: _auto_

– Áp dụng: _các phần tử kiểu block và kiểu inline không chứa văn bản_

– Kế thừa: _không_

Thuộc tính _height_:

– Giá trị: _giá trị đo kích thước | % | auto_

– Mặc định: _auto_

– Áp dụng: _các phần tử kiểu block và kiểu inline không chứa văn bản_

– Kế thừa: _không_

**Thiết lập kích thước kiểu content-box**

Mặc định, khi không có khai báo thuộc tính _box-sizing_, thì giá trị _width_ và _height_ sẽ được tính cho Vùng nội dung, hay nói cách khác là kiểu tính kích thước _content-box_. Tuy nhiên, lập trình viên cũng có thể thiết lập một cách tường minh bằng đoạn mã _box-sizing: content-box_. 

Ví dụ, đoạn mã sau sẽ thiết lập kích thước cho phần tử _p_ gồm các giá trị: rộng 500px, cao 150px, vùng đệm trong (cả bốn phía) 20px, đường viền (cả bốn cạnh) 2px, vùng đệm ngoài (cả bốn phía) 20px. Giả sử kiểu kích thước là _content-box,_ nên chiều rộng và chiều cao sẽ là của vùng nội dung.

```html
p {

background: #c2f670;

width: 500px;

height: 150px;

padding: 20px;

border: 2px solid gray;

margin: 20px;

}
```

Kết quả: chiều rộng của phần tử (không tính vùng đệm ngoài) sẽ là 544px (500px vùng nội dung, cộng thêm 40px vùng đệm trong, cộng thêm 4px đường viền) – đây là vùng của phần tử mà người dùng nhìn thấy; chiều rộng của toàn bộ phần tử (tính cả vùng đệm ngoài 40px – vùng này người dùng không nhìn thấy) sẽ là 584px. Biết được kích thước này sẽ giúp việc bố trí giao diện phù hợp, chính xác.

Xem hình minh họa, kích thước kiểu _content-box_,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEg4ZLAr3EYAc_3LeK5exVypKR8etUrM3eCWieigQyRL9FLVnTpukDJpoI31m9TjJCFmMhkwmNUbRvSfktErW3ei5TRLPIkOBikzzDJVxZqaNW3CW_G8WDdnuAdZXQNmYvBbpFYNk5pi7d01hj1g1w_19j8DuqJJQnyjGSyuY365y-yDYMjbJuz5KGdsCLk=w398-h400)](https://blogger.googleusercontent.com/img/a/AVvXsEg4ZLAr3EYAc_3LeK5exVypKR8etUrM3eCWieigQyRL9FLVnTpukDJpoI31m9TjJCFmMhkwmNUbRvSfktErW3ei5TRLPIkOBikzzDJVxZqaNW3CW_G8WDdnuAdZXQNmYvBbpFYNk5pi7d01hj1g1w_19j8DuqJJQnyjGSyuY365y-yDYMjbJuz5KGdsCLk)

**Thiết lập kích thước kiểu border-box**

Đây không phải là chế độ tính kích thước mặc định, nên cần khai báo tường minh, _box-sizing: border-box_.

Giá trị _width_ và _height_ sẽ bao gồm kích thước của vùng nội dung, vùng đệm trong và đường viền.

Ví dụ, quan sát kết quả khi thực hiện thiết lập _width_ cho phần tử _p_ là 500px, và _height_ là 150px,
```html
p {

box-sizing: border-box;

width: 500px;

height: 150px;

}
```

Xem hình minh họa, kích thước kiểu _border-box_,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEhg5JBFuzABUH2S-hR3R-_q2HsDcCTfdkclaT8prZMD6veDmUOk7zHvbxLwcrxHg_MsOeWMe2I49ltJLtI7Xye0hiu32DzeD14PbYHsLbUkCQGL0G8HukUWJ5z7kogg0GDp20t2HczXvvzOp5K6JO7Mfdv3nsiW8lnJPG3Wobm8xVkk7q-3BoJ8WRGCUDU=w400-h374)](https://blogger.googleusercontent.com/img/a/AVvXsEhg5JBFuzABUH2S-hR3R-_q2HsDcCTfdkclaT8prZMD6veDmUOk7zHvbxLwcrxHg_MsOeWMe2I49ltJLtI7Xye0hiu32DzeD14PbYHsLbUkCQGL0G8HukUWJ5z7kogg0GDp20t2HczXvvzOp5K6JO7Mfdv3nsiW8lnJPG3Wobm8xVkk7q-3BoJ8WRGCUDU)

Các lập trình viên thường hay sử dụng kiểu tính kích thước _border-box_, lý do là nó trực quan và đơn giản. Ví dụ, khi xác định kích thước của phần tử, không phải bận tâm tới việc tính thêm kích thước của vùng đệm trong và đường viền. Đặc biệt, kiểu kích thước _border-box_ và đơn vị đo là % chính là nền tảng của kĩ thuật thiết kế tùy biến theo kích thước giao diện (responsive design), ví dụ, nếu muốn tạo thành hai cột bằng nhau, đơn giản chỉ việc thiết lập thuộc tính _width_ là 50% cho mỗi cột.

Để đơn giản, các lập trình viên thường thiết lập cho mọi phần tử của tài liệu HTML đều được tính kích thước theo kiểu _border-box_ bằng khai báo sau,

_* { box-sizing: border-box; }_

**Kích thước tối thiểu, tối đa**

Để thiết lập kích thước tối đa hoặc tối thiểu cho một phần tử, sử dụng các thuộc tính sau: _max-height, max-width, min-height, min-width_.

Giá trị: _% | chiều dài | none_

Lưu ý: các thuộc tính này chỉ áp dụng trên các phần tử kiểu block và kiểu inline không chứa văn bản. Nếu kiểu kích thước của phần tử đang được thiết lập là _content-box_ thì các thuộc tính _max-height, max-width, min-height, min-width_ sẽ áp dụng cho vùng nội dung, và khi đó, nếu vùng đệm trong, viền hoặc vùng đệm ngoài cũng được thiết lập thì sẽ làm cho kích thước toàn bộ phần tử lớn hơn giá trị _max-height_ và _max-width_ đã được thiết lập. Không nên sử dụng các thuộc tính _max-height, max-width, min-height, min-width_ trong chế độ _border-box_ vì chúng có thể gây ra các trục trặc liên quan đến trình duyệt.

**Xác định chiều cao**

Thông thường, chiều cao của phần tử ít được thiết lập, mà nó hay để ở chế độ mặc định. Nghĩa là, chiều cao của phần tử sẽ tùy thuộc vào lượng nội dung, kích thước của phông chữ, các thiết lập của người dùng và các yếu tố khác. Với phần tử chứa văn bản, nếu có thiết lập chiều cao, thì cần để ý trường hợp nội dung vượt quá sức chứa của phần tử.

Trường hợp nội dung văn bản vượt quá sức chứa của phần tử (do thiết lập chiều cao), CSS có một số tùy chọn để hiển thị phần nội dung bị tràn.

**Xử lý khi bị tràn nội dung**

Khi bị tràn nội dung, có thể sử dụng thuộc tính _overflow_ để chọn cách xử lý.

Thuộc tính _overflow_:

– Giá trị: _visible | hidden | scroll | auto_

– Mặc định: _visible_

– Áp dụng: _các phần tử kiểu block và kiểu inline không chứa văn bản_

– Kế thừa: _không_

Hình dưới đây là minh họa cho các giá trị của _overflow_, phần tử chứa văn bản là một hình vuông có kích thước 150px (phần có nền được tô màu).

[![](https://blogger.googleusercontent.com/img/a/AVvXsEgRW1zs0nlprWnvxjojsrRkJ7ezk3gqJMyFpkseFmDeRiq6FJOwWlKx3UG9RlmczuuMlWh-AmaXuWVjDVDxgKlVbf2WbZlplYySkzx8s7KegZvZSXQAall7SGToWJIf8CvRG316NXRvjwQ7rrZ4nmL-jSWSJL9Xhlr8KqepmPi9mUdEj1Sbybn-FMEHojc=w400-h171)](https://blogger.googleusercontent.com/img/a/AVvXsEgRW1zs0nlprWnvxjojsrRkJ7ezk3gqJMyFpkseFmDeRiq6FJOwWlKx3UG9RlmczuuMlWh-AmaXuWVjDVDxgKlVbf2WbZlplYySkzx8s7KegZvZSXQAall7SGToWJIf8CvRG316NXRvjwQ7rrZ4nmL-jSWSJL9Xhlr8KqepmPi9mUdEj1Sbybn-FMEHojc)

  

– _visible_: chế độ mặc định, nội dung bị tràn vẫn được hiển thị, nhưng nằm ngoài vùng giới hạn của phần tử

– _hidden_: nội dung bị tràn sẽ bị ẩn đi

– _scroll_: phần tử có thêm thanh cuộn, giúp đọc được các nội dung bị tràn. Tuy nhiên, thanh cuộn này luôn tồn tại, dù nội dung không bị tràn.

– _auto_: trình duyệt tự xử lý khi có nội dung bị tràn, thường là sẽ có thanh cuộn. Tuy nhiên, khi nội dung không bị tràn thì thanh cuộn này sẽ tự động mất đi.

### 4.1.4       Vùng đệm trong

Như đã biết, vùng đệm trong là khoảng không nằm giữa vùng nội dung (content area) và đường viền (border). Nếu đường viền không được thiết lập thì vùng đệm này cũng có thể xem như một “đường viền” cho vùng nội dung.

Với mỗi phần tử, khi thiết lập màu nền và đường viền thì cũng nên thiết lập luôn vùng đệm trong, điều này giúp cho vùng nội dung được gọn gàng, cân đối, tránh tình trạng văn bản nằm quá sát với đường viền.

Có thể thêm vùng đệm trong cho cả hai loại phần tử block và inline.

Có thể thêm vùng đệm trong cho từng cạnh, hoặc cả bốn cạnh một lần.

Để thêm vùng đệm trong cho từng cạnh, sử dụng các thuộc tính sau,

_padding-top, padding-right, padding-bottom, padding-left_:

– Giá trị: _đơn vị đo chiều dài | %_

– Mặc định: _0_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ,
```html
p {

padding-top: 1em;

padding-right: 3em;

padding-bottom: 1em;

padding-left: 3em;

background-color: #D098D4;

}
```

Xem hình minh họa,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEjycysktIomCnKP39dkFt7R9LFag0zDHhvM_XjkusE25wfLw4R629PGdXfAFuxRp-95-Jlis44tasECl63F6rTncgL3crSiKyNTEvW4oLPFJLXVh7jq7owuQFhEjdwnrMQ1-i0lKCvfBR2yWbfrchULe9ur2-UTt8CVW4fOcdVUBbmmjaeXtLlBuPP0D1c=w400-h151)](https://blogger.googleusercontent.com/img/a/AVvXsEjycysktIomCnKP39dkFt7R9LFag0zDHhvM_XjkusE25wfLw4R629PGdXfAFuxRp-95-Jlis44tasECl63F6rTncgL3crSiKyNTEvW4oLPFJLXVh7jq7owuQFhEjdwnrMQ1-i0lKCvfBR2yWbfrchULe9ur2-UTt8CVW4fOcdVUBbmmjaeXtLlBuPP0D1c)

  

Đơn vị để thiết lập padding có thể là _em_, _px_ hoặc % (phần trăm chiều rộng của phần tử cha).

Lưu ý, khi thiết lập padding là %, nếu chiều rộng của phần tử cha thay đổi, sẽ dẫn tới padding bị thay đổi theo, điều này làm cho việc kiểm soát bố cục phức tạp.

**Thuộc tính padding**

Ngoài cách thiết lập padding cho từng cạnh, có thể sử dụng thuộc tính _padding_ để thiết lập một lần cho bốn cạnh.

Thuộc tính _padding_,

– Giá trị: _đơn vị đo chiều dài | %_

– Mặc định: _0_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Thuộc tính padding có thể chấp nhận bốn, ba, hai, hoặc một giá trị.

Khi padding có bốn giá trị, các giá trị này sẽ được áp dụng lần lượt cho các cạnh tương ứng, theo chiều kim đồng hồ, bắt đầu là cạnh trên (top), sau đó đến cạnh phải (right), cạnh dưới (bottom), cuối cùng là cạnh trái (left). Để dễ nhớ, tiếng Anh có từ TRouBLe, mỗi chữ viết hoa sẽ ứng với một cạnh.

Cú pháp,

padding: top right bottom left;

Ví dụ,
```html
p {

padding: 1em 3em 1em 3em;

background-color: #D098D4;

}
```

Nếu giá trị padding của cạnh trái và phải bằng nhau, thì có thể rút gọn thuộc tính padding còn lại ba giá trị. Khi đó, giá trị của cạnh phải (giá trị thứ hai trong chuỗi giá trị) cũng được sử dụng làm giá trị cho cạnh trái. Thực tế là, khi biên dịch mã CSS, trình duyệt thấy thiếu giá trị của cạnh trái nên nó mặc định lấy giá trị của cạnh phải để thay vào.

Cú pháp,

padding: top right/left bottom;

Ví dụ, chỉ dẫn CSS ở phía trên có thể viết gọn lại như sau,
```html
p {

padding: 1em 3em 1em;

background-color: #D098D4;

}
```

Tiếp tục, nếu chỉ cung cấp hai giá trị cho thuộc tính _padding_, thì giá trị đầu tiên sẽ là của cạnh trên và dưới, giá trị thứ hai sẽ là của cạnh trái và phải.

Cú pháp,

padding: top/bottom right/left;

Ví dụ, chỉ dẫn CSS ở phía trên có thể viết gọn lại như sau,
```html
p {

padding: 1em 3em;

background-color: #D098D4;

}
```

Cuối cùng, nếu chỉ cung cấp một giá trị cho thuộc tính _padding_, thì giá trị này sẽ là của cả bốn cạnh.

Ví dụ, chỉ dẫn CSS sau sẽ thiết lập _padding_ cho cả bốn cạnh là 15px,
```html
p {

padding: 15px;

background-color: #D098D4;

}
```
### 4.1.5       Đường viền

Đường viền là đường bao quanh phần tử (gồm vùng nội dung và vùng đệm trong). Có tám kiểu đường viền, Ngoài ra, có thể định dạng độ dày và màu sắc tùy ý. Có thể thiết lập đường viền xung quanh phần tử, hoặc chỉ thiết lập cho một số cạnh cụ thể. CSS cũng cung cấp các thuộc tính giúp tạo các góc bo tròn (rounding of the corners) và tạo đường viền bằng hình ảnh.

**Các kiểu đường viền**

Thuộc tính xác định kiểu đường viền là thuộc tính quan trọng nhất, vì theo đặc tả của CSS, nếu không có thuộc tính này, các thuộc tính còn lại liên quan đến đường viền sẽ bị bỏ qua.

Có thể thiết lập kiểu đường viền cho từng cạnh bằng các thuộc tính: _border-top-style, border-right-style, border-bottom-style, border-left-style,_

– Giá trị: _none | dotted | dashed | solid | double | groove | ridge | inset | outset | hidden_

– Mặc định: _none_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ sau sẽ thiết lập bốn kiểu đường viền khác nhau cho bốn cạnh,
```html
p {

border-top-style: solid;

border-right-style: dashed;

border-bottom-style: double;

border-left-style: dotted;

width: 300px;

height: 100px;

}
```

Hình sau minh họa các kiểu của đường viền,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEguIeL3z4VxaQ6I2WysA5V-Kt979Otj3MOMf-fttAf0aNj-xgjYY0LDn8f-eTlNvUbbKLMHPpRAK14SSub53VONVdq1Q_oUIopRe4i6t90zkxHRi_RAb5YvoUxtcjjOeH2LJgo6FKFn9eDsAVY6gvlUuYhx0Txh_SdZzhnunGVpdYpRAW_8TCjgYhLo4eg=w400-h272)](https://blogger.googleusercontent.com/img/a/AVvXsEguIeL3z4VxaQ6I2WysA5V-Kt979Otj3MOMf-fttAf0aNj-xgjYY0LDn8f-eTlNvUbbKLMHPpRAK14SSub53VONVdq1Q_oUIopRe4i6t90zkxHRi_RAb5YvoUxtcjjOeH2LJgo6FKFn9eDsAVY6gvlUuYhx0Txh_SdZzhnunGVpdYpRAW_8TCjgYhLo4eg)

  

Cũng có thể thiết lập kiểu đường viền cho cả bốn cạnh một lần bằng thuộc tính: _border-style,_

– Giá trị: _none | dotted | dashed | solid | double | groove | ridge | inset | outset | hidden_

– Mặc định: _none_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Thuộc tính _border-style_ thiết lập kiểu đường viền cho bốn cạnh theo chiều kim đồng hồ (clockwise). Giống như thuộc tính _padding_ đã tìm hiểu, thứ tự các cạnh sẽ được áp dụng sẽ là trên, phải, dưới, trái (để dễ nhớ, sử dụng từ TRouBLe rồi phiên ra thứ tự). Cần cung cấp bốn giá trị cho bốn cạnh này, tuy nhiên, nếu cạnh _trên/dưới_ và _phải/trái_ có kiểu giống nhau thì chỉ cần cung cấp hai giá trị, nếu cả bốn cạnh có kiểu giống nhau thì chỉ cần cung cấp một giá trị.

Ví dụ,
```html
p {

border-style: solid dashed double dotted;

width: 300px;

height: 100px;

}
```

Lưu ý: nếu không thiết lập giá trị cho độ dày của đường viền, thì giá trị mặc định là medium (trung bình) sẽ được sử dụng. Nếu không thiết lập màu cho đường viền, thì màu mặc định sẽ là màu mặt trước (foreground color) của phần tử (cùng màu với văn bản).

**Độ dày của đường viền**

Có thể thiết lập độ dày cho từng cạnh đường viền bằng các thuộc tính: _border-top-width, border-right-width, border-bottom-width, border-left-width,_

– Giá trị: _đơn vị đo độ dày | thin | medium | thick_

– Mặc định: _medium_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ sau sẽ thiết lập độ dày cho từng cạnh,
```html
p {

border-top-width: thin;

border-right-width: medium;

border-bottom-width: thick;

border-left-width: 12px;

border-style: solid;

width: 300px;

height: 100px;

}
```

Đơn vị đo độ dày thường là _px_ hoặc _em_. Tuy nhiên, cũng có thể sử dụng các từ khóa: _thin_ (mỏng), _medium_ (vừa, trung bình) hoặc _thick_ (dày).

Cũng có thể thiết lập độ dày cho cả bốn cạnh một lần bằng thuộc tính: _border-width,_

– Giá trị: _đơn vị đo độ dày | thin | medium | thick_

– Mặc định: _medium_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Thuộc tính _border-width_ thiết lập độ dày cho bốn cạnh theo chiều kim đồng hồ (clockwise). Giống như thuộc tính _border-style_, thứ tự các cạnh sẽ được áp dụng sẽ là trên, phải, dưới, trái (để dễ nhớ, sử dụng từ TRouBLe rồi phiên ra thứ tự). Cần cung cấp bốn giá trị cho bốn cạnh này, tuy nhiên, nếu cạnh _trên/dưới_ và _phải/trái_ có độ dày bằng nhau thì chỉ cần cung cấp hai giá trị, nếu cả bốn cạnh có độ dày bằng nhau thì chỉ cần cung cấp một giá trị.

Ví dụ,
```html
p {

border-width: thin medium thick 12px;

border-style: solid;

width: 300px;

height: 100px;

}
```

**Màu của đường viền**

Để thiết lập màu cho đường viền, cũng có thể thiết lập cho từng cạnh, hoặc cho tất cả các cạnh một lần. Khi thiết lập màu cho đường viền, nó sẽ đè lên màu đường viền trước đó (được thiết lập bằng thuộc tính _color_).

Có thể thiết lập màu cho từng cạnh bằng các thuộc tính: _border-top-color, border-right-color, border-bottom-color, border-left-color,_

– Giá trị: _tên màu hoặc giá trị RGB/HSL | transparent_

– Mặc định: _màu do thuộc tính color thiết lập_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ sau sẽ thiết lập màu cho từng cạnh,
```html
p {

border-top-color: green;

border-right-color: red;

border-bottom-color: violet;

border-left-color: yellow;

border-width: 6px;

border-style: solid;

width: 300px;

height: 100px;

}
```

Cũng có thể thiết lập màu cho cả bốn cạnh một lần bằng thuộc tính _border-color,_

– Giá trị: _tên màu hoặc giá trị RGB/HSL | transparent_

– Mặc định: _màu do thuộc tính color thiết lập_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Thuộc tính _border-color_ thiết lập màu cho bốn cạnh theo chiều kim đồng hồ (clockwise). Giống như thuộc tính _border-width_, thứ tự các cạnh sẽ được áp dụng sẽ là trên, phải, dưới, trái (để dễ nhớ, sử dụng từ TRouBLe rồi phiên ra thứ tự). Cần cung cấp bốn giá trị cho bốn cạnh này, tuy nhiên, nếu cạnh _trên/dưới_ và _phải/trái_ có màu giống nhau thì chỉ cần cung cấp hai giá trị, nếu cả bốn cạnh có màu giống nhau thì chỉ cần cung cấp một giá trị.

Ví dụ, cạnh trên/dưới có màu xanh, cạnh phải/trái có màu đỏ,
```html
  p {

border-color: green red;

border-width: 6px;

border-style: solid;

width: 300px;

height: 100px;

}
```

**Kết hợp kiểu, độ dày và màu**

Để viết mã nhanh hơn, CSS cho phép định dạng cả ba giá trị gồm: kiểu, độ dày và màu một lần cho từng cạnh, hoặc một lần cho cả bốn cạnh.

Để định dạng cho từng cạnh, sử dụng các thuộc tính: _border-top, border-right, border-bottom và border-left._

– Giá trị: _border-style border-width border-color_

– Mặc định: _giá trị mặc định của mỗi thuộc tính_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ,
```html
p {

border-top: solid 6px green;

border-right: solid 6px red;

border-bottom: solid 6px violet;

border-left: solid 6px yellow;

width: 300px;

height: 100px;

}
```

Để định dạng một lần cho cả bốn cạnh, sử dụng thuộc tính _border_, các giá trị của thuộc tính border sẽ luôn luôn áp dụng trên cả bốn cạnh,

– Giá trị: _border-style border-width border-color_

– Mặc định: _giá trị mặc định của mỗi thuộc tính_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ,
```html
  p {

    border: solid 6px green;

    width: 300px;

    height: 100px;

  }
```

Thứ tự các giá trị thuộc tính _border_ là không quan trọng, ngoài giá trị _border-style_ bắt buộc phải có, hai thuộc tính còn lại là tùy chọn.

**Tạo góc bo tròn**

Để tạo bo tròn cho từng góc, sử dụng các thuộc tính _border-top-left-radius, border-top-right-radius,_ _border-bottom-right-radius, border-bottom-left-radius,_ 

– Giá trị: _đơn vị đo chiều dài | %_

– Mặc định: _0_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Để tạo bo tròn cho cả bốn góc, sử dụng thuộc tính _border-radius_, bốn giá trị được thiết lập lần lượt cho các góc: _top-left, top-right, bottom-right, bottom-left_. Nếu chỉ cung cấp hai giá trị, thì giá trị đầu là của góc _top-left_ và _bottom right_, giá trị thứ hai cho hai góc còn lại.

– Giá trị: _1, 2, 3, hoặc 4 đơn vị đo chiều dài | %_

– Mặc định: _0_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Lưu ý: để có thể nhìn thấy góc bo tròn, bắt buộc phần tử phải được thiết lập đường viền (border), hoặc màu nền của phần tử phải khác màu nền của trang web. Đơn vị đo của bo tròn có thể là _em_ hoặc _pixel_. Nếu dùng đơn vị là _%_, độ lớn bo tròn sẽ luôn được giữ cân đối, khi kích thước của phần tử thay đổi.

**Tạo góc bo elipse**

Để tạo góc bo elipse, cần cung cấp hai giá trị là bo theo chiều ngang (horizontal) và bo theo chiều dọc (vertical).

Ví dụ,
```html
  p {

    border: solid 6px green;

    width: 300px;

    height: 100px;

    border-top-right-radius: 15px 30px;

  }
```

Nếu sử dụng thuộc tính _border-radius_ thì giá trị của chiều ngang và chiều dọc sẽ ngăn cách nhau bằng dấu xuyệt (/).

Ví dụ,
```html
  p {

    border: solid 6px green;

    width: 300px;

    height: 100px;

    border-radius: 15px / 40px;

  }
```

Tuy nhiên, để xác định chiều ngang và chiều dọc cho từng góc, các giá trị chiều ngang sẽ viết liền nhau, các giá trị chiều dọc sẽ viết liền nhau, ngăn cách nhau bằng dấu xuyệt.

Ví dụ,
```html
  p {

    border: solid 6px green;

    width: 300px;

    height: 100px;

    border-radius: 36px 40px 60px 20px / 12px 10px 30px 36px;

  }
```

**Tạo đường viền bằng hình ảnh**

Để tạo đường viền và bo góc bằng hình ảnh, sử dụng thuộc tính _border-image_.

– Giá trị: _border-image-source border-image-slice border-image-width border-image-outset border-image-repeat_

– Mặc định: _giá trị mặc định của mỗi thuộc tính_

– Áp dụng: _mọi phần tử ngoại trừ phần tử table có border-collapse là collapse_

– Kế thừa: _không_

Để dễ hiểu, quan sát hình minh họa dưới đây.

[![](https://blogger.googleusercontent.com/img/a/AVvXsEjDIiGsy3BM782LJDCj5YVfMLRY2qv0E4S7ruyBc3gVijlPH3UpI-qrUbcg-8DUJEeYzjrkUcYEzVBZ1pMCjVzGysVoS_4q4WGji5d1GX5o0WE4EZnWghd14sg_EP97v398daaEb3NBEX5JUe-oIxt19e8FX6LHHONa_z883T1F5R2DY2hlabFcSjEiIo4=w400-h330)](https://blogger.googleusercontent.com/img/a/AVvXsEjDIiGsy3BM782LJDCj5YVfMLRY2qv0E4S7ruyBc3gVijlPH3UpI-qrUbcg-8DUJEeYzjrkUcYEzVBZ1pMCjVzGysVoS_4q4WGji5d1GX5o0WE4EZnWghd14sg_EP97v398daaEb3NBEX5JUe-oIxt19e8FX6LHHONa_z883T1F5R2DY2hlabFcSjEiIo4)

  

Hình (a), (c) là hình gốc, được sử dụng để làm đường viền cho hình (b) và (d) tương ứng.

Hình gốc sẽ được cắt thành chín phần, các nét đứt chính là đường cắt, bốn góc của hình gốc sẽ được dùng làm bốn góc bo của đường viền, bốn cạnh của hình gốc sẽ dùng để tạo ra bốn đường viền tương ứng, còn lại một phần ở giữa hình gốc không sử dụng.

Vị trí của các đường cắt được chỉ ra bằng bộ-bốn-giá-trị theo thứ tự: _top, right, bottom, left_. Mỗi giá trị chính là khoảng lùi, tính từ mỗi cạnh vào phía trong của hình gốc, đơn vị tính là px.

Đường viền của phần tử sẽ được phủ kín bằng cạnh tương ứng của hình gốc, việc phủ kín được thực hiện bằng cách lặp lại cạnh gốc (tile) hoặc kéo dãn cạnh gốc (stretch).

Cú pháp của thuộc tính _border-image_,

```border-image: url(anhgoc.png) top right bottom left stretch```

Ví dụ, đường viền của hình (b) được tạo bằng đoạn mã CSS sau,

```border-image: url(a.png) 55 55 55 55 stretch```

Nếu bốn đường cắt có giá trị giống nhau thì có thể viết rút gọn thành một giá trị, ví dụ đoạn mã trên có thể viết lại gọn hơn là,

```border-image: url(a.png) 55 stretch```

Ví dụ, đường viền của hình (d) được tạo bằng đoạn mã CSS sau,

```border-image: url(c.png) 20 10 20 10 round```

Để lặp lại cạnh gốc có thể sử dụng từ khóa _round_ (vừa lặp lại vừa kéo căng cạnh gốc cho vừa với đường viền) hoặc _repeat_ (chỉ lặp lại cạnh gốc).

Ví dụ, tạo đường viền bằng hình ảnh, có thêm tiếp đầu ngữ _-webkit_ và _-o_ để đoạn mã làm việc tốt trên cả hai trình duyệt Safari và Opera tương ứng,
```html
p {

    border: 10px solid transparent;

    padding: 15px;

    -webkit-border-image: url(border.png) 30 round; /* Safari 3.1-5 */

    -o-border-image: url(border.png) 30 round; /* Opera 11-12.1 */

    border-image: url(border.png) 30 round;

}
```

Thuộc tính _border-image_ còn hai giá trị nữa, _border-image-width_ để xác định độ rộng của đường-viền-ảnh, và _border-image-outset_ để xác định kích thước phần đường-viền-ảnh tràn ra phía ngoài phần tử.

### 4.1.6       Vùng đệm ngoài

Thành phần cuối cùng của mô hình cái hộp là “vùng đệm ngoài” (margin), đây là vùng tùy chọn, là khoảng-không được thêm vào phía ngoài của đường viền (border).

Vùng đệm ngoài giúp phần tử không bị dính (nằm quá sát) vào phần tử khác hoặc nằm quá sát so với cạnh của cửa sổ trình duyệt.

Thuộc tính _margin_ làm việc khá giống với thuộc tính _padding_, để thêm vùng đệm ngoài cho từng cạnh, sử dụng các thuộc tính: _margin-top, margin-right, margin-bottom, margin-left_:

– Giá trị: _đơn vị đo chiều dài | % |  auto_

– Mặc định: _auto_

– Áp dụng: _mọi phần tử_

– Kế thừa: _không_

Ví dụ,
```html
p {

margin-top: 2em;

margin-right: 250px;

margin-bottom: 1em;

margin-left: 4em;

border: 1px solid red;

background: #fcf2be;

}
```

Đơn vị để thiết lập margin có thể là _em_, _px_ hoặc % (phần trăm chiều rộng của phần tử cha).

Lưu ý, khi thiết lập margin là %, nếu chiều rộng của phần tử cha thay đổi, sẽ dẫn tới margin bị thay đổi theo, điều này làm cho việc kiểm soát bố cục phức tạp.

Từ khóa _auto_ là chế độ thiết lập vùng đệm ngoài mặc định của trình duyệt. Với chế độ này, nhiều khi làm cho người thiết kế web không thể kiểm soát chính xác được bố cục, giải pháp là đặt lại (reset) giá trị margin và padding của mọi phần tử về 0. Ví dụ,
```html
* {

margin: 0;

padding: 0;

}
```

Lưu ý: khi giá trị là 0 thì không cần cung cấp đơn vị đo.

Để thiết lập vùng đệm ngoài cho bốn cạnh một lần, sử dụng thuộc tính _margin_.

Thuộc tính _margin_:

– Giá trị: _đơn vị đo chiều dài | % |  auto_

– Mặc định: _auto_

– Áp dụng: _mọi phần tử, ngoại trừ các phần tử tr, th, td_

– Kế thừa: _không_

Thuộc tính _margin_ có thể chấp nhận bốn, ba, hai, hoặc một giá trị.

Khi _margin_ có bốn giá trị, các giá trị này sẽ được áp dụng lần lượt cho các cạnh tương ứng, theo chiều kim đồng hồ, bắt đầu là cạnh trên (top), sau đó đến cạnh phải (right), cạnh dưới (bottom), cuối cùng là cạnh trái (left). Để dễ nhớ, tiếng Anh có từ TRouBLe, mỗi chữ viết hoa sẽ ứng với một cạnh.

Cú pháp,

margin: top right bottom left;

Ví dụ,
```html
p {

margin: 1em 3em 1em 3em;

background-color: #d098d4;

}
```

Nếu giá trị _margin_ của cạnh trái và phải bằng nhau, thì có thể rút gọn thuộc tính _margin_ còn lại ba giá trị. Khi đó, giá trị của cạnh phải (giá trị thứ hai trong chuỗi giá trị) cũng được sử dụng làm giá trị cho cạnh trái. Thực tế là, khi biên dịch mã CSS, trình duyệt thấy thiếu giá trị của cạnh trái nên nó mặc định lấy giá trị của cạnh phải để thay vào.

Cú pháp,

margin: top right/left bottom;

Ví dụ, chỉ dẫn CSS ở phía trên có thể viết gọn lại như sau,
```html
p {

margin: 1em 3em 1em;

background-color: #d098d4;

}
```

Tiếp tục, nếu chỉ cung cấp hai giá trị cho thuộc tính _margin_, thì giá trị đầu tiên sẽ là của cạnh trên và dưới, giá trị thứ hai sẽ là của cạnh trái và phải.

Cú pháp,

margin: top/bottom right/left;

Ví dụ, chỉ dẫn CSS ở phía trên có thể viết gọn lại như sau,
```html
p {

margin: 1em 3em;

background-color: #d098d4;

}
```

Cuối cùng, nếu chỉ cung cấp một giá trị cho thuộc tính _margin_, thì giá trị này sẽ là của cả bốn cạnh.

Ví dụ, chỉ dẫn CSS sau sẽ thiết lập _margin_ cho cả bốn cạnh là 15px,
```html
p {

margin: 15px;

background-color: #d098d4;

}
```

Mặc dù cách làm việc của thuộc tính _margin_ khá đơn giản, tuy nhiên, cũng cần lưu ý một số trường hợp đặc biệt sau đây: hiện tượng thu gọn margin (collapse), margin cho các phần tử kiểu inline và margin có giá trị âm.

**Hiện tượng thu gọn margin**

Hiện tượng này xảy ra với margin top và bottom. Cụ thể, với hai margin (top hoặc bottom) của hai phần tử cạnh nhau, thay vì cộng dồn giá trị (của top và bottom) lại thì sẽ lấy giá trị lớn hơn.

Ví dụ, phần tử A có margin bottom là 4px, phần tử B nằm ngay phía dưới phần tử A, và có margin top là 2px; khi đó, giá trị margin giữa A và B sẽ là 4px, chứ không phải 6px.

Hiện tượng thu gọn margin không xảy ra nếu thuộc tính _position_ của phần tử được thiết lập là _absolute_ hoặc _float_.

**Margin cho phần tử kiểu inline**

Với các phần tử inline-văn-bản, chỉ có thể thiết lập margin left và margin right, và giá trị của margin này đã bao gồm luôn cả khoảng trắng ở phía trước và phía sau phần tử.

Tuy nhiên, với phần tử inline còn lại (ví dụ, phần tử _img_) thì có thể thiết lập margin cho cả bốn cạnh.

Xem hình ví dụ,

[![](https://blogger.googleusercontent.com/img/a/AVvXsEgRJerAETgaXJGAMxfe9zrUtS_eysnTGAdnyfzDjOcLGE2mDw814posn-avcsW58EOuDKPaPXGMyEQTzUVq6QcV4-WYALndUIMm_mYZ0Mkj1bCjUXqRsLNKP03Oavm5dkpwtsd5VPH-FZP7ZUSYCv7lC7GHdo53Ak-vy06QXMZ6pcGCxicoVtEGhx6re-Q=w400-h285)](https://blogger.googleusercontent.com/img/a/AVvXsEgRJerAETgaXJGAMxfe9zrUtS_eysnTGAdnyfzDjOcLGE2mDw814posn-avcsW58EOuDKPaPXGMyEQTzUVq6QcV4-WYALndUIMm_mYZ0Mkj1bCjUXqRsLNKP03Oavm5dkpwtsd5VPH-FZP7ZUSYCv7lC7GHdo53Ak-vy06QXMZ6pcGCxicoVtEGhx6re-Q)

  

**Margin có giá trị âm**

Với margin có giá trị dương, toàn bộ nội dung, vùng đệm trong và đường viền của phần tử lân cận sẽ được dịch chuyển ra xa. Tuy nhiên, nếu margin có giá trị âm, các thành phần trên của phần tử lân cận sẽ dịch chuyển theo chiều ngược lại.

Quan sát ví dụ trong hình dưới đây, gồm hai phần tử _p_ nằm cạnh nhau. Hình bên trái, thiết lập _margin-bottom_ _4em_ cho đoạn đầu tiên, kết quả làm cho đoạn phía dưới bị đẩy xuống một khoảng. Hình bên phải, thiết lập _margin-bottom -4em_ cho đoạn đầu tiên, kết quả làm cho đoạn thứ hai dịch chuyển lên, và phủ lấp vào đoạn đầu tiên.

[![](https://blogger.googleusercontent.com/img/a/AVvXsEjZUfVCJhDbusq1FDNNDyFIR5HDLw2Towo77BynnXZ13xSKA87U4l2lkaBDeBFc6Sejj8Wb14lV60QpQd1AtSXCimW-vA0QOCWQuA2ftaa1MAeD6zwdVrCMpdpeKJcr3bQt5MEWTQe5562cPi-K-pjPwRyVxUbpl87tgRVQxKwaSUcwfl9v6kOi31mrPWE=w400-h189)](https://blogger.googleusercontent.com/img/a/AVvXsEjZUfVCJhDbusq1FDNNDyFIR5HDLw2Towo77BynnXZ13xSKA87U4l2lkaBDeBFc6Sejj8Wb14lV60QpQd1AtSXCimW-vA0QOCWQuA2ftaa1MAeD6zwdVrCMpdpeKJcr3bQt5MEWTQe5562cPi-K-pjPwRyVxUbpl87tgRVQxKwaSUcwfl9v6kOi31mrPWE)

  

Sử dụng margin với giá trị dương và âm cho phép di chuyển một phần tử tới mọi vị trí trong một trang. Đây là một trong những kĩ thuật cơ bản trong việc tạo bố cụ trang web.
