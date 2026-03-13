
## BTTH03: JS nền tảng, DOM & Sự kiện

**Đối tượng:** Sinh viên chưa học lý thuyết JavaScript

---

## 1. MỤC TIÊU HỌC TẬP

Sau buổi lab, sinh viên có thể:

- Mô tả được JavaScript là gì, chạy ở đâu, khác HTML/CSS ở điểm nào.
- Viết được các đoạn JS đơn giản với:
  - Biến, kiểu dữ liệu cơ bản (number, string, boolean),
  - Cú pháp lệnh, toán tử đơn giản,
  - Cấu trúc điều khiển if/else, vòng lặp đơn giản,
  - Hàm (function) có tham số và giá trị trả về.
- Thao tác được với DOM:
  - Lấy phần tử bằng `document.getElementById`,
  - Thay đổi nội dung văn bản, kiểu dáng (style),
  - Lắng nghe và xử lý một số sự kiện cơ bản: `click`, `input`.
- Nhận biết jQuery là một thư viện hỗ trợ thao tác DOM/sự kiện (ở mức nhận diện, chưa cần sử dụng thành thạo).

---

## 2. CẤU TRÚC THỜI GIAN BUỔI LAB
- 03 tiết thực hành.

---

## 3. HOẠT ĐỘNG 1 (45’): GIỚI THIỆU JS & CÚ PHÁP CƠ BẢN

### 3.1. Chuẩn bị file HTML & JS

Tạo file `lab-js-basic.html`:

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Lab JS Cơ bản</title>
</head>
<body>
  <h1>Khám phá JavaScript</h1>
  <p id="welcome">Chưa có JavaScript...</p>
  <button id="runBtn">Nhấn để chạy JS</button>

  <script src="main.js"></script>
</body>
</html>
```

Tạo file `main.js`:

```js
console.log("Hello from JavaScript!");
```


---

### 3.2. Nhiệm vụ cho sinh viên

#### Bước 1: Mở file \& Quan sát bằng Console

1. Mở `lab-js-basic.html` trong trình duyệt (Chrome/Edge/…).
2. Mở DevTools → tab **Console**.
3. Quan sát thông báo xuất hiện.

> Câu hỏi:
> - Em thấy dòng thông báo nào trong console?
> - Em thấy dòng ```Hello from JavaScript!```
> - Điều này cho em biết JavaScript đang làm gì khi trang web được tải?
> - Khi trang web được tải , JS thực hiện lệnh console.log in ra màn hình dòng chữ ```Hello from JavaScript!```

---

#### Bước 2:  “JavaScript là gì?” (Tra cứu nhanh)

Sử dụng 1–2 nguồn tài liệu (vd. W3Schools, freeCodeCamp, …), tóm tắt:

> a) JavaScript chạy ở đâu? (Trình duyệt / Server / Cả hai?)
> b) HTML, CSS, JavaScript mỗi phần chịu trách nhiệm chính về điều gì?
>
> - HTML: Content & Structure (Nội dung & Cấu trúc)
> - CSS: Presentation & Design (Trình bày & Thiết kế)
> - JavaScript: Behavior & Interactivity (Hành vi & Tương tác)

---

#### Bước 3: Thử nghiệm biến \& kiểu dữ liệu trong Console

Trong tab Console, gõ từng dòng sau và ghi lại kết quả:

```js
let age = 20;
const name = "An";
let isStudent = true;

typeof age;
typeof name;
typeof isStudent;

1 + 2 * 3;
"Hello " + "world";
```

> Câu hỏi:
> - Kết quả `typeof age` là gì? ```KQ là : number```
> - Kết quả `typeof name` là gì? ```KQ là : string```
> - Kết quả `typeof isStudent` là gì? ``` KQ là : boolean``
> - Em hãy tự mô tả ngắn gọn:
>   - `number` là: ```Kiểu dữ liệu số (bao gồm cả số nguyên như 20 và số thập phân như 9.5). Dùng để thực hiện các phép tính toán học.```
>   - `string` là: ```Kiểu dữ liệu chuỗi ký tự (văn bản). Luôn được đặt trong dấu ngoặc kép "", ngoặc đơn '' hoặc dấu backtick `.```
>   - `boolean` là: ```Kiểu dữ liệu logic, chỉ có hai giá trị duy nhất là true (đúng) hoặc false (sai). Thường dùng trong các điều kiện kiểm tra.```

---

#### Bước 4: Viết đoạn script tính tuổi

Mở file `main.js`, viết thêm:

```js
let name = "An";
let yearOfBirth = 2005;
let currentYear = 2026;
let age = currentYear - yearOfBirth;

console.log("Xin chào, mình là " + name + ", năm nay mình " + age + " tuổi.");
```

Sau đó:

1. Đổi giá trị `name`, `yearOfBirth` thành thông tin của chính em.
2. Reload trang \& quan sát console.

> Câu hỏi:
> - Dòng log hiển thị gì sau khi em sửa thông tin?
> - ```Hello from JavaScript! Xin chào, mình là Trường, năm nay mình 20 tuổi.```
> - Nếu em quên dấu `;` hoặc quên dấu `+`, điều gì xảy ra? Trình duyệt báo lỗi thế nào?
> - Trình duyệt báo lỗi ```Uncaught SyntaxError: missing ) after argument list```
---

#### Bước 5: Phản tư nhanh (Reflection)

> - Điều thú vị nhất em vừa khám phá được về console là gì?
> - Console không chỉ để hiện lỗi mà còn là một "phòng thí nghiệm" để chạy thử code JS ngay lập tức.
> - Em gặp lỗi cú pháp nào? Em đã xử lý bằng cách nào (tự sửa, hỏi bạn, đọc lỗi, tìm Google, …)?
> - Quên dấu + khi nối chuỗi, viết sai chính tả tên biến (ví dụ yearOfBirth thành yearofbirth), hoặc thiếu dấu ngoặc đơn/kép. Em tự sửa.
---

## 4. HOẠT ĐỘNG 2 (40’): CẤU TRÚC ĐIỀU KHIỂN \& HÀM

### 4.1. Chuẩn bị file logic (hoặc viết tiếp trong main.js)

Ví dụ đoạn mã:

```js
// TODO: Đổi giá trị score và quan sát kết quả
let score = 7.5;

// TODO: Dự đoán điều kiện if/else đang làm gì, rồi chạy thử
if (score >= 8) {
  console.log("Giỏi");
} else if (score >= 6.5) {
  console.log("Khá");
} else if (score >= 5) {
  console.log("Trung bình");
} else {
  console.log("Yếu");
}

// TODO: Viết hàm tính điểm trung bình 3 môn
function tinhDiemTrungBinh(m1, m2, m3) {
  let avg = (m1 + m2 + m3) / 3;
  return avg;
}

// Gợi ý dùng thử hàm trong console:
// tinhDiemTrungBinh(8, 7, 9);
```


---

### 4.2. Nhiệm vụ cho sinh viên

#### Bước 1: Đoán trước – chạy sau

> a) Nếu `score = 9`, em dự đoán console sẽ in: Giỏi
> b) Nếu `score = 6`, em dự đoán console sẽ in: Trung Bình

Sau đó:

1. Thay `score = 9`, reload trang hoặc chạy file và kiểm tra console.
2. Thay `score = 6`, kiểm tra lại.

> So sánh dự đoán và kết quả thực tế:
> - Trường hợp `score = 9`: Dự đoán vs Thực tế: Giỏi (Giống với dự đoán)
> - Trường hợp `score = 6`: Dự đoán vs Thực tế: Trung Bình ( Giống với dự đoán )

---

#### Bước 2: Mô tả lại if/else bằng lời

> - Khi nào chương trình in `"Giỏi"`? Khi score có giá trị lớn hơn hoặc bằng 8
> - Khi nào chương trình in `"Yếu"`? Khi score có giá trị dưới 5
> - Em hãy mô tả cấu trúc `if/else` bằng lời của em (có thể ví von “ngã rẽ” trong đời sống):
> - Cấu trúc if/else giống như một ngã rẽ trên đường: Nếu con đường phía trước thỏa mãn điều kiện (biển báo) thì ta đi tiếp, nếu không thì buộc phải rẽ sang hướng khác để tìm lựa chọn phù hợp hơn.

#### Bước 3: Làm việc với hàm

1. Mở Console, gọi hàm:
```js
tinhDiemTrungBinh(8, 7, 9);
```

> Em ghi lại giá trị hàm trả về: 8

2. Viết thêm hàm `xepLoai(avg)` trong file JS:
```js
function xepLoai(avg) {
  // TODO: Dùng if/else để:
  // avg >= 8  -> "Giỏi"
  // avg >= 6.5 -> "Khá"
  // avg >= 5  -> "Trung bình"
  // còn lại   -> "Yếu"
  if (avg >= 8) return "Giỏi";
  if (avg >= 6.5) return "Khá";
  if (avg >= 5) return "Trung bình";
  return "Yếu";
}
```

3. Gọi thử trong console:
```js
let avg = tinhDiemTrungBinh(8, 7, 9);
let loai = xepLoai(avg);
console.log("Điểm TB:", avg, " - Xếp loại:", loai);
```

> Câu hỏi:
> - Một hàm gồm những phần chính nào?
>   - Tên hàm: Định danh để gọi hàm (VD: tinhDiemTrungBinh).
>   - Tham số (parameters): Các biến đầu vào nằm trong dấu () (VD: m1, m2, m3).
>   - Thân hàm (body): Khối lệnh nằm trong {} để thực hiện logic.
>   - Giá trị trả về (return): Kết quả sau khi chạy hàm qua từ khóa return.
> - Ưu điểm của việc dùng hàm thay vì lặp lại cùng một đoạn code nhiều lần là gì? Tái sử dụng code, giúp chương trình gọn gàng, dễ quản lý và tránh sai sót khi cần sửa logic ở nhiều nơi.

---

#### Bước 4: Mở rộng nhỏ (tuỳ chọn)

Viết hàm `kiemTraTuoi(age)`:

```js
function kiemTraTuoi(age) {
  // TODO:
  // Nếu age >= 18 -> console.log("Đủ 18 tuổi");
  // Ngược lại -> console.log("Chưa đủ 18 tuổi");
  if (age >= 18) {
    console.log("Đủ 18 tuổi");
  } else {
    console.log("Chưa đủ 18 tuổi");
  }
}
```

Gọi thử: `kiemTraTuoi(16);`, `kiemTraTuoi(20);`.

---

#### Bước 5: Phản tư

> - Phần nào trong if/else hoặc hàm khiến em khó hiểu nhất? Thường là việc hiểu cách dữ liệu truyền vào Tham số và cách return đưa kết quả ra ngoài để sử dụng cho hàm khác.
> - Em đã làm gì để vượt qua (thử nhiều lần, hỏi bạn, xem lại ví dụ, tra Google, …)?Thử thay đổi giá trị nhiều lần (trial and error), dùng console.log() để kiểm tra từng bước chạy của code và xem lại các ví dụ mẫu.

---

## 5. HOẠT ĐỘNG 3 (40’): THAO TÁC DOM \& SỰ KIỆN

### 5.1. Chuẩn bị HTML

Thêm vào trang (hoặc tạo file mới):

```html
<section>
  <h2>DOM & Sự kiện</h2>
  <p id="status">Chưa có tương tác...</p>

  <button id="btnHello">Chào</button>
  <button id="btnRed">Đổi màu nền thành đỏ</button>

  <div style="margin-top: 20px;">
    <label>Nhập tên: </label>
    <input id="nameInput" type="text" />
    <p id="greeting"></p>
  </div>
</section>

<script src="dom.js"></script>
```

Tạo file `dom.js`:

```js
const statusEl = document.getElementById("status");
const btnHello = document.getElementById("btnHello");

btnHello.addEventListener("click", function () {
  statusEl.textContent = "Xin chào! Đây là nội dung được thay đổi bằng JavaScript.";
});
```


---

### 5.2. Nhiệm vụ cho sinh viên

#### Bước 1: Đọc \& giải thích

> Câu hỏi:
> - `document.getElementById("status")` đang làm gì?
> - Tìm và chọn phần tử HTML có thuộc tính `id` là "status" để có thể thao tác với nó bằng JavaScript.
> - Sự kiện `"click"` xảy ra khi nào?
> - Xảy ra khi người dùng dùng chuột và nhấn vào một phần tử trên trang web.
> - Trong đoạn code trên, khi nhấn nút `btnHello`, điều gì thay đổi trên trang?
> - Nội dung văn bản bên trong phần tử có `id="status"` sẽ được thay đổi thành "Xin chào! Đây là nội dung được thay đổi bằng JavaScript.".

---

#### Bước 2: Thử nghiệm nút đổi màu nền

Hoàn thiện code:

```js
const btnRed = document.getElementById("btnRed");

btnRed.addEventListener("click", function () {
  // TODO: Đổi màu nền trang thành đỏ
  document.body.style.backgroundColor = "red";
});
```

> Câu hỏi:
> - Em có thể đổi sang màu khác (vd. `lightblue`) không? Hãy thử.
> - **Trả lời:** Có. Chỉ cần thay giá trị `"red"` thành `"lightblue"`.
 > - Em hãy ghi lại 1 ví dụ khác mà JavaScript có thể làm với `document.body.style`.
> - **Trả lời:** `document.body.style.fontSize = "18px";` (để thay đổi cỡ chữ toàn trang).

---

#### Bước 3: Xử lý sự kiện input – gõ tên, hiện lời chào

Hoàn thiện code:

```js
const nameInput = document.getElementById("nameInput");
const greeting = document.getElementById("greeting");

nameInput.addEventListener("input", function () {
  const value = nameInput.value;
  greeting.textContent = "Xin chào, " + value + "!";
});
```

> Câu hỏi:
> - Sự kiện `"input"` khác gì so với `"click"`?
> - **`input`**: Kích hoạt **liên tục** ngay khi giá trị trong ô nhập liệu thay đổi (mỗi lần gõ phím hoặc xóa ký tự).
> - **`click`**: Chỉ kích hoạt **một lần** khi người dùng nhấn chuột vào phần tử.
> - Khi em xoá hết nội dung ô input, dòng `greeting` hiển thị gì?
> - Hiển thị: `Xin chào, !` (Do biến `value` lúc này là một chuỗi rỗng).

---

#### Bước 4: Liên hệ khái niệm DOM

> DOM (Document Object Model) là mô hình biểu diễn trang HTML dưới dạng một **cây các đối tượng** mà JavaScript có thể truy cập và thay đổi.
>
> Em hãy:
> - Tự mô tả DOM bằng lời của em:
>   DOM là một **"bản đồ"** hoặc **"cây cấu trúc"** của trang HTML. Nó biến các thẻ HTML tĩnh thành các đối tượng mà JavaScript có thể "cầm, nắm" và điều khiển để thay đổi nội dung, màu sắc hoặc hành vi của trang web.
> - Nêu 1 ví dụ “thao tác DOM” trong bài (ghi lại 1 dòng lệnh cụ thể).
>   `greeting.textContent = "Xin chào, " + value + "!";`

---

#### Bước 5: Phản tư

> - **Phần khiến em khó hiểu nhất:**
>   Việc hiểu cách các sự kiện (event) chờ đợi hành động của người dùng và cách truyền dữ liệu từ ô `input` sang một thẻ `div` hoặc `p` khác thông qua biến.
> - **Cách vượt qua:**
>   Em đã thực hiện **thử sai nhiều lần**, quan sát lỗi hiển thị trong **Console**, so sánh kỹ cú pháp với ví dụ mẫu và tra cứu thêm trên MDN/W3Schools để hiểu rõ từng thuộc tính.

---

## 6. KẾT THÚC (15’): GIỚI THIỆU JQUERY \& PHẢN TƯ

### 6.1. Nhìn nhanh jQuery (so sánh với JS thuần)

Ví dụ:

```js
// JS thuần
document.getElementById("btnHello").addEventListener("click", function () {
  alert("Hello from JS!");
});

// jQuery (giả sử đã import jQuery)
$("#btnHello").on("click", function () {
  alert("Hello from jQuery!");
});
```

> Câu hỏi:
> - Điểm giống nhau về chức năng giữa 2 đoạn code trên là gì?
> - Điểm khác nhau về cú pháp là gì (`document.getElementById` vs `$("#id")`, `addEventListener` vs `.on`)?
> - Em hãy tra cứu nhanh “What is jQuery used for?” và ghi 2 ý chính:
>   1. ................................................................
>   2. ................................................................

---

### 6.2. Tự đánh giá \& định hướng

> 1. Sau buổi lab, em tò mò nhất về phần nào của JavaScript/DOM?
> 2. Em muốn tự làm thêm tính năng gì trên trang web (vd: bộ đếm, đổi theme, pop-up, mini game, …)?
> 3. Em đánh giá mức độ hiểu của mình về:
>    - Biến \& kiểu dữ liệu: [ ] Chưa hiểu  [ ] Tạm ổn  [ ] Khá rõ
>    - If/else \& hàm:       [ ] Chưa hiểu  [ ] Tạm ổn  [ ] Khá rõ
>    - DOM \& sự kiện:       [ ] Chưa hiểu  [ ] Tạm ổn  [ ] Khá rõ

---

## 7. GHI CHÚ CHO GIẢNG VIÊN (NỘI BỘ)

- Có thể cho SV làm theo cặp/nhóm 2–3 để hỗ trợ nhau thử nghiệm, đọc lỗi, tra cứu.
- Tùy thời lượng thực tế, có thể:
    - Giảm bớt phần mở rộng (hàm `kiemTraTuoi`, tuỳ biến thêm hiệu ứng).
    - Hoặc tăng thêm bài tập DOM (ẩn/hiện một khối, đếm số lần click, v.v.).
- Phiếu học tập tiếp theo có thể chi tiết hóa từng hoạt động thành form trả lời, chỗ dán ảnh, và câu hỏi mini test trắc nghiệm.

```

---```
