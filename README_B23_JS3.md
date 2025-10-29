# PHẠM VI, KIỂU STRING, XUẤT CHUỖI

---------------

## 3. Phạm vi, kiểu string, xuất chuỗi

### 3.1 Phạm vi

Ở phần trước, bạn đã biết cách khai báo một biến bằng từ khóa const, hoặc let. Bạn cũng biết là chương trình JavaScript được tạo thành từ các lệnh và các khối lệnh (block code). Vậy nếu một biến được khai báo ở trong khối lệnh thì khi ra ngoài khối lệnh nó có tồn tại không? Hoặc một biến khai báo ở bên ngoài thì trong khối lệnh bạn có dùng được nó không? Hoặc bên ngoài khối lệnh đã khai báo biến, bên trong khối lệnh cũng khai báo một biến trùng tên, thì chuyện gì xảy ra? Phần này sẽ tìm hiểu để trả lời một số câu hỏi như vậy.

Trong lập trình, phạm vi (scope) là một khái niệm dùng để xác định một vùng của chương trình máy tính, mà trong đó, biến có tồn tại và có thể tham chiếu tới nó để thực hiện các thao tác.

Trong JavaScript, phạm vi của biến được xác định dựa trên mã nguồn (lexical scope).

Từ JavaScript phiên bản ES6 trở đi, một vùng mã, hay khối lệnh (code block) được xác định bằng các cặp dấu ngoặc nhọn ({}).

JavaScript có hai loại phạm vi là: toàn cục (global scope) và cục bộ (local scope).

Phạm vi toàn cục

Biến được khai báo bên ngoài khối lệnh sẽ có phạm vi toàn cục. Ngoài ra, nếu khai báo biến ở bất cứ đâu, nếu không dùng từ khóa const và let thì nó cũng sẽ có phạm vi toàn cục.

Với biến toàn cục, bạn có thể sử dụng, truy cập tới biến này ở mọi nơi trong chương trình.

Mới nghe qua, sẽ thấy ý tưởng biến toàn cục này có vẻ hay. Tuy nhiên, trong thực tế nó không không phải như vậy. Các lập trình viên kinh nghiệm thường hạn chế sử dụng các biến toàn cục, lý do là nó dễ gây ra tình trạng khó kiểm soát tên biến, và có nguy cơ bị ghi đè giá trị.

Phạm vi cục bộ

Các biến được khai báo ở trong khối lệnh, bằng từ khóa const và let sẽ có phạm vi cục bộ trong chính khối lệnh đó. Nghĩa là, biến sẽ được sử dụng ở bên trong khối lệnh, và không thể truy cập nó ở bên ngoài khối lệnh.

Một số ví dụ minh họa về phạm vi của biến

– Khi bạn khai báo một biến toàn cục, thì bạn có thể sử dụng nó ở mọi nơi

```js
    const a \= 5;

    {

        console.log(a);// 5

    }

    console.log(a); // 5
```

– Nếu bạn khai báo một biến là cục bộ thì bạn không thể sử dụng nó ở bên ngoài khối lệnh

```js
    {

        const a \= 5;

        console.log(a);// 5

    }

    console.log(a); // error
```

– Nếu bạn đã định nghĩa một biến toàn cục và một biến cục bộ trùng tên, thì sẽ tồn tại 2 biến khác nhau (mặc dù trùng tên)

```js
    const a \= 6;

    {

        const a \= 5;

        console.log(a); // 5

    }

    console.log(a); // 6
```

– Khi khai báo một biến mà không dùng từ khóa const hoặc let, biến đó sẽ là toàn cục, cho dù bạn khai báo ở trong hay ngoài khối lệnh

```js
    c \= 7;

    {

        console.log(c); // 7

        d \= 8;

    }

    console.log(d); // 8
```

### 3.2 Kiểu dữ liệu string

Ở phần trước, bạn đã biết trong JavaScript có các kiểu dữ liệu căn bản (string, symbol, number, boolean, undefined, null) và kiểu object. Phần này sẽ tìm hiểu chi tiết về kiểu dữ liệu string.

String (chuỗi) là một dãy các kí tự. Người ta sử dụng kiểu dữ liệu string để lưu trữ các dữ liệu dạng văn bản. Xem hình ví dụ (nguồn wikipedia).

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpWX1ac0H213Sn6mqkDXr7i9QHmc4gI-PNVe2B2I8CAuo8mmCLxcGTt11e3xldkhGU1QXb_MQjKHuB6Np1K5KcwNesiWF_Qcqoq8iXUWa1KxW0oVIYqS9IRa_abyXUgp1bUVtSulDaNcAauCvELoeVaYeWsoXYdpWhvpCH7WuA8FoNWqovnqyIvda2MM8/s320/string.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpWX1ac0H213Sn6mqkDXr7i9QHmc4gI-PNVe2B2I8CAuo8mmCLxcGTt11e3xldkhGU1QXb_MQjKHuB6Np1K5KcwNesiWF_Qcqoq8iXUWa1KxW0oVIYqS9IRa_abyXUgp1bUVtSulDaNcAauCvELoeVaYeWsoXYdpWhvpCH7WuA8FoNWqovnqyIvda2MM8/s727/string.png)

Để tạo ra dữ liệu kiểu string, bạn chỉ cần bao một chuỗi bằng dấu nháy đơn (') hoặc dấu nháy kép ("). Trong JavaScript, người ta gọi chuỗi này là string literal (chuỗi thuần). Ví dụ:

```js
    const str1 \= "Chao bac Teo";

    console.log(str1);

    const str2 \= 'Chao cu Ti';

    console.log(str2);
```

Nếu trong chuỗi có chứa dấu nháy đơn, hoặc nháy kép thì khi tạo chuỗi bạn cần đảo dấu nháy ở bên ngoài, ví dụ:

```js
    const str1 \= "Chao bac's Teo";

    console.log(str1);

    const str2 \= 'Chao "cu" Ti';

    console.log(str2);

    const str3 \= 'chao bac's Teo'; // lỗi
```

Bạn cũng có thể sử dụng dấu xuyệt ngược (backslash) để xuất các dấu nháy đơn và nháy kép ở trong một chuỗi. Ví dụ:

```js
    const str1 \= 'Chao bac\\'s Teo';
```

Bạn cũng có thể tạo ra một chuỗi bằng cách tạo ra một đối tượng kiểu String, tuy nhiên cách này ít dùng vì phải gõ phím nhiều. Ví dụ:

```js
    const str4 \= new String('Chao bac Teo');

    // String {'Chao bac Teo'}
```

Khi bạn tạo ra một biến kiểu string, JavaScript sẽ dùng lớp String để bọc lại biến, vì vậy bạn có thể xử lý biến như một đối tượng. Nghĩa là bạn có thể gọi các thuộc tính và phương thức đi kèm với đối tượng String. Sử dụng dấu chấm (.) để truy cập tới các thuộc tính và phương thức.

Chúng ta sẽ cùng tìm hiểu một số thuộc tính và phương thức.

Để biết chiều dài của chuỗi (chuỗi đang chứa bao nhiêu kí tự), sử dụng thuộc tính length.

```js
    const str \= 'hello';

    console.log(str.length);// 5
```

Cũng có thể sử dụng dấu ngoặc vuông (\[\]) để truy cập tới thuộc tính.

```js
    console.log(str\['length'\]);
```

Với kiểu dữ liệu căn bản, JavaScript không cho phép bạn thay đổi giá trị trong các thuộc tính. Ví dụ, giá trị thuộc tính length của chuỗi str đang là 5, bạn sẽ không thể thay đổi được giá trị này.

```js
    const str \= 'hello';

    console.log(str\['length'\]);// 5

    str.length \= 7; // thay đổi giá trị của thuộc tính

    console.log(str.length) // 5
```

Để chuyển chuỗi sang dạng chữ hoa, sử dụng phương thức toUpperCase(). Để ý sẽ thấy, khi gọi “phương thức” sẽ khác với khi “tham chiếu tới thuộc tính”; phương thức luôn có dấu ngoặc đơn ().

```js
    console.log(str.toUpperCase()); // HELLO
```

Chuyển chuỗi sang dạng chữ thường, dùng phương thức toLowerCase().

```js
    const str \= 'Hello';

    console.log(str.toLowerCase()); // hello
```

Dùng phương thức charAt() để xem ký tự tại một vị trí trong chuỗi là gì? Lưu ý: vị trí trong chuỗi được đánh số từ 0.

```js
    console.log(str.charAt(1));// e
```

Nếu muốn biết một ký tự hoặc một chuỗi con có trong chuỗi không, sử dụng phương thức indexOf(). Nếu có: trả về vị trí bắt đầu, nếu không: trả về giá trị -1.

```js
    console.log(str.indexOf('o')); // 4

    console.log(str.indexOf('z')); // -1
```

Nếu muốn trả về vị trí của kí tự hoặc chuỗi con xuất hiện sau cùng (nếu có), sử dụng phương thức lastIndexOf().

```js
    const str \= 'Hello every one';

    console.log(str.lastIndexOf('e')); // 14
```

Để kiểm tra một chuỗi có chứa một ký tự bất kì, sử dụng phương thức includes().

```js
    const str \= 'hello';

    console.log(str.includes('e')); // true

    console.log(str.includes('z')); // false
```

Để kiểm tra một chuỗi có bắt đầu bằng một ký tự cụ thể nào đó, sử dụng phương thức startsWith(). Phương thức này có phân biệt chữ hoa, chữ thường (case-sensitive).

```js
    const str \= 'hello';

    console.log(str.startsWith('h')); // true

    console.log(str.startsWith('H')); // false
```

Để kiểm tra một chuỗi có kết thúc bằng một ký tự cụ thể nào đó, sử dụng phương thức endsWith(). Phương thức này có phân biệt chữ hoa, chữ thường (case-sensitive).

```js
    const str \= 'hello';

    console.log(str.endsWith('o')); // true

    console.log(str.endsWith('H')); // false
```

Để nối hai chuỗi, sử dụng phương thức concat() (viết tắt của concatenate). Hoặc đơn giản hơn là dùng toán tử cộng (+).

```js
    const str \= 'hello';

    console.log(str.concat(' bac Teo')); // hello bac Teo

    // đơn giản hơn

    console.log(str + ' bac Teo');
```

Nếu bạn muốn xóa các khoảng trắng ở đầu và cuối chuỗi, sử dụng phương thức trim().

```js
    const str \= '   nguyen van teo   ';

    console.log(str); // '   nguyen van teo   '

    console.log(str.trim()); // 'nguyen van teo'
```

Nếu bạn muốn lặp lại một chuỗi nhiều lần, sử dụng phương thức repeat().

```js
    const str \= 'hi';

    console.log(str.repeat(3)); // hihihi
```

Để trích một chuỗi con từ chuỗi gốc, sử dụng phương thức slice(viTriBatDau, viTriKetThuc). Phương thức slice sẽ lấy ký tự từ chỉ mục viTriBatDau tới kí tự tại (viTriKetThuc – 1).

```js
    const str \= 'Nguyen Thi Van Teo';

    console.log(str.slice(0, 6)); // Nguyen
```

Để tách một chuỗi thành nhiều chuỗi con, sử dụng phương thức split(kiTuTach).

```js
    const str \= 'teonv@gmail.com';

    const result \= str.split('@');

    console.log(result\[0\]); // teovn

    console.log(result\[1\]); // gmail.com
```

### 3.3 Mẫu xuất chuỗi

Trong tiếng Anh, ba từ này là tương đương: template strings, template literals và string templates tạm gọi là mẫu dùng để xuất chuỗi.

Thông thường, bạn hay sử dụng dấu cộng (+) để nối chuỗi với giá trị của biến, ví dụ:

```js
    const ho \= 'Nguyen', ten \= 'Teo';

    console.log('Ho ten la: ' + ho + ' ' + ten);
```

Ngoài cách trên, bạn có thể sử dụng mẫu (template) để xuất chuỗi cùng với giá trị của biến, sử dụng cú pháp ${}.

Ví dụ:

```js
    const ho \= 'Nguyen', ten \= 'Teo';

    console.log(\`Ho ten la: ${ ho } ${ ten }\`);
```

Để ý ở đoạn mã trên, đừng nhầm dấu nháy đơn (‘’) với dấu (\`\`).

Khi hiển thị template, các khoảng trắng và dấu xuống dòng vẫn được duy trì so với mã nguồn, vì vậy rất tiện cho việc thiết kế các mẫu dữ liệu xuất ra màn hình, như một email hoặc một đoạn mã nguồn.

Ví dụ:

```js
          const ten \= 'Teo';

          const qty \= 4;

          const email \= \`

          Xin chao ban ${ ten },

          Chung toi ra vui khi nhan duoc ${ qty } don hang tu ban.

          Cam on ban.\`;

          console.log(email);
```

Hoặc bạn có thể sử dụng template để xuất trực tiếp trên trang HTML như ví dụ sau:

```js
          const article \= {

               title: 'Xuat template',

               body: 'Su dung template de xuat truc tiep len trang web'

          };

          document.body.innerHTML \= \`

          <section>

               <header>

                    <h1>Hoc React</h1>

               </header>

               <article>

                    <h2>${article.title}</h2>

                    ${article.body}

               </article>

               <footer>

                    <p>copyright ${new Date().getFullYear()} | Hoc React</p>

               </footer>

          </section>

          \`;
```

### 3.4 Xem và đọc thêm

– Darren Jones, JavaScript Novice To Ninja, second edition, SitePoint, 2017,  p31 > p59

– Alex Banks, Eve Porcello, Learning React – Modern Patterns for Developing React Apps, O’Reilly Media, 2020, p7 – p11

### 3.5 Bài tập và thực hành

**Bài tập 3a.** Viết và chạy các đoạn mã trong phần lý thuyết.

**Bài tập 3b.** Cho một chuỗi là họ tên của người dùng, hãy viết đoạn mã để tách thành họ, tên lót và tên.

Ví dụ:

– Họ tên: Nguyen Van Teo

– Kết quả: ho = 'Nguyen'; tenLot = 'Van' ; ten = 'Teo'.

**Bài tập 3c.** Write a JavaScript function to hide email addresses to protect from unauthorized users.

Input: "robin\_singh@example.com"

Output: "robin...@example.com"

*\[Gợi ý\]*

**Bài tập 3b.**

```js
    const str \= '     Nguyen Thi Van Teo     ';

    // bỏ khoảng trắng dư ở đầu và đuôi

    const temp \= str.trim();

    // tìm khoảng trắng đầu tiên

    const firstSpace \= temp.indexOf(' ');

    // tim khoảng trắng sau cùng

    const lastSpace \= temp.lastIndexOf(' ');

    const ho \= temp.slice(0, firstSpace);

    const tenLot \= temp.slice(firstSpace + 1, lastSpace);

    const ten \= temp.slice(lastSpace + 1, temp.length + 1);

    console.log(ho, tenLot, ten);
```

Bạn có thể viết thêm các đoạn mã kiểm tra cho trường hợp:

– Họ tên không hợp lệ, ví dụ: chuỗi rỗng, chỉ có một chữ

– Có nhiều khoảng trắng giữa các chữ, ví dụ: '      Nguyen      Van     Teo  '

**Bài tập 3c.**

```js
    const email \= 'teonv@gmail.com';

    let avg \= 0, splitted \= '', part1 \= '', part2 \= '';

    splitted \= email.split("@");

    part1 \= splitted\[0\];

    avg \= part1.length / 2;

    part1 \= part1.slice(0, (part1.length \- avg));

    part2 \= splitted\[1\];

    console.log(part1 + "...@" + part2);
```

### 3.6 Câu hỏi ôn tập

**Câu 1.** Đoạn mã này xuất gì ra màn hình:  const a = 6; { const a = 5; console.log(a); }

A. 6

**B. 5**

C. Error

D. null

**Câu 2.** Đoạn mã này xuất gì ra màn hình:  const a = 6; { const a = 5; } console.log(a);

A. Error

B. undefined

C. 5

**D. 6**

**Câu 3.** Đoạn mã này xuất gì ra màn hình? const str = 'Nguyen Van Teo'; console.log(str.slice(3, 6));  

A. Nguyen

B. Van

C. Teo

**D. yen**

**Câu 4.** Đoạn mã này xuất gì ra màn hình? const str = 'teonv@gmail.com'; const result = str.split('@'); console.log(result\[0\]);

A. t

**B. teonv**

C. null

D. @
