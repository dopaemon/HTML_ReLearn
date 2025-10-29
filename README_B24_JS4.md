# KIỂU DỮ LIỆU NUMBER

-----------

## 4. Kiểu dữ liệu number

### 4.1 Kiểu number

**Số nguyên và số thập phân**

Number (số) là một trong bảy kiểu dữ liệu nguyên thủy (primitive) của JavaScript, dùng để biểu diễn các giá trị số, bao gồm cả số nguyên và số thập phân.

Kiểu number trong JavaScript không phân biệt giữa số nguyên (integers) và số thập phân (floating-point numbers). Cả hai đều được xếp vào cùng một kiểu number và được lưu trữ theo cùng một định dạng.

Vậy là trong JavaScript, bạn không cần phải khai báo kiểu dữ liệu riêng biệt là int hay float như trong các ngôn ngữ khác.

|**Ví dụ**|**Mô tả**|
|---------|---------|
|```js const integer = 123;```|Số nguyên|
|```js const float = 3.14; ```|Số thập phân|
|```js typeof integer; ```|\'number\'|
|```js typeof float; ```|\'number\'|

**Các hệ cơ số khác**

Bạn có thể viết số ở các hệ cơ số khác ngoài hệ thập phân (cơ số 10) bằng cách sử dụng các tiền tố:

|Hệ cơ số|Tiền tố|Ví dụ|Giá trị thập phân|
|--------|-------|-----|-----------------|
|Nhị phân|0b|0b1011|11|
|Bát phân|0o|0o75|61|
|Thập lục phân|0x|0xFF|255|

*Ví dụ:*

```js
NhiPhan = 0b1011;

console.log(NhiPhan); //11

  

BatPhan = 0o75;

console.log(BatPhan); //61

  

ThapLucPhan = 0xFF;

console.log(ThapLucPhan); //255
```

**Phương thức kiểm tra số nguyên**

Vì số nguyên và số thập phân cùng có kiểu là number, nên ES6 cung cấp phương thức Number.isInteger() để kiểm tra chính xác xem một giá trị có phải là số nguyên hay không.

```js
Number.isInteger(5); // true

Number.isInteger(5.0); // true

Number.isInteger(5.1); // false

Number.isInteger('5.0'); // false
```

**Ký hiệu mũ**

Ký hiệu mũ (exponential notation) là một cách để biểu diễn số theo dạng “hệ số nhân với 10 lũy thừa” để thể hiện các số rất lớn hoặc rất nhỏ một cách gọn gàng. 

Ký hiệu mũ bao gồm một hệ số (thường là số thập phân nằm trong khoảng từ 1 đến 10) và một số mũ, cho biết số lần cơ số 10 được nhân với chính nó. Ví dụ, 1.56 x 10^7 là cách viết ký hiệu mũ cho một số rất lớn (1.56 x 10 000 000).

Trong JavaScript, ký hiệu mũ được sử dụng với chữ cái e (hoặc E), viết tắt cho "exponent" (số mũ) hoặc "power of 10" (lũy thừa của 10).

|Ký hiệu mũ (JavaScript)|Ý nghĩa toán học|Giá trị|
|-----------------------|----------------|-------|
|1e3|1×103|1000|
|2.5e-2|2.5×10−2|0.025|
|5.67e5|5.67×105|567000|

Ví dụ:

```js
let number1 = 1e3;    // 1000

let number2 = 2.5e-2; // 0.025

let number3 = 5.67e5; // 567000

  

console.log(number1);

console.log(number2);

console.log(number3);
```

**Các phương thức của Number**

Kiểu dữ liệu Number cũng có một số phương thức tích hợp sẵn. Tuy nhiên, bạn nên cẩn thận khi sử dụng ký hiệu dấu chấm (.) với các số nguyên là giá trị thuần (literals) vì JavaScript sẽ nhầm lẫn dấu chấm đó với dấu chấm trong số thập phân. Để xử lý vấn đề này, JavaScript có một số cách, chúng ta sẽ minh họa bằng phương thức toExponential(); phương thức này trả về số dưới dạng chuỗi dưới dạng ký hiệu mũ.

\- Sử dụng 2 dấu chấm

5..toExponential();

\>>'5e+0'

\- Thêm một khoảng trắng trước dấu chấm

5 .toExponential(); >> "5e+0"

\- Luôn viết số nguyên dưới dạng số thập phân

5.0.toExponential(); >> "5e+0"

\- Đặt số nguyên trong ngoặc đơn

(5).toExponential(); >> "5e+0"

\- Gán số cho một hằng

const number = 5;

\>> 5

number.toExponential();

\>> "5e+0"

Chúng ta cùng tìm hiểu thêm một số phương thức của Number.

\- Phương thức toFixed(), để làm tròn một số đến một số lượng “chữ số thập phân” cố định

const PI = 3.1415926;

<< undefined

PI.toFixed(3); //chỉ cần sử dụng một dấu chấm, khi sử dụng phương thức này cho hằng hoặc biến

<< "3.142"

Để ý: giá trị trả về là kiểu chuỗi, chứ không phải kiểu số

\- Phương thức toPrecision(), để làm tròn một số đến một “số lượng chữ số” có nghĩa cố định, kết quả cũng trả về kiểu chuỗi (và thường sử dụng ký hiệu mũ)

325678..toPrecision(2);

<< "3.3e+5"

2.459.toPrecision(2);

<< "2.5"

**Một số phép toán số học**

\- Phép cộng (addition)

5 + 4.3;

<< 9.3

\- Phép trừ (subtraction)

5 + 4.3;

<< 9.3

\- Phép nhân (multiplication)

6 \* 7;

<< 42

\- Phép chia (division)

3/7;

<<0.42857142857142855

\- Lũy thừa (exponentiation)

2\*\*3; //có từ ES2017

<< 8

\- Phép chia dư (modulo)

23 % 6

<< 5

**Thay đổi giá trị của biến**

Nếu một biến đã được gán giá trị, bạn có thể thay đổi giá trị của nó bằng các phép toán sau:

let points = 0; //khởi tạo biến points có giá trị là 0

<< 0

points = points + 10;

<< 10

Lệnh trên đã thay đổi giá trị của biến points thành 10.

Có cách viết lệnh ngắn gọn hơn, bằng cách sử dụng toán tử gán kết hợp (compound assignment operator +=).

points += 10;

<< 20

Các phép toán khác cũng có toán tử gán kết hợp.

points -= 5; //giảm points đi 5

<< 15

points \*= 2; //nhân đôi points

<< 30

points /= 3; //chia points cho 3

<< 10

points %= 7; //chia 7 lấy phần dư

<< 3

**Tăng biến lên 1 đơn vị**

Nếu bạn chỉ muốn tăng giá trị của biến lên 1 đơn vị, bạn có thể sử dụng toán tử ++. Toán tử này có thể đặt trước hoặc sau biến.

let points = 5;

points++

<< 6

Câu hỏi quan trọng là: đặt toán tử ++ trước và sau biến thì có khác gì nhau không? Có, sự khác biệt chính là giá trị được trả về bởi phép toán. Cả hai phép toán đều tăng giá trị của biến points lên 1, nhưng:

\- points++ sẽ trả về giá trị ban đầu, sau đó mới tăng giá trị (của points) lên 1

\- ++points sẽ tăng giá trị (của points) lên 1, sau đó mới trả về giá trị mới

points++; //sẽ trả về 6, sau đó tăng points lên 7

<< 6

points

<< 7

++points; //sẽ tăng points lên 8, sau đó trả về 8

<< 8

points

<< 8

Toán tử -- cũng làm việc tương tự toán tử ++.

**Vô cực**

Vô cực (infinity) là một “giá trị lỗi đặc biệt” trong JavaScript được dùng để đại diện cho bất kỳ số nào quá lớn so với khả năng xử lý của ngôn ngữ này. Số lớn nhất mà JavaScript có thể xử lý là 1.7976931348623157e+308.

1e308; // 1 với 308 số 0!

<< 1e+308

2e308; // too big!

<< Infinity

Cũng có số âm vô cực (-infinity) được dùng để đại diện cho số âm nhỏ hơn -1.7976931348623157e+308.

\-1e309;

<< -Infinity

Bạn cũng nhận được giá trị infinity khi thực hiện phép chia cho 0.

1/0;

<< Infinity

Số nhỏ nhất mà JavaScript có thể xử lý là 5e^-324 (tương đương 5 x 10 mũ -324). Bất kỳ số nào nhỏ hơn mức này sẽ được đánh giá là 5e^-324 hoặc là 0.

5e-324;

<< 5e-324

3e-325;

<< 5e-324

2e-325;

<< 0

**NaN**

NaN là một giá trị lỗi, viết tắt của "Not a Number" (không phải là một Số). Nó được sử dụng khi một phép toán được thực hiện nhưng kết quả không phải là một giá trị số, chẳng hạn như khi bạn cố gắng nhân một chuỗi với một số.

'hello' \* 5;

<< NaN

Tuy nhiên, kết quả trả về của toán tử typeof lại khá lạ.

typeof NaN

'number'

**Kiểm tra một giá trị có phải là một số hay không?**

Bạn có thể kiểm tra xem một giá trị có phải là một số có thể sử dụng được hay không bằng cách dùng phương thức Number.isFinite(). Phương thức này sẽ trả về true nếu giá trị đó là một số không phải là Infinity, -Infinity hoặc NaN.

Number.isFinite(1/0);

<< false

Number.isFinite(-Infinity);

<< false

Number.isFinite(NaN);

<< false

Number.isFinite(42);

<< true

### 4.2 Bài tập và thực hành

**Bài tập 4a.** Tạo ra một máy tính cầm tay (calculator) với các yêu cầu như sau:

\- Tạo thư mục dự án (ví dụ: calculator)

\- Nhúng Git vào trong dự án

\- Viết mã HTML, CSS, JS thành 3 tập tin riêng biệt

\- Tạo giao diện bằng HTML, CSS

\- Viết xử lý bằng JS

\- Thực hiện commit sau khi hoàn thành mỗi chức năng (ví dụ: xong HTML, xong CSS, xong JS)

\- Đẩy thư mục dự án lên Github

\- Yêu cầu người làm hiểu được ý nghĩa của từng dòng mã

\- Bạn có thể tự viết theo cách đơn giản nhất (quan trọng là hiểu từng dòng mã), hoặc có thể tham khảo cách làm của chatbot.

  

Giao diện tham khảo (chatbot làm):

  

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhAe5c5rUdahOXuT0sHd6otFdDtp-jToVufOiCTN2MUWnq3C0kxJZXyMKAccx6s61zw_imy3VvUJCab_WXaPOyRXSonCo9OVl_X4KFSo7_hX_R4KCjpaeYXb3j7YIiTedL_GLQ5-Ex56mrXgmiWa0xx9ZLaNfgb71G96CorNcvI8ZfSXCT5ReAPxVZOS6I/s320/GiaoDien.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhAe5c5rUdahOXuT0sHd6otFdDtp-jToVufOiCTN2MUWnq3C0kxJZXyMKAccx6s61zw_imy3VvUJCab_WXaPOyRXSonCo9OVl_X4KFSo7_hX_R4KCjpaeYXb3j7YIiTedL_GLQ5-Ex56mrXgmiWa0xx9ZLaNfgb71G96CorNcvI8ZfSXCT5ReAPxVZOS6I/s633/GiaoDien.png)

  

Mã nguồn tham khảo (chatbot làm)

\[calculator.html\]

```html
<!DOCTYPE html\>

<html lang\="vi"\>

<head\>

    <meta charset\="UTF-8"\>

    <meta name\="viewport" content\="width=device-width, initial-scale=1.0"\>

    <title\>Máy Tính Cầm Tay JavaScript</title\>

</head\>

<body\>

    <!-- sinh viên nhớ xóa dòng này, đây là dòng thừa -->

    <div class\="calculator"\>

        <div id\="display" class\="calculator-display"\>0</div\>

        <div class\="calculator-keys"\>

            <!-- Hàng 1 -->

            <button class\="key key-ac" data-action\="clear"\>AC</button\>

            <button class\="key key-operator" data-action\="modulo"\>%</button\>

            <button class\="key key-operator" data-action\="exponentiation"\>^</button\> <!-- Biểu diễn Lũy thừa -->

            <button class\="key key-operator" data-action\="divide"\>/</button\>

  

            <!-- Hàng 2 -->

            <button class\="key key-digit" data-value\="7"\>7</button\>

            <button class\="key key-digit" data-value\="8"\>8</button\>

            <button class\="key key-digit" data-value\="9"\>9</button\>

            <button class\="key key-operator" data-action\="multiply"\>x</button\>

  

            <!-- Hàng 3 -->

            <button class\="key key-digit" data-value\="4"\>4</button\>

            <button class\="key key-digit" data-value\="5"\>5</button\>

            <button class\="key key-digit" data-value\="6"\>6</button\>

            <button class\="key key-operator" data-action\="subtract"\>\-</button\>

  

            <!-- Hàng 4 -->

            <button class\="key key-digit" data-value\="1"\>1</button\>

            <button class\="key key-digit" data-value\="2"\>2</button\>

            <button class\="key key-digit" data-value\="3"\>3</button\>

            <button class\="key key-operator" data-action\="add"\>+</button\>

  

            <!-- Hàng 5 -->

            <button class\="key key-digit" data-value\="0"\>0</button\>

            <button class\="key key-decimal" data-action\="decimal"\>.</button\>

            <button class\="key key-equals" data-action\="calculate"\>\=</button\>

        </div\>

    </div\>

  

    <!-- dòng này cũng thừa, các bạn hãy xóa đi -->

    <script\>

    </script\>

</body\>

</html\>
```
  

\[main.css\]

```css
        /\* Tùy chỉnh CSS cho Máy tính \*/

        body {

            font-family: 'Inter', sans-serif;

            background-color: #f0f4f8;

            display: flex;

            justify-content: center;

            align-items: center;

            min-height: 100vh;

            margin: 0;

        }

  

        .calculator {

            width: 100%;

            max-width: 380px;

            padding: 1rem;

            background-color: #334155; /\* Slate-700 \*/

            box-shadow: 0 20px 25px \-5px rgba(0, 0, 0, 0.3), 0 10px 10px \-5px rgba(0, 0, 0, 0.1);

            border-radius: 1.5rem;

            transform: scale(1);

            transition: transform 0.2s ease-in-out;

        }

  

        .calculator:active {

            transform: scale(0.99);

        }

  

        .calculator-display {

            background-color: #1e293b; /\* Slate-800 \*/

            color: #f8fafc; /\* White \*/

            font-size: 2.5rem;

            text-align: right;

            padding: 1rem 1.5rem;

            margin-bottom: 1rem;

            border-radius: 0.75rem;

            overflow-x: auto;

            white-space: nowrap;

            height: 5.5rem;

            display: flex;

            flex-direction: column;

            justify-content: flex-end;

            align-items: flex-end;

            line-height: 1;

        }

  

        .calculator-keys {

            display: grid;

            grid-template-columns: repeat(4, 1fr);

            gap: 0.75rem;

        }

  

        .key {

            padding: 1.5rem 0.5rem;

            font-size: 1.5rem;

            font-weight: 600;

            border: none;

            border-radius: 9999px; /\* Full rounded \*/

            cursor: pointer;

            transition: background-color 0.15s ease-in-out, transform 0.1s ease-in-out;

            box-shadow: 0 4px 6px \-1px rgba(0, 0, 0, 0.2), 0 2px 4px \-2px rgba(0, 0, 0, 0.15);

        }

  

        /\* Nút Số (Digits) \*/

        .key-digit, .key-decimal {

            background-color: #475569; /\* Slate-600 \*/

            color: #f8fafc;

        }

  

        .key-digit:hover, .key-decimal:hover {

            background-color: #64748b; /\* Slate-500 \*/

        }

        .key-digit:active, .key-decimal:active {

            transform: translateY(1px);

        }

  

        /\* Nút Toán tử (Operators) \*/

        .key-operator {

            background-color: #f97316; /\* Orange-600 \*/

            color: #fff;

        }

  

        .key-operator:hover {

            background-color: #fb923c; /\* Orange-500 \*/

        }

        .key-operator:active {

            transform: translateY(1px);

        }

  

        /\* Nút Đặc biệt (AC/Equals) \*/

        .key-ac {

            background-color: #ef4444; /\* Red-500 \*/

            color: #fff;

        }

  

        .key-ac:hover {

            background-color: #f87171; /\* Red-400 \*/

        }

        .key-ac:active {

            transform: translateY(1px);

        }

  

        .key-equals {

            background-color: #10b981; /\* Emerald-500 \*/

            color: #fff;

            grid-column: span 2; /\* Chiếm 2 cột \*/

        }

  

        .key-equals:hover {

            background-color: #34d399; /\* Emerald-400 \*/

        }

        .key-equals:active {

            transform: translateY(1px);

        }

        /\* Responsive design \*/

        @media (max-width: 640px) {

            .calculator {

                max-width: 90%;

                margin: 1rem;

            }

            .calculator-display {

                font-size: 2rem;

            }

            .key {

                padding: 1rem 0.5rem;

                font-size: 1.25rem;

            }

        }
```

\[script.js\]

```js
 // Lấy các phần tử DOM cần thiết

        const display = document.getElementById('display');

        const keys = document.querySelector('.calculator-keys');

  

        // Đối tượng lưu trữ trạng thái của máy tính

        const calculator = {

            displayValue: '0',

            firstOperand: null,

            waitingForSecondOperand: false,

            operator: null,

        };

  

        // Hàm cập nhật màn hình hiển thị

        function updateDisplay() {

            // Hiển thị giá trị hiện tại. Cắt bớt nếu quá dài.

            let displayString = String(calculator.displayValue);

            // Xử lý các giá trị đặc biệt (Infinity, -Infinity, NaN)

            if (displayString.includes('Infinity')) {

                display.textContent = 'Lỗi: Vô cực';

            } else if (displayString === 'NaN') {

                display.textContent = 'Lỗi: Không phải số';

            } else {

                display.textContent = displayString.length > 18

                    ? parseFloat(displayString).toPrecision(15)

                    : displayString;

            }

        }

  

        // Hàm xử lý nhập số

        function inputDigit(digit) {

            const { displayValue, waitingForSecondOperand } = calculator;

  

            if (waitingForSecondOperand === true) {

                calculator.displayValue = digit;

                calculator.waitingForSecondOperand = false;

            } else {

                // Nếu displayValue là '0', thay thế bằng digit mới, ngược lại nối thêm

                calculator.displayValue = displayValue === '0' ? digit : displayValue + digit;

            }

  

            updateDisplay();

        }

  

        // Hàm xử lý dấu thập phân

        function inputDecimal(dot) {

            // Không cho phép nhập dấu thập phân nếu đang chờ toán hạng thứ hai

            if (calculator.waitingForSecondOperand === true) {

                calculator.displayValue = '0.';

                calculator.waitingForSecondOperand = false;

                updateDisplay();

                return;

            }
  

            // Chỉ cho phép thêm dấu thập phân nếu chưa có

            if (!calculator.displayValue.includes(dot)) {

                calculator.displayValue += dot;

            }

  

            updateDisplay();

        }

  

        // Hàm xử lý toán tử

        function handleOperator(nextOperator) {

            const { firstOperand, displayValue, operator } = calculator;

            // Chuyển giá trị hiển thị thành số thực

            const inputValue = parseFloat(displayValue);

  

            // Kiểm tra Number.isFinite() như trong tài liệu

            if (!Number.isFinite(inputValue) && inputValue !== 0) {

                 // Không làm gì nếu giá trị hiện tại là NaN, Infinity, -Infinity

                calculator.displayValue = 'Lỗi phép toán';

                updateDisplay();

                return;

            }

  

  

            if (firstOperand === null) {

                // Đây là toán hạng đầu tiên

                calculator.firstOperand = inputValue;

            } else if (operator) {

                // Có toán tử và đã có toán hạng thứ nhất -> Thực hiện tính toán

                const result = performCalculation\[operator\](firstOperand, inputValue);

  

                // Cập nhật kết quả, làm tròn nếu cần (để tránh lỗi số học dấu phẩy động)

                calculator.displayValue = String(result);

                calculator.firstOperand = result;

            }

  

            // Cập nhật trạng thái cho phép toán tiếp theo

            calculator.waitingForSecondOperand = true;

            calculator.operator = nextOperator;

            updateDisplay();

        }

  

        // Đối tượng chứa logic tính toán cho từng toán tử

        const performCalculation = {

            '/': (firstOperand, secondOperand) => firstOperand / secondOperand,

            '\*': (firstOperand, secondOperand) => firstOperand \* secondOperand,

            '+': (firstOperand, secondOperand) => firstOperand + secondOperand,

            '-': (firstOperand, secondOperand) => firstOperand - secondOperand,

            // Lũy thừa (Exponentiation): sử dụng toán tử \*\*

            '^': (firstOperand, secondOperand) => firstOperand \*\* secondOperand,

            // Phép chia dư (Modulo)

            '%': (firstOperand, secondOperand) => firstOperand % secondOperand,

        };

  

        // Hàm thiết lập lại máy tính

        function resetCalculator() {

            calculator.displayValue = '0';

            calculator.firstOperand = null;

            calculator.waitingForSecondOperand = false;

            calculator.operator = null;

            updateDisplay();

        }

  

        // Lắng nghe sự kiện click trên các nút

        keys.addEventListener('click', (event) => {

            const { target } = event;

            const action = target.dataset.action;

            const value = target.dataset.value;

  

            // Đảm bảo chỉ xử lý các nút (button)

            if (!target.matches('button')) {

                return;

            }

  

            // Xử lý nút số

            if (value !== undefined) {

                inputDigit(value);

                return;

            }

  

            // Xử lý các hành động

            if (action === 'decimal') {

                inputDecimal('.');

                return;

            }

  

            if (action === 'clear') {

                resetCalculator();

                return;

            }

  

            // Nếu là phép toán hoặc dấu bằng

            if (action) {

                if (action === 'calculate') {

                    // Xử lý phép tính cuối cùng

                    handleOperator(calculator.operator);

                    calculator.waitingForSecondOperand = true;

                    calculator.operator = null; // Kết thúc phép toán

                } else {

                    // Xử lý toán tử tiếp theo

                    handleOperator(action);

                }

                return;

            }

        });

  

        // Khởi tạo hiển thị

        updateDisplay();
```

### 4.3 Câu hỏi ôn tập

**Câu 1.** Đoạn mã này xuất ra cái gì: const float = 3.14; typeof float;

A. float

B. double

**C. number**

D. PI

**Câu 2.** Đoạn mã này xuất ra cái gì: let number1 = 1e3; console.log(number1);

**A. 1000**

B. 1e3

C. 0.001

D. 0.003

**Câu 3.** Đoạn mã này xuất ra cái gì: const PI = 3.1415926; console.log(PI.toFixed(4));

A. 3.142

**B. 3.1416**

C. 3.0000

D. 3141

**Câu 4.** Đoạn mã này xuất ra cái gì: const PI = 3.1415926; console.log(PI.toPrecision(3));

**A. 3.14**

B. 3.142

C. 3.141

D. 3.000

**Câu 5.** Đoạn mã này xuất ra cái gì? typeof NaN;

A. NaN

B. string

C. error

**D. number**
