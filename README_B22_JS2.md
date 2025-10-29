# CÚ PHÁP, KIỂU DỮ LIỆU VÀ BIẾN

----------

## 2. Cú pháp, kiểu dữ liệu và biến

Sau khi học bài học trước, chúng ta đã biết cách viết và chạy một chương trình JavaScript đơn giản. Trong phần này, chúng ta sẽ tìm hiểu về cú pháp, kiểu dữ liệu và biến trong ngôn ngữ JavaScript. Bạn nên vừa đọc lý thuyết vừa lập trình và quan sát kết quả, nó sẽ giúp bạn nhớ được cú pháp, hiểu được nội dung lý thuyết và có kĩ năng làm việc tốt hơn.

### 2.1 Cú pháp

**Câu lệnh**

Chương trình JavaScript được tạo thành từ các câu lệnh (statement). Câu lệnh là một chỉ dẫn cho máy tính thực hiện một công việc cụ thể. Kết thúc câu lệnh là một dấu chấm phẩy (;), hoặc xuống hàng (line break, new line).

Ví dụ sau đây là 2 câu lệnh, mỗi câu lệnh nằm trên 1 hàng, kết thúc câu lệnh bằng cách xuống hàng:

```js
const message = 'Chao bac Teo!'

alert(message)
```

Ở ví dụ sau, chúng ta dùng dấu chấm phẩy để kết thúc một lệnh, bạn nên sử dụng cách này:

```js
const message = 'Chao bac Teo!';

alert(message);
```

Nếu sử dụng dấu chấm phẩy, bạn có thể viết nhiều lệnh trên một hàng, tuy nhiên không khuyến khích sử dụng cách này, vì làm cho mã nguồn khó đọc:

```js
const message = 'Chao bac Teo!';alert(message);
```

Khối lệnh là tập hợp của nhiều lệnh, được bao lại bằng cặp ngoặc nhọn {}, kết thúc khối lệnh không cần dấu chấm phẩy.  Ví dụ:
```js
{

const message = 'Chao bac Teo!';

alert(message);

}
```

Khoảng trắng

Khoảng trắng gồm ký tự trắng (space), tab, dấu xuống hàng (new line). Các khoảng trắng dư thừa sẽ bị bỏ qua khi dịch mã. Vì vậy, chúng ta nên sử dụng các khoảng trắng cho phù hợp, để mã nguồn có bố cục rõ dàng, dễ đọc.

Ví dụ, thay vì viết mã như thế này:

```js
const message='Chao bac Teo!';alert(message);
```

Thì chúng ta có thể sử dụng các khoảng trắng và dấu xuống hàng để mã nguồn dễ đọc hơn:

```js
const message = 'Chao bac Teo!';

alert(message);
```

Phân biệt chữ hoa và chữ thường

JavaScript là ngôn ngữ có phân biệt chữ hoa và chữ thường (case-sensitive). Ví dụ, nếu đặt một biến có tên là “myVariable”, một biến khác có tên là “myvariable”, và một biến có tên là “MyVariable” thì sẽ tạo ra ba biến khác nhau.

```js
const myVariable = 'a';

const myvariable = 'b';

const MyVariable = 'c';
```

Từ dành riêng

Từ dành riêng (reserved words) là các từ khóa được ngôn ngữ JavaScript độc quyền sử dụng. Do vậy chúng ta không thể, hoặc không nên sử dụng các từ khóa này để đặt tên biến, tên hàm, hay thuộc tính. Ví dụ một số từ dành riêng của JavaScript:

abstract, await, boolean, break, byte, case, catch, char, class, const, continue, debugger, default, delete, do, double, else, enum, export, extends, false, final, finally, float, for, function, goto, if, implements, import, in, instanceof, int, interface, let, long, native, new, null, package, private, protected, public, return, short, static, super, switch, synchronized, this, throw, throws, transient, true, try, typeof, var, volatile, void, while, with, yield, undefined, NaN, Infinity

Ví dụ, chúng ta đặt tên biến là case thì chương trình sẽ báo lỗi:  
  const case = 'dung tu khoa dat ten bien';

Chú thích

Chú thích (comment) là những lời giải thích, hoặc những mô tả đi kèm với các đoạn mã. Mục đích giúp người lập trình sau này có thể dễ dàng hiểu được chức năng hoặc cách làm việc của một đoạn mã. Ngoài ra, trong quá trình tìm và sửa lỗi (debug) cũng thường hay sử dụng chức năng chú thích để che các đoạn mã không muốn thực thi.

Phần chú thích sẽ được bỏ qua khi trình duyệt thực thi đoạn mã JavaScript. Có hai cách để tạo chú thích: tạo chú thích từng hàng và tạo chú thích nhiều hàng.

Để tạo chú thích từng hàng, đặt hai dấu xuyệt (//) ở đầu nội dung chú thích, JavaScript sẽ hiểu phần nội dung nằm sau dấu xuyệt cho đến hết hàng là chú thích (không cần có dấu kết thúc). Ví dụ:

```js
// day la cau chao

         alert("Chao bac Teo");
```

Hoặc,

```js
alert("Chao bac Teo"); // day la cau chao
```

Để tạo chú thích trên nhiều hàng, sử dụng kí hiệu /\* \*/ để bao lại phần nội dung chú thích, ví dụ:

```js
/\* đây là câu chào

nó sẽ xuất hiện trong một cửa sổ

trên trình duyệt \*/

alert("Chao bac Teo");
```

Khi lập trình, chúng ta nên đặt tên biến, tên hàm và viết mã nguồn có ngữ nghĩa rõ ràng, dễ hiểu. Khi đó, bản thân mã nguồn đã cho biết nó thực hiện việc gì và thực hiện như thế nào mà không nhất thiết phải có đoạn chú thích. Bạn có thể đọc thêm các bài viết liên quan đến sử dụng chú thích trong các chủ đề về “clean code”. Tóm lại là không nên viết quá nhiều chú thích trong mã nguồn.

### 2.2 Kiểu dữ liệu

Dữ liệu được định nghĩa là:

– Một chuỗi gồm một hoặc nhiều ký hiệu (sequence of one or more symbols), ví dụ: 123, ‘nguyen van teo’.

– Ở mức thấp nhất, ví dụ khi dữ liệu được lưu trên RAM, nó sẽ được biểu diễn dưới dạng hệ số nhị phân (0 và 1)

– Cần được thông dịch (diễn dịch) để trở thành thông tin

– Biểu diễn số lượng, tính chất hoặc chỉ dẫn hoạt động

– Được tổ chức trong nhiều loại cấu trúc dữ liệu khác nhau

Trong lập trình, dữ liệu được chia thành nhiều kiểu (loại). Mỗi kiểu cho biết miền giá trị, các phép toán có thể thực hiện trên nó, ý nghĩa của dữ liệu và cách thức lưu trữ.

Kiểu dữ liệu giúp cho Chương Trình Dịch đoán được ý định xử lý dữ liệu của lập trình viên.

JavaScript có 7 kiểu dữ liệu khác nhau, trong đó có 6 kiểu dữ liệu cơ bản (primitive data type) và kiểu dữ liệu object.

Các kiểu dữ liệu cơ bản gồm:

– String

– Symbol

– Number

– Boolean

– Undefined

– Null

Các dữ liệu không thuộc 6 kiểu cơ bản trên sẽ là kiểu object, ví dụ mảng, hàm và object literal (đối tượng nguyên bản).

Toán tử typeof

Trong JavaScript, chúng có thể sử dụng toán tử (operator) typeof để kiểm tra xem một dữ liệu thuộc kiểu gì?

Ví dụ:

```js
typeof 'hi bac Teo';

<'string'

typeof 123

<'number'

typeof true

<'boolean'

typeof true;

<'boolean'

typeof {ten : 'van teo'};

<'object'

typeof \[1, 2, 3\];

<'object'
```

### 2.3 Biến

Khi lập trình, chúng ta cần sử dụng các biến (variable) để chứa dữ liệu. Hiểu đơn giản, biến chính là các ô nhớ (hay thùng chứa) trong bộ nhớ, dùng để chứa dữ liệu bên trong. Mỗi biến được đại diện bằng một cái tên. Ví dụ, hình dưới đây minh họa một biến có tên là num, và có giá trị là 5:

  

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvqYXBzYgkt0ufEsQB_aiDXrJc2b2hfyosRwfzg3p7R8mvetRz51E_Jp5pujWMstNEC8UAre-XblU-i7KCjkHipU-8s7UoxprmN1czlKAflVGAr_vN_NVHi3GtbNR4RK5Z2sUZ0LmlvIXs_ssHVTnipy_iW6d7pjxXTgI66GaCwfS5Md5RCfK08jPY1AE/s1600/variable.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvqYXBzYgkt0ufEsQB_aiDXrJc2b2hfyosRwfzg3p7R8mvetRz51E_Jp5pujWMstNEC8UAre-XblU-i7KCjkHipU-8s7UoxprmN1czlKAflVGAr_vN_NVHi3GtbNR4RK5Z2sUZ0LmlvIXs_ssHVTnipy_iW6d7pjxXTgI66GaCwfS5Md5RCfK08jPY1AE/s254/variable.png)

  

Ví dụ sau sẽ tạo ra một biến có tên là tuoi và gán cho nó giá trị là 20:

var tuoi = 20;

Để khai báo biến, chúng ta sử dụng từ khóa var (viết tắt của variable), theo sau là tên biến, dấu “=” dùng để gán giá trị, 20 là giá trị gán cho biến, và kết thúc câu lệnh là dấu chấm phẩy (;).

JavaScript là ngôn ngữ “định kiểu yếu”, hay “định kiểu động”. Do vậy, khi khai báo biến sẽ không cần xác định kiểu của biến. Giá trị trong biến sẽ cho biết kiểu dữ liệu của biến là gì. Một biến có thể chứa mọi loại dữ liệu, như số, chuỗi kí tự, phần tử DOM, hàm. 

Ở ví dụ sau, khi gán tuoi = 20 thì kiểu dữ liệu của nó là number, tuy nhiên, vẫn biến đó, nhưng khi gán tuoi = ' hai muoi' thì kiểu dữ liệu lại là string.

```js
var tuoi = 20;

typeof(tuoi);

<'number'

tuoi = 'hai muoi';

typeof(tuoi);

<'string'
```

Tên biến là một chuỗi bất kì, miễn là không trùng với các từ khóa độc quyền của JavaScript. Tuy nhiên, cần đặt tên biến sao cho có ý nghĩa, dễ dàng đoán ra mục đích của nó. Như ở ví dụ trên, chúng ta có thể dùng tên biến là “so” (số) thay cho “tuoi” (tuổi), tuy nhiên, dùng là “tuoi” sẽ cụ thể và dễ hiểu hơn.

Về mặt cú pháp, tên biến cần tuân theo các quy tắc sau:

– Tên biến phải bắt đầu bằng một chữ cái hoặc ký tự gạch dưới (\_)

– Tên biến chỉ bao gồm các ký tự, ký số và ký tự gạch dưới

– Tên biến không chứa khoảng trắng

– Tên biến có phân biệt chữ hoa, chữ thường

Với tên biến gồm nhiều từ, để dễ dàng nhận diện được các từ, có thể sử dụng nhiều cách, ví dụ chúng ta có thể sử dụng một trong hai cách sau:

– Sử dụng dấu gạch dưới (\_) (underscore) để ngăn cách giữa các từ, ví dụ: variable\_name

– Sử dụng kiểu u lạc đà (camelCase), ví dụ: variableName. Lập trình viên JavaScript hay sử dụng cách này.

Trước phiên bản ES6, chúng ta dùng từ khóa var để khai báo biến. Từ ES6 trở đi, chúng ta có thể sử dụng thêm hai từ khóa để khai báo biến là const và let. Một biến được khai báo bằng từ khóa const sẽ được gán giá trị cố định khi khai báo, và sau đó thì không cho thay đổi giá trị. Có thể hiểu, biến được khai báo bằng từ khóa const chính là một hằng (constant). Lưu ý, tính chất này chỉ đúng khi giá trị gán cho biến thuộc 6 kiểu dữ liệu căn bản.

Một biến được khai báo bằng từ khóa let hoạt động như khi khai báo bằng từ khóa var, tuy có một chút khác biệt.

Ví dụ dùng từ khóa const:

```js
const namSinh = 2000;

namSinh = 2001;

Uncaught TypeError: Assignment to constant variable.

    at <anonymous\>:2:9
```

Ví dụ dùng từ khóa let:

```js
let diem = 7;

diem = 8;

console.log(diem);

< 8
```

Dùng từ khóa var để khai báo biến có thể xảy ra một số vấn đề liên quan đến phạm vi của biến (sẽ tìm hiểu ở các phần sau), vì vậy, chúng ta nên sử dụng từ khóa let và const để khai báo biến và hằng.

Chúng ta có thể khai báo và gán giá trị cho nhiều biến trên cùng một hàng, mỗi khai báo ngăn cách nhau bằng dấu phẩy (,).

```js
let x = 1, y = 2, z = 3;

console.log(x, y, z);

< 1 2 3
```

Như ở phần trên đã đề cập, khi chúng ta dùng từ khóa const để khai báo biến, nếu không phải là kiểu dữ liệu căn bản (6 kiểu), thì vẫn có thể thay đổi dữ liệu của một biến. Ví dụ :

```js
const arr = \[1, 2, 3\];

arr\[0\] = 4; // thay đổi giá trị của mảng

console.log(arr);

< (3) \[4, 2, 3\]
```

Nhưng một biến được khai báo bằng từ khóa const sẽ không cho gán một đối tượng khác vào biến ban đầu. Ví dụ:

```js
const arr1 = \[4, 5, 6\];

arr1 = \[7, 8, 9\];

Uncaught TypeError: Assignment to constant variable.

    at <anonymous\>:2:6
```

Mặc dù khai báo biến bằng const vẫn còn những hạn chế, tuy nhiên, chúng ta vẫn nên xem xét để sử dụng nó nhiều nhất có thể. Vì nó giúp chúng ta tránh được một số tình huống không mong đợi do việc thay đổi giá trị của biến trong chương trình.

Khác so với var, việc khai báo biến bằng let và const sẽ không cho phép ghi đè lên các phương thức tạo sẵn (built-in method), đồng thời phạm vi của biến sẽ được xem xét ở mức độ block (block scope).

### 2.4 Xem và đọc thêm

– \[1\] Dùng các từ khóa sau tìm kiếm trên mạng để đọc thêm: kiểu dữ liệu wiki, data type wiki

– \[2\] Darren Jones, JavaScript Novice To Ninja, second edition, SitePoint, 2017,  trang 31 tới 59

### 2.5 Bài tập và thực hành

**Bài tập 2a.** Viết lại các đoạn mã trong phần lý thuyết.

**Bài tập 2b.** Sử dụng toán tử typeof, điền kết quả vào bảng sau, giải thích kết quả:

|Dữ liệu|Kiểu dữ liệu|
|-------|------------|
|null| |
|undefined| |
|0| |
|True (lưu ý: chữ t viết hoa)| |
|true (lưu ý : chữ t viết thường)| |
|\'True\'| |
|1e5| |

*Gợi ý:*

**Bài tập 2.**

|Dữ liệu|Kiểu dữ liệu|
|-------|------------|
|null|Object|
|undefined|Undefined|
|0|Numbe|
|True (lưu ý: chữ t viết hoa)|Undefined|
|true (lưu ý : chữ t viết thường)|Boolean|
|\'True\'|String|
|1e5|Number|

### 2.6 Câu hỏi ôn tập

**Câu 1.** Trong JavaScript, đoạn mã này: const case = 'dung tu khoa dat ten bien'; bị lỗi gì?

A. Dấu gán phải là ‘:=’

B. Thừa dấu chấm phẩy ( ;) ở cuối câu lệnh

C. Phải bao một chuỗi bằng dấu nháy kép ("")

**D. Dùng từ khóa để đặt tên biến**

**Câu 2.** Trong JavaScript, dòng mã sau sẽ xuất gì ra màn hình?

typeof(3.1415);

A. PI

**B. Number**

C. Double

D. Integer

**Câu 3.** Khi lập trình, có nhiều cách để viết tên các biến, ví dụ một biến có tên là  fullName thì nó được viết theo phong cách gì?

A. PascalCase

B. snake\_case

**C. camelCase**

D. kebab-case

**Câu 4.** Trong JavaScript, tên biến nào sau đây bị lỗi?

**A. var full-name = 'nguyen van teo';**

B. var full\_name = 'nguyen van teo';

C. var full4Name = 'nguyen van teo';

D. var $fullName = 'nguyen van teo';
