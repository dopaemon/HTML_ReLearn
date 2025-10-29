# 1. Làm quen với JavaScript

## 1.1 Vài thông tin chung về JavaScript
-------------------------------------

JavaScript là gì?

JavaScript (JS) là một ngôn ngữ lập trình đa mẫu hình (multi-paradigm language) được Brendan Eich phát triển vào năm 1995. Tên ban đầu của nó là Mocha, sau đó là LiveScript, và cuối cùng được gọi là JavaScript.

JavaScript không chỉ là một ngôn ngữ "chạy trên trình duyệt" mà còn hỗ trợ nhiều mẫu hình lập trình (paradigm) mạnh mẽ như:

- Lập trình kịch bản (Scripting)

- Lập trình hướng đối tượng (Object-Oriented Programming - OOP)

- Lập trình hàm (Functional Programming)

- Lập trình hướng sự kiện (Event-driven)

- Lập trình mệnh lệnh (Imperative)

Tập tin mã nguồn JavaScript có phần mở rộng là .js.

Ứng dụng của JavaScript

Ban đầu, JavaScript chỉ dùng để xử lý các tương tác trên trình duyệt (Front-end). Ngày nay, nhờ sự phát triển mạnh mẽ của các nền tảng và Framework, JavaScript đã trở thành một ngôn ngữ toàn diện, được sử dụng để lập trình trong các lĩnh vực sau:

Lĩnh vực

Vai trò

Công nghệ/Framework tiêu biểu

Web Front-end

Xử lý giao diện, tương tác người dùng

React, Angular, Vue.js, jQuery

Web Back-end

Xây dựng API, logic nghiệp vụ, máy chủ

Node.js (với Express, Next.js), NestJS

Ứng dụng Di động

Ứng dụng đa nền tảng (iOS/Android)

React Native

Ứng dụng Desktop

Ứng dụng chạy trên máy tính (Windows/macOS)

Electron

ECMAScript: Tiêu chuẩn hóa JavaScript

Cũng như mọi ngôn ngữ lập trình khác, JavaScript không ngừng được cải tiến. Để chuẩn hóa và quản lý các thay đổi này, tổ chức European Computer Manufacturers Association (ECMA) đã tiếp nhận và phát triển một tiêu chuẩn có tên là ECMAScript (thường gọi tắt là ES).

Các phiên bản của JavaScript mà chúng ta đang sử dụng đều tuân theo tiêu chuẩn ECMAScript. Đặc biệt, phiên bản ES6 (ECMAScript 2015) là một cột mốc quan trọng, mang lại nhiều cú pháp hiện đại.

Phiên bản chuẩn

Năm ra đời

Ghi chú

ES5

2009

Phiên bản phổ biến trước khi có cải tiến lớn

ES6 / ES2015

2015

Phiên bản đột phá với const, let, Arrow Function, Class, Promise

ES2016

2016

Các phiên bản sau này được đặt tên theo năm ra đời

ES2017 - ES2023

2017 - 2023

Các bản cập nhật hàng năm, bổ sung tính năng mới

Trong giáo trình này, chúng ta sẽ tập trung vào các phiên bản hiện đại (ES6 trở lên) để nắm bắt các công nghệ lập trình mới nhất.

## 1.2 Chương trình JavaScript đầu tiên
------------------------------------

Để bắt đầu lập trình JavaScript, bạn cần biết: viết mã ở đâu và chạy mã ở đâu. Với JavaScript, mọi thứ rất linh hoạt.

Để lập trình với JavaScript, bạn có vài lựa chọn sau:

Vai trò

Công cụ sửa dụng

Ghi chú

Trình viết mã

(Code Editor, IDE)

VS Code, Sublime Text, WebStorm, Notepad, Các trang web trực tuyến, Phần mềm tính hợp AI (Cursor), Các phần mềm sinh mã tự động

Dùng để viết và chỉnh sửa mã nguồn JS

Trình thông dịch/Thực thi

(Interpreter/Runtime)

  

Trình duyệt Web (Chrome, Firefox)

Có sẵn JavaScript Interpreter để dịch và chạy mã Front-end

Node.js

Môi trường Back-end, để dịch và chạy mã JavaScript độc lập

Đối với lập trình Front-end, Trình duyệt Web đóng vai trò kép: vừa là môi trường chạy mã (Runtime) vừa là nơi hiển thị kết quả.

Chúng ta cùng thực hành, trải nghiệm và chạy một chương trình JavaScript trên một số môi trường khác nhau:

Cách 1: Chạy trên Trình duyệt (Console)

Đây là cách nhanh nhất để thử nghiệm các đoạn mã ngắn.

- Mở trình duyệt web (ví dụ: Chrome, Firefox)

- Mở cửa sổ Developer Tools (Công cụ dành cho nhà phát triển) bằng cách nhấn F12 hoặc chuột phải vào màn hình trình duyệt > chọn Inspect (Kiểm tra)

- Chọn tab Console

[![](https:blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg_UTlkf-S7j1uXXS0HjBNjlKlDO34CkDvBgcrCsiIuBSWTSeMKZT55tRcxsDPwyDs2ZwUXdBsxmd-eTLNdV00J3B7E7xcWULmyyBpv_xCIbSyWEQnqKg61jAdmqCdxa6I6F2ao8rrrxwb5Dm8P_fE1oCP0tJIlqx9ulAxXBesp6fSO_j_MSrBnSV4bgjM/s320/js_console.png)](https:blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg_UTlkf-S7j1uXXS0HjBNjlKlDO34CkDvBgcrCsiIuBSWTSeMKZT55tRcxsDPwyDs2ZwUXdBsxmd-eTLNdV00J3B7E7xcWULmyyBpv_xCIbSyWEQnqKg61jAdmqCdxa6I6F2ao8rrrxwb5Dm8P_fE1oCP0tJIlqx9ulAxXBesp6fSO_j_MSrBnSV4bgjM/s947/js_console.png)

  

- Nhập dòng mã sau, sau đó nhấn Enter:  
console.log('Xin chao, toi la JavaScript!');

(Kết quả sẽ hiển thị ngay bên dưới dòng lệnh.)

- Để xóa sạch màn hình Console, gõ lệnh console.clear(); hoặc nhấn Ctrl + L.

Cách 2: Nhúng JavaScript trong Tài liệu HTML (Front-end)

Trong lập trình Front-end, bạn nhúng mã JS trực tiếp vào tài liệu HTML bằng thẻ <script>.

- Tạo một tập tin HTML mới (ví dụ: index.html)

- Nhập đoạn mã sau vào tập tin index.html:
```html
<!DOCTYPE html>

<html>

<head>

<title>Chuong trinh dau tien</title>

</head>

<body>

<h1>Hello World!</h1>

<script>

 Mã JavaScript được đặt ở đây

alert("Chao mung ban den voi JavaScript!");

</script>

</body>

</html>
```

- Lưu tập tin và mở bằng trình duyệt. Một cửa sổ thông báo (alert box) sẽ xuất hiện với nội dung "Chao mung ban den voi JavaScript!".

Cách 3: Viết mã JavaScript trong tập tin riêng biệt

Đây là phương pháp tiêu chuẩn để lập trình web thực tế, giúp tách biệt mã HTML và mã JavaScript.

- Tạo một thư mục mới (ví dụ: BaiTap1)

- Trong thư mục đó, tạo hai tập tin: index.html và main.js.

- Trong index.html: Liên kết đến tập tin main.js bằng thuộc tính src trong thẻ <script>:  
[index.html]
```html
<!DOCTYPE html>

<html>

<head>

<title>Thuc hanh ket noi JS</title>

</head>

<body>

<button id='btnChange'>Thay doi mau nen</button>

  

<script src='main.js'></script>

</body>

</html>
```

- Trong main.js: Viết logic xử lý:  
[main.js]  
 1. Tim den phan tu nut bam trong HTML

const btn = document.getElementById('btnChange');

  

 2. Tao mot mang cac mau sac

const colors = ['red','orange','yellow','green','blue','purple'];

  

 3. Dinh nghia ham thay doi mau nen
```html
function changeColor(){

     Chon mot mau sac ngau nhien tu mang

    const randomColor = colors[Math.floor(colors.length * Math.random())];

  

     Gan mau nen moi cho the <body>

    document.body.style.background = randomColor;

}
```
  
 4. Gan su kien 'click' cho nut bam

btn.addEventListener('click', changeColor);

- Mở tập tin index.html bằng trình duyệt, sau đó nhấn nút "Thay doi mau nen" để thấy màu nền thay đổi ngẫu nhiên.

Cách 4: Chạy mã JavaScript trên nền tảng Node.js (Back-end)

Khi lập trình Back-end hoặc các ứng dụng độc lập, chúng ta cần môi trường Node.js để thực thi mã JS.

Các bước thực hiện:

Cài đặt Node.js:

- Truy cập trang web chính thức của Node.js: [https:nodejs.org/en/](https:nodejs.org/en/)

- Tải về và cài đặt phiên bản được đề xuất

- Sau khi cài đặt, mở Command Prompt (CMD) hoặc Terminal, gõ lệnh node -v và nhấn Enter

- Nếu phiên bản Node.js hiển thị, nghĩa là việc cài đặt đã thành công

Viết mã Back-end:

- Tạo một tập tin mới (ví dụ: my_backend.js)

- Nhập đoạn mã sau:

[my_backend.js]  
 Mã này sẽ chạy trên môi trường máy chủ (Server)

console.log('Chao mung, toi la Node.js!');

  

const sum = 10 + 20;

console.log('Ket qua phep cong: ' + sum);

Thực thi mã:

- Mở CMD/Terminal, di chuyển đến thư mục chứa tập tin my_backend.js

- Gõ lệnh sau và nhấn Enter:  
node my_backend.js

- Kết quả sẽ được in ra ngay trên cửa sổ dòng lệnh

Tóm lại: Bạn có thể bắt đầu với cửa sổ lập trình Console hoặc nhúng trong HTML để làm quen. Khi phát triển dự án thực tế, bạn sẽ dùng tập tin .js riêng biệt cho lập trình Front-end) hoặc Node.js (cho Back-end).

## 1.3 Bài tập
-----------

Bài tập 1a. Cài đặt và viết lại các đoạn mã trong phần lý thuyết.

Bài tập 1b. Sử dụng từ khóa Javascript roadmap để tìm kiếm và xem các nội dung cần học về JavaScript.

## 1.4 Câu hỏi ôn tập
------------------

Câu 1. Bạn có thể lập trình (viết mã) JavaScript bằng các công cụ sau. Đáp án nào sai?

A. Web browser

B. Text editor

C. Code editor, IDE

**D. JavaScript Interpreter**

Câu 2. Trong HTML, mã JavaScript được đặt trong phần tử nào?

A. <javascript>

**B. <script>**

C. <js>

D. <scripting>

Câu 3. Trong JavaScript, ES8 là viết tắt của?

A. Essential 8

**B. ECMAScript 8**

C. Explorer Source 8

D. European Script 8

Câu 4. JavaScript was created in …… by Brendan Eich, an employee of Netscape.

A. 1994

**B. 1995**

C. 1996

D. 2015
