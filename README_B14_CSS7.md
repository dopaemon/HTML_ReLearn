# CSS (7) - Định dạng chữ

## 2.2       Định dạng chữ
-----------------------

### 2.2.1       Cỡ chữ

Trong phần này, chúng ta sẽ tìm hiểu các nội dung sau:

– Thiết lập được cỡ chữ.

– Hiểu về các giá trị, các đơn vị đo có thể sử dụng để thiết lập cỡ chữ.

– Quan sát một số kinh nghiệm thiết lập cỡ chữ cho giao diện web.

Để thiết lập kích cỡ của chữ, sử dụng thuộc tính font-size:

– Giá trị: đơn vị đo chiều dài | phần trăm | xx-small | x-small | small | medium | large | x-large | xx-large | smaller | larger.

– Mặc định: medium.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Lưu ý, việc thiết lập cỡ chữ không chỉ làm thay đổi cỡ của chữ, mà nó còn làm thay đổi các độ đo dựa trên cỡ chữ, như em, ex.

Thuộc tính font-size có thể nhận các kiểu giá trị: các đơn vị đo kích thước, phần trăm, các từ khóa.

– Đơn vị đo kích thước tương đối (em, rem), tuyệt đối (px), ví dụ:
```css
h1 { font-size: 1.5em; }

h1 { font-size: 1.5rem; }

h1 { font-size: 30px; }
```

Lưu ý: đơn vị đo phải viết liền ngay sau giá trị số, viết như sau là bị lỗi,

```css h1 { font-size: 1.5 em; }```

– Giá trị %, thể hiện tỉ lệ (tăng hoặc giảm) so với cỡ chữ của phần tử mà nó kế thừa, ví dụ:

```css h1 { font-size: 150%; }```

Khi đó, nếu phần tử h1, là con của body. Mà body có cỡ 16px, thì h1 sẽ có cỡ chữ là 24px.

– Các từ khóa kiểu tuyệt đối, như: xx-small, x-small, small, medium, large, x-large, xx-large. Với hầu hết các trình duyệt, medium sẽ tương ứng với kích thước phông mặc định, ví dụ,

```css h1 { font-size: x-large; }```

– Các từ khóa kiểu tương đối, như: larger, smaller. Kết quả là chữ sẽ to hơn hoặc nhỏ hơn so với các chữ lân cận. Ví dụ,

```css strong { font-size: larger; }```

Để tối ưu trong lập trình, chúng ta nên sử dụng 2 đơn vị đo tương đối (em, rem) và giá trị phần trăm (%). Bạn cũng có thể sử dụng đơn vị đo tuyệt đối là px, tuy nhiên, nó không đảm bảo tính hiệu quả, uyển chuyển, và linh hoạt trong quá trình thiết kế trang web.

Về mặt tâm lý, người duyệt web sẽ có xu hướng cảm thấy dễ chịu, khi sử dụng những gì quen thuộc, được coi là mặc nhiên. Cỡ chữ cũng vậy.

Chúng ta có thể thiết lập cỡ chữ trong một trang web theo cách sau:

– Sử dụng cỡ chữ mặc định của trình duyệt (16px), bằng cách thiết lập cỡ chữ cho phần tử html là 100%. Bạn cũng có thể thiết lập cho phần tử body là 100% thay vì phần tử hmtl, tuy nhiên, thiết lập cho phần tử html để sử dụng được đơn vị đo là rem.

        ```css html { font-size: 100%; }```

– Các phần tử còn lại sẽ được thiết lập cỡ chữ dựa trên phần tử html, bằng cách dùng các đơn vị đo tương đối (rem, em, %). Ví dụ, cỡ chữ của tiêu đề không thiết lập cố định là 24px, mà nó sẽ là 1.5 so với cỡ chữ của phần tử html.

        ```css h1 { font-size: 1.5rem; } /* 1.5 x 16px = 24px */```

Đơn vị đo rem, là viết tắt của "root em", 1rem tương đương với kích thước phông chữ của phần tử html. Nếu kích thước phông chữ của html là 16px, thì 1rem = 16px.

Đơn vị đo em, là kích thước phông chữ của phần tử hiện tại. Nếu kích thước phông chữ của phần tử là 24px, thì 1em = 24px. Người ta hay dùng đơn vị đo em để thiết lập cho margin, padding, border, width, height cho một phần tử.

Có một câu hỏi thú vị là, nếu chúng ta muốn thiết lập kích thước phông chữ cho phần tử hiện tại bằng em thì sao? Ví dụ, chúng ta quan sát đoạn mã sau:

```css

    <style>

        html { font-size: 100%; }

        h1 { font-size: 1.5em; } /* 1.5 x 16px = 24px */

    </style>

</head>

<body>

    <h1>Tiêu đề h1</h1>

```

Ở đoạn mã trên, do h1 chưa được thiết lập kích thước phông chữ một cách tường minh, nhưng chúng ta lại dùng đơn vị đo em, nên h1 sẽ kế thừa kích thước phông chữ từ phần tử cha của nó (là html).

Quan sát thêm một ví dụ khác:
```css
    <style>

        html { font-size: 100%; }

        article { font-size: 0.875em } /* 0.875 x 16px = 14px */

        h1 { font-size: 1.5em; } /* 1.5 x 14px = 21px */

    </style>

</head>

<body>

    <article>

        <h1>Tiêu đề h1</h1>

    </article>
```
Quan sát hai đoạn mã ở trên, chúng ta thấy h1 đều được thiết lập kích thước phông chữ là 1.5em. Tuy nhiên, kích thước phông chữ thực tế là 24px và 21px cho hai trường hợp khác nhau, do phần tử cha của h1 ở hai trường hợp là khác nhau. Do vậy, đơn vị đo là em phụ thuộc vào từng ngữ cảnh cụ thể.

Nếu các phần tử lồng nhiều cấp, và đều dùng đơn vị đo là em sẽ dẫn tới tình trạng trình duyệt phải tính toán nhiều lần, vừa tốn thời gian, tốn tài nguyên và có thể bị sai lệch do làm tròn số.

Chúng ta cũng có thể sử dụng đơn vị phần trăm (%) để thiết lập cỡ chữ. CSS sẽ lấy cỡ chữ được kế thừa từ phần tử cha, nhân với giá trị %, để có được cỡ chữ của phần tử hiện tại. Ví dụ:

```css

    <style>

        html { font-size: 100%; }

        article { font-size: 75% } /* 75% x 16px = 12px */

        h1 { font-size: 150%; } /* 150% x 12px = 18px */

    </style>

</head>

<body>

    <article>

        <h1>Tiêu đề h1</h1>

    </article>

</body>

```

Ở đoạn mã trên, phần tử html kế thừa cỡ chữ mặc định của trình duyệt (16px), bằng cách thiết lập font-size: 100%. Phần tử article là con của html, có cỡ chữ: 75% x 16px = 12px. Phần tử h1 là con của article, có cỡ chữ: 150% x 12px = 18px.

Chúng ta đã tìm hiểu về các giá trị của thể sử dụng để thiết lập cỡ chữ. Tuy nhiên, để biết cách lựa chọn cỡ chữ phù hợp cho các nội dung khác nhau trên trang web, thì chúng ta cần đọc thêm các chủ đề chuyên sâu về trình bày văn bản hoặc quan sát cách thiết lập cỡ chữ trên các trang web đang có trên Internet. Ví dụ, bạn vào trang themeforest, tìm một giao diện bạn ưa thích và quan sát cỡ chữ của các nội dung khác nhau trên trang web.

### 2.2.2       Độ đậm của chữ

Chúng ta đã chọn được phông chữ và cỡ chữ cho văn bản. Phần này chúng ta sẽ thay đổi độ đậm nhạt (lạt) của văn bản, sử dụng thuộc tính font-weight:

– Giá trị (values): normal | bold | bolder | lighter | 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900.

– Mặc định: normal.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Mặc dù trong dãy các giá trị về độ đậm nhạt của phông chữ gồm có bốn từ khóa mô tả (normal, bold, bolder, lighter) và 9 giá trị thể hiện độ đậm của chữ (100,…,900). Tuy nhiên, trong thực tế các phông chữ thường chỉ có hai chế độ là normal và bold. Do vậy, đây chính là hai giá trị thường được sử dụng. Các trình duyệt cũng thường không hỗ trợ đầy đủ các giá trị về độ đậm nhạt. Với các giá trị số, thông thường giá trị từ 600 trở lên sẽ là chữ đậm.

Ví dụ,

dt { font-weight: bold; }

### 2.2.3       Kiểu chữ nghiêng

Sử dụng thuộc tính font-style để thiết lập kiểu dáng (posture) của văn bản. Văn bản thường có hai kiểu dáng là kiểu đứng (normal) và kiểu nghiêng (italic hoặc oblique).

Thuộc tính font-style:

– Giá trị: normal | italic | oblique.

– Mặc định: normal.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Cả hai giá trị italic và oblique đều hiển thị dạng chữ nghiêng, tuy nhiên, italic là một kiểu chữ được thiết kế riêng, trong khi oblique là kiểu chữ thông thường được hiển thị ở dạng nghiêng. Tuy vậy, kết quả hiển thị của văn bản, ứng với hai giá trị này, trên hầu hết các trình duyệt là như nhau.

### 2.2.4       Kiểu chữ hoa đặc biệt

Sử dụng thuộc tính font-variant với giá trị là small-caps để chuyển dạng chữ thường sang dạng chữ hoa,với kích thước ở dạng chữ hoa đúng bằng kích thước ở dạng chữ thường.

Thuộc tính font-variant:

– Giá trị: normal | small-caps.

– Mặc định: normal.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Để ý chữ small-caps chính là viết tắt của small capitals (chữ hoa nhỏ).

### 2.2.5       Viết rút gọn các thuộc tính phông

Ở các phần trên, chúng ta đã tìm hiểu một số thuộc tính liên quan đến phông chữ. Để tránh việc lặp lại và giảm số dòng mã, có thể sử dụng thuộc tính font để gom các định dạng liên quan đến phông vào chỉ dẫn CSS.

Thuộc tính font:

– Giá trị: font-style font-weight font-variant font-size/line-height font-family | inherit.

– Mặc định: tùy thuộc vào giá trị của mỗi thuộc tính được liệt kê ở trên.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Giá trị của thuộc tính font chính là giá trị của tất cả các thuộc tính đã được liệt kê ở trên, mỗi giá trị cách nhau bằng một khoảng trắng. Lưu ý: tính thứ tự của các giá trị là quan trọng, do vậy không thể xáo trộn vị trí của chúng, thứ tự cụ thể là,

{ font: style weight variant size/line-height font-family }

Ở dạng tối giản, thuộc tính font cũng phải có hai giá trị là font-size và font-family. Nếu thiếu một trong hai hoặc đặt sai vị trí sẽ dẫn tới chỉ dẫn bị lỗi. Ví dụ một chỉ dẫn tối giản,

p { font: 1em sans-serif; }

Nếu trong chỉ dẫn đã có hai giá trị bắt buộc (font-size và font-family) rồi, thì các giá trị còn lại sẽ là tùy chọn, miễn là đứng trước font-size. Nếu các giá trị của style, weight và variant không xác định thì CSS sẽ sử dụng giá trị mặc định là normal. Trong thuộc tính font còn có một giá trị mới là line-height, đây là chiều cao của hàng văn bản, được sử dụng để thêm khoảng trắng giữa các hàng, giá trị này nằm ngay sau giá trị font-size, ngăn cách bằng dấu xuyệt (/). Ví dụ,

h3 { font: oblique bold small-caps 1.5em/**1.8em** Verdana, sans-serif; }

h2 { font: bold 1.75em/**2** sans-serif; }

### 2.2.6       Màu chữ

Để thiết lập màu chữ, sử dụng thuộc tính color.

Thuộc tính color:

– Giá trị: giá trị màu (tên màu hoặc giá trị số).

– Mặc định: tùy thuộc vào trình duyệt và thiết lập của người dùng.

– Áp dụng: cho mọi phần tử.

– Kế thừa: có.

Giá trị của thuộc tính color có thể là tên màu, CSS2 cung cấp sẵn 17 tên màu, CSS3 cung cấp sẵn 140 tên màu. Ví dụ một số tên màu,

Black, white, purple, lime, navy, aqua, silver, maroon, fuchsia, olive, blue, orange, gray, red, green, yellow, teal.

Giá trị của thuộc tính color cũng có thể là giá trị số, bắt đầu là dấu #, hoặc rgb sau đó là bộ ba giá trị của ba màu cơ bản là Red, Green và Blue (RGB), Ví dụ, màu xám sẽ có giá trị là #666 hoặc #666666.

Ví dụ, để phần tử h1 có màu xám, có thể sử dụng một trong các chỉ dẫn CSS sau,
```css
h1 { color: gray; }

h1 { color: #666666; } /* R = 66, G = 66, B = 66 */

h1 { color: #666; } /* R = 6, G = 6, B = 6 */

h1 { color: rgb(102,102,102); }
```

Vì thuộc tính color có tính kế thừa, nên để thiết lập màu cho toàn bộ văn bản, thay vì làm cho từng phần tử thì có thể thực hiện một lần cho phần tử body. Ví dụ,

body { color: gray; }

Để ý là thuộc tính color không phải chỉ để thiết lập màu cho chữ, mà theo mô tả của CSS thì nó được sử dụng để thay đổi “màu mặt trước” (foreground color đối lập với màu nền – background) của một phần tử. Mặt trước bao gồm văn bản và đường biên. Do vậy, khi thiết lập màu cho phần tử (bao gồm phần tử img) bằng thuộc tính color cũng đồng thời thiết lập màu cho đường biên.

### 2.2.8       Bài tập và thực hành

Bài tập 2.2a. Viết lại các đoạn mã trong phần lý thuyết.

Bài tập 2.2b. Thiết lập kích thước phông.

Chúng ta cùng tinh chỉnh kích thước của một số phần tử văn bản để thực đơn của nhà hàng nhìn có vẻ đặc biệt hơn. Mở tập tin menu.html (làm tiếp trên tập tin của bài tập 2.1 về phông chữ) trong trình viết mã và thực hiện các bước sau. Bạn có thể lưu lại tập tin mỗi khi thực hiện thay đổi, và mở lại trên trình duyệt để xem kết quả. Bạn cũng có thể thiết lập phông chữ với kích thước bất kỳ theo ý bạn. 

[Bước 1] Có nhiều cách để thiết lập kích thước phông chữ cho một trang web. Trong ví dụ này, chúng ta sẽ bắt đầu bằng cách dựa trên kích thước phông chuẩn của tài liệu (kích thước phông chữ của phần tử HTML), và thiết lập kích thước phông cho phần tử body là 100% (nghĩa là bằng với kích thước của phông của HTML), bởi vậy, đây chính là cơ sở cho cách tính dựa trên đơn vị đo **em** sau này.
```csss
body {

font-family: Verdana, sans-serif;

font-size: 100%;

}
```

[Bước 2]. Trên trình duyệt, phông chữ mặc định cho phần văn bản sẽ có kích thước 16 pixel, nhưng chúng ta muốn hiển thị tiêu đề nổi bật hơn. Chúng ta sẽ thiết lập cho tiêu đề có kích thước 24 pixel, nghĩa là nó sẽ lớn hơn 1.5 lần so với kích thước phông chuẩn (24 = 16 x 1.5).

Chúng ta sẽ thêm chỉ dẫn mới để thiết lập cho kích thước của h1 là 1.5em. Bạn cũng có thể sử dụng kích thước phông là 150% để có được kết quả tương tự.
```css
h1 {

font-size: 1.5em;

}
```
[Bước 3]. Chúng ta tiếp tục thiết lập cho các tiêu đề mức 2 (h2) có kích thước bằng với kích thước văn bản thông thường, để nhìn chúng tương hợp hơn với phần còn lại của trang:
```css
h2 {

font-size: 1em;

}
```

Bài tập 2.2c. Setting font size.

Let’s refine the size of some of the text elements to give the online menu a more sophisticated appearance. Open menu.html (get this file from Bài tập2 in Phông chữ topic) in a text editor and follow the steps. You can save the document at any point and take a peek in the browser to see the results of your work. You should also feel free to try out other size values along the way.

1. There are many approaches to sizing text on web pages. In this example, start by putting a stake in the ground and setting the font-size of the body element to 100%, thus clearing the way for em measurements thereafter:
```css
body {

font-family: Verdana, sans-serif;

font-size: 100%;

}
```

2. The browser default of 16 pixels is a fine size for the main page text, but I would like to improve the appearance of the heading levels. I’d like the main heading to be 24 pixels, or one and a half times larger than the body text [target (24) ÷ context (16) = 1.5]. I’ll add a new rule that sets the size of the h1 to 1.5em. I could have used 150% to achieve the same thing.
```css
h1 {

font-size: 1.5em;

}
```

3. Now make the h2s the same size as the body text so they blend in with the page better:
```css
h2 {

font-size: 1em;

}
```

Bài tập 2.2d. Mở một trang web trên Internet (ví dụ một trang trong themeforest, báo Thanh niên, hoặc thegioididong, …), sử dụng Developer tools để ghi lại các phông chữ, cỡ chữ, độ đậm, kiểu dáng đã sử dụng. Điền kết quả vào bảng sau:

|**Nội dung**|**Phông chữ**|**Cỡ chữ**|**Độ đậm**|**Kiểu dáng**|
|------------|-------------|----------|----------|-------------|
|Menu chính| | | | |
|Đoạn văn bản| | | | |
|Nội dung vùng chân trang (page footer)| | | | |
|Tiêu đề mức 1 (h1)| | | | |

### 2.2.9       Câu hỏi ôn tập

Câu 1.  is defined relative to the font size of the root element. The root element is matched by the :root pseudo-class or the html selector. 1 therefore takes on the value which is given to the font-size of the root element.

A. em

**B. rem**

C. %

D. vw

Câu 2. Chỉ dẫn CSS nào sau đây bị lỗi:

A. h1 { font-size: 100%; }

B. h1 { font-size: 20px;   }

C. h1 { font-size: 1.5rem;   }

**D. h1 { font-size: 1.5 em; }**

Câu 3. Trong CSS, muốn định dạng chữ nghiêng, sử dụng thuộc tính nào?

A. font-weight

**B. font-style**

C. font-variant

D. font-size

Câu 4. Cho đoạn mã sau:   

```css

<style>

        html { font-size: 100%; }

        article { font-size: 0.875em }

        h1 { font-size: 1.5em; }

    </style>

</head>

<body>

    <article>

        <h1>Tiêu đề h1</h1>

    </article>

```

Cỡ chữ của h1 là bao nhiêu px?

A. 16

**B. 21**

C. 14

D. 24

