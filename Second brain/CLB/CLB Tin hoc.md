Ban hoc tap: to chuc buoi hoc, cuoc thi, boi duong ky thuat kĩ năng tin học, lập trình văn phòng. Triển khia các dự án phần mềm, nghiên cứu đề tài khoa học kỹ thuật.
Ban truyền thông - thiết kế: Quả lý fanpage 
Quản lý sự kiện/ hậu cần: quản lý bên máy tính với quỹ các thứ để hỗ trợ tổ chức


# **Ban chủ nhiệm**

	Chủ nhiệm: (Hữu)
		quản lý chung với phân chia các công việc
		Nhiệt tình 


	Phó chủ nhiệm:
		Tuấn Kiệt 11/6 (Ban học tập : sđt: 
		Tố Uyên 11/6 (Ban hậu cần)  : sđt:
		Hạnh Nguyên 12/6 (Ban truyền thông) : sđt: 

- [ ]Tháng 11 sau: chủ đề Canva & Capcut 


________________________________________________________________________

Chương I: Ma trận, Định thức và Hệ phương trình tuyến tính bao gồm các khái niệm, công thức cơ bản về ma trận, cách tính định thức, tìm ma trận nghịch đảo, và các phương pháp giải hệ phương trình tuyến tính.

Dưới đây là tổng hợp các công thức và cách thức giải quan trọng theo yêu cầu:

---

# Tổng Hợp Công Thức và Phương Pháp Giải Toán Cao Cấp (Chương I)

## 1. Ma Trận (Matrices)

### 1.1. Khái niệm và Ký hiệu

Ma trận $A$ cấp $m \times n$ là một bảng gồm $m \cdot n$ số $a_{ij}$ được sắp xếp thành $m$ dòng và $n$ cột. $$ A = \begin{pmatrix} a_{11} & a_{12} & \dots & a_{1n} \ a_{21} & a_{22} & \dots & a_{2n} \ \vdots & \vdots & \ddots & \vdots \ a_{m1} & a_{m2} & \dots & a_{mn} \end{pmatrix} = [a_{ij}]_{m \times n} $$

### 1.2. Các Phép Toán Cơ Bản

|Phép toán|Công thức/Quy tắc quan trọng|Điều kiện thực hiện|
|:--|:--|:--|
|**Cộng** (Addition)|$A + B = [c_{ij}]_{m \times n}$, với $c_{ij} = a_{ij} + b_{ij}$.|$A$ và $B$ phải cùng cấp $m \times n$.|
|**Nhân với số** (Scalar Multiplication)|$\alpha A = [b_{ij}]_{m \times n}$, với $b_{ij} = \alpha \cdot a_{ij}$.|Không có điều kiện cấp, $\alpha$ là số thực.|
|**Nhân ma trận** (Multiplication)|$A_{m \times n} \cdot B_{n \times p} = C_{m \times p}$, với $c_{ik} = \sum_{j=1}^{n} a_{ij}b_{jk}$.|Số cột của ma trận đầu ($A$) phải bằng số dòng của ma trận thứ hai ($B$) ($n=n$).|
|**Chuyển vị** (Transpose)|$A = [a_{ij}]_{m \times n} \implies A^t = [a_{ji}]_{n \times m}$.|Luôn thực hiện được.|
|**Lũy thừa** (Powers)|$A^n = A \cdot A \cdot \ldots \cdot A$ ($n$ lần). Quy ước $A^0 = I$ (ma trận đơn vị).|Chỉ áp dụng cho ma trận vuông ($m=n$).|

**Tính chất chuyển vị quan trọng:** $(A + B)^t = A^t + B^t$ và **$(AB)^t = B^t A^t$**.

### 1.3. Hạng của Ma Trận (Rank of Matrix)

**Khái niệm:** Hạng của ma trận $A$, ký hiệu là $r(A)$, là số dòng khác không của ma trận bậc thang thu được từ $A$ thông qua các phép biến đổi sơ cấp dòng (BĐSC).

**Cách tìm hạng:**

1. **Sử dụng BĐSC** để đưa ma trận $A$ về dạng bậc thang (dòng).
    - Các phép BĐSC bao gồm: Đổi chỗ hai dòng ($d_i \leftrightarrow d_j$), Nhân một dòng với số $\alpha \ne 0$ ($d_i \rightarrow \alpha \cdot d_i$), Thêm vào một dòng một bội của dòng khác ($d_i \rightarrow d_i + \alpha \cdot d_j$).
2. **Đếm** số dòng khác không của ma trận bậc thang thu được. **Điều kiện:** Nếu $A$ là ma trận cấp $m \times n$, thì $0 \le r(A) \le \min(m, n)$.

## 2. Định Thức (Determinants)

Định thức (detA) chỉ được xác định cho ma trận vuông.

### 2.1. Công thức Tính Định Thức

|Cấp ma trận|Công thức|
|:--|:--|
|**Cấp 2**|$A = \begin{pmatrix} a_{11} & a_{12} \ a_{21} & a_{22} \end{pmatrix} \implies \det A = a_{11}a_{22} - a_{21}a_{12}$.|
|**Cấp 3** (Quy tắc Sarrus)|$\det A = a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{31}a_{22}a_{13} - a_{32}a_{23}a_{11} - a_{33}a_{21}a_{12}$.|
|**Cấp $n$** (Khai triển Laplace)|Khai triển theo dòng $i$: $\det A = \sum_{j=1}^{n} a_{ij} A_{ij}$.Khai triển theo cột $j$: $\det A = \sum_{i=1}^{n} a_{ij} A_{ij}$.|

Trong đó, **Phần bù đại số** (Algebraic Complement) $A_{ij}$ được xác định bởi: $$ A_{ij} = (-1)^{i+j} D_{ij} $$ $D_{ij}$ là định thức của ma trận thu được bằng cách xóa dòng $i$ và cột $j$ của $A$.

### 2.2. Tính Chất Quan Trọng

- **Chuyển vị:** $\det A = \det(A^t)$.
- **Tích:** $\det(AB) = \det A \cdot \det B$. Hệ quả: $\det(A^k) = (\det A)^k$.
- **Ma trận Tam giác/Chéo:** Định thức bằng tích các phần tử trên đường chéo chính: $\det A = a_{11}a_{22} \ldots a_{nn}$.
- **Biến đổi sơ cấp:**
    - Đổi chỗ hai dòng/cột: $\det A$ đổi dấu.
    - Nhân một dòng/cột với số $\alpha$: $\det A$ nhân với $\alpha$.
    - Cộng bội một dòng/cột vào dòng/cột khác: $\det A$ không thay đổi.

**Phương pháp tính định thức:**

1. **Dùng BĐSC** đưa ma trận về dạng tam giác (trên) (phương pháp Gauss).
2. **Dùng công thức Laplace** (khai triển) theo dòng/cột có nhiều số 0.

## 3. Ma Trận Khả Nghịch (Inverse Matrix)

### 3.1. Điều kiện Khả nghịch

Ma trận vuông $A$ cấp $n$ **khả nghịch** khi và chỉ khi: $$ \det A \ne 0 \quad \text{hoặc} \quad \text{rank}(A) = n $$ Nếu $A$ khả nghịch, ma trận nghịch đảo $A^{-1}$ là duy nhất và thỏa mãn $A A^{-1} = A^{-1} A = I$.

### 3.2. Thuật toán tìm Ma trận Nghịch đảo

**a) Dùng Định thức và Ma trận Phụ hợp:**

1. Tính $D = \det A$. Nếu $D=0$, $A$ không khả nghịch.
2. Tìm ma trận phụ hợp $P_A = [A_{ij}]_{n \times n}$. $A_{ij}$ là phần bù đại số của $a_{ij}$.
3. Tính ma trận nghịch đảo $A^{-1}$ bằng công thức: $$ A^{-1} = \frac{1}{D} P_A^t $$ Trong đó $P_A^t$ là ma trận chuyển vị của ma trận phụ hợp $P_A$.

**b) Dùng Phép Biến đổi Sơ cấp (Gauss-Jordan):**

1. Lập ma trận mở rộng $[A | I]$ (ghép $A$ với ma trận đơn vị $I$ cùng cấp).
2. Dùng BĐSC trên các dòng của $[A | I]$ để đưa $A$ về dạng $I$: $$ [A | I] \xrightarrow{\text{BĐSC}} [I | B] $$
3. Nếu biến đổi được, $A$ khả nghịch và **$A^{-1} = B$**. Nếu trong quá trình biến đổi xuất hiện dòng không ở ma trận bên trái, $A$ không khả nghịch.

## 4. Hệ Phương Trình Tuyến Tính (System of Linear Equations)

### 4.1. Dạng Ma trận và Điều kiện Nghiệm

Hệ phương trình tuyến tính (PTTT) có dạng ma trận: $$ AX = B $$ Trong đó $A$ là ma trận hệ số, $X$ là cột ẩn số, $B$ là cột hệ số tự do. Ma trận bổ sung (ma trận mở rộng) là $[A | B]$.

**Định lý Kronecker–Capelli** (Điều kiện có nghiệm): Hệ PTTT $AX = B$ có nghiệm khi và chỉ khi hạng của ma trận hệ số bằng hạng của ma trận mở rộng: $$ \text{rank}(A) = \text{rank}([A|B]) $$

**Phân loại nghiệm** (Đặt $r = \text{rank}(A) = \text{rank}([A|B])$ và $n$ là số ẩn):

- **Vô nghiệm:** $\text{rank}(A) < \text{rank}([A|B])$.
- **Nghiệm duy nhất:** $r = n$.
- **Vô số nghiệm:** $r < n$. Nghiệm phụ thuộc $n - r$ tham số tùy ý (ẩn tự do).

### 4.2. Giải Hệ Cramer (Cramer's Rule)

**Hệ Cramer** là hệ vuông ($m=n$) có ma trận hệ số $A$ khả nghịch ($\det A \ne 0$). Hệ Cramer có nghiệm duy nhất cho bởi công thức: $$ x_j = \frac{\det A_j}{\det A}, \quad (j = 1, 2, \dots, n) $$ Trong đó $D = \det A \ne 0$, và $A_j$ là ma trận thu được từ $A$ bằng cách thay cột $j$ bằng cột tự do $B$.

### 4.3. Phương Pháp Gauss (Giải Hệ PTTT Tổng Quát)

Phương pháp này sử dụng BĐSC trên ma trận mở rộng để khử ẩn số.

1. **Lập ma trận mở rộng** $[A | B]$.
2. **BĐSC** để đưa $[A | B]$ về dạng bậc thang $[A' | B']$.
3. **Kiểm tra điều kiện có nghiệm** (Kronecker–Capelli).
4. **Xác định ẩn chính** (ẩn ứng với hệ số khác 0 đầu tiên trên mỗi dòng bậc thang) và **ẩn tự do** (các ẩn còn lại).
5. **Giải hệ mới** (tương đương với hệ cũ) bằng cách thế dần từ phương trình cuối lên phương trình đầu.

### 4.4. Hệ Phương Trình Tuyến Tính Thuần Nhất (Homogeneous System)

Hệ có dạng $AX = O$ (cột tự do bằng 0).

**Điều kiện có nghiệm không tầm thường:**

1. Hệ thuần nhất luôn có nghiệm tầm thường $X=O$.
2. Hệ có **nghiệm không tầm thường** (vô số nghiệm) khi và chỉ khi: $$ \text{rank}(A) < n \quad (\text{số ẩn}) $$
3. Nếu $A$ là ma trận vuông, hệ có nghiệm không tầm thường khi và chỉ khi $\det A = 0$.

**Mối liên hệ giữa hệ tổng quát và hệ thuần nhất**: Nghiệm tổng quát của hệ tổng quát $AX = B$ là tổng của một nghiệm riêng $X_r$ của nó với nghiệm tổng quát $X_{tn}$ của hệ thuần nhất tương ứng $AX = O$: $$ X_{tq} = X_r + X_{tn} $$
________________________________________________________________________
Link: "[[Bồi dưỡng]]"