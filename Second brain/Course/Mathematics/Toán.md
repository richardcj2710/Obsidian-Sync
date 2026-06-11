---

---
---
# Tổng hợp công thức tính diện tích các hình - Ôn thi THPTQG

Dưới đây là hệ thống toàn bộ các [[Second_Brain/Second brain/Course/Tin (Lý thuyết)|công thức tính diện]] tích hình phẳng, khối tròn xoay và ứng dụng [[Second_Brain/Second brain/IELTS/Writting|tích phân thường xuyên]] [[Second_Brain/Second brain/Học tiếng anh|xuất hiện trong cấu]] trúc đề thi THPTQG.

---

## I. Diện tích các hình phẳng cơ bản

### 1. Tam giác
Cho tam giác $ABC$ có các cạnh tương ứng là $a, b, c$; đường cao tương ứng là $h_a, h_b, h_c$; bán kính [[Second_Brain/Extra skills/Python/Python algorithm|đường tròn ngoại tiếp]] là $R$; bán kính đường tròn nội tiếp là $r$; và nửa chu vi là $p = \frac{a+b+c}{2}$.

* **Công thức cơ bản (chiều cao):**
  $$S = \frac{1}{2}a \cdot h_a = \frac{1}{2}b \cdot h_b = \frac{1}{2}c \cdot h_c$$

* **Công thức theo góc (Hàm số sin):**
  $$S = \frac{1}{2}ab \cdot \sin C = \frac{1}{2}bc \cdot \sin A = \frac{1}{2}ac \cdot \sin B$$

* **Công thức Heron (Sử dụng khi biết độ dài 3 cạnh):**
  $$S = \sqrt{p(p-a)(p-b)(p-c)}$$

* **Theo bán kính đường tròn ngoại tiếp $R$:**
  $$S = \frac{abc}{4R}$$

* **Theo bán kính đường tròn nội tiếp $r$:**
  $$S = p \cdot r$$

* **Trường hợp đặc biệt (Tam giác vuông):**
  $$S = \frac{1}{2} \cdot (\text{Tích hai cạnh góc vuông})$$

* **Trường hợp đặc biệt (Tam giác đều cạnh $a$):** *(Tần suất xuất hiện cực cao dưới dạng mặt đáy khối chóp/lăng trụ)*
  $$S = \frac{a^2\sqrt{3}}{4}$$
  *(Mẹo nhớ nhanh đường cao tam giác đều: $h = \frac{a\sqrt{3}}{2}$)*

---

### 2. Hình tứ giác

* **Hình vuông (cạnh $a$):**
  $$S = a^2 = \frac{1}{2}d^2 \quad (\text{với } d = a\sqrt{2} \text{ là độ dài đường chéo})$$

* **Hình chữ nhật (hai cạnh $a, b$):**
  $$S = a \cdot b$$

* **Hình bình hành (cạnh đáy $a$, chiều cao $h$, góc $\alpha$ giữa hai cạnh):**
  $$S = a \cdot h = a \cdot b \cdot \sin\alpha$$

* **Hình thoi (hai đường chéo $d_1, d_2$, cạnh $a$, góc nhọn $\alpha$):**
  $$S = \frac{1}{2}d_1 \cdot d_2 = a^2 \cdot \sin\alpha$$

* **Hình thang ($a, b$ là đáy lớn/đáy nhỏ, $h$ là chiều cao):**
  $$S = \frac{(a+b) \cdot h}{2}$$

* **Tứ giác bất kỳ có hai đường chéo vuông góc ($d_1 \perp d_2$):**
  $$S = \frac{1}{2}d_1 \cdot d_2$$

---

### 3. Hình tròn & Hình quạt tròn

* **Hình tròn (bán kính $R$):**
  $$S = \pi R^2$$

* **Hình quạt tròn (bán kính $R$, cung tròn có số đo $\alpha^\circ$ hoặc góc $\alpha$ bằng radian):**
  $$S = \frac{\pi R^2 \cdot \alpha^\circ}{360^\circ} = \frac{1}{2}R^2 \cdot \alpha \quad (\text{với } \alpha \text{ tính bằng radian})$$

---

## II. Diện tích các hình tròn xoay (Nón - Trụ - Cầu)

Trong các công thức dưới đây: $R$ là bán kính đáy (hoặc bán kính cầu), $l$ là độ dài đường sinh, $h$ là chiều cao hình khối.

### 1. Hình nón
* **Mối liên hệ giữa các đại lượng:** $l^2 = h^2 + R^2$ (Hệ thức Pitago)
* **Diện tích xung quanh:** 
  $$S_{xq} = \pi R l$$
* **Diện tích toàn phần:** 
  $$S_{tp} = S_{xq} + S_{\text{đáy}} = \pi R l + \pi R^2$$

### 2. Hình trụ
* **Mối liên hệ giữa các đại lượng:** $l = h$
* **Diện tích xung quanh:** 
  $$S_{xq} = 2\pi R l = 2\pi R h$$
* **Diện tích toàn phần:** 
  $$S_{tp} = S_{xq} + 2S_{\text{đáy}} = 2\pi R h + 2\pi R^2$$

### 3. Mặt cầu
* **Diện tích mặt cầu:** 
  $$S = 4\pi R^2$$

---

## III. Ứng dụng Tích phân tính diện tích hình phẳng (Giải tích 12)

### 1. Hình phẳng giới hạn bởi 1 đường cong và trục hoành $Ox$
Giới hạn bởi đồ thị $y = f(x)$, trục hoành $y = 0$, hai đường thẳng $x = a, x = b$:
$$S = \int_{a}^{b} |f(x)| \,dx$$

### 2. Hình phẳng giới hạn bởi 2 đường cong
Giới hạn bởi đồ thị $y = f(x)$, đồ thị $y = g(x)$, hai đường thẳng $x = a, x = b$:
$$S = \int_{a}^{b} |f(x) - g(x)| \,dx$$

---
## Notes

<iframe src="https://heid.vn/cong-thuc-toan-on-thi-tot-nghiep-thpt-bo-tui-chat-luong/" style="width: 100% ; height: 600px;"></iframe>


