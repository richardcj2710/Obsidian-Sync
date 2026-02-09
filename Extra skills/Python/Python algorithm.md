### <font color="#ff0000">Sorts:</font>
---
##### 1. Bubble sort ($O(n^2)$):
Hoạt động bằng cách *hoán đổi liên tiếp* các *phần tử liền kề* nếu chúng sai thứ tự.
```python title:Bubble_Sort.py
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr
```
---
##### 2. Insertion Sort($O(n^2)$):
Tương tự như cách bạn sắp xếp quân bài trên tay: lấy một phần tử và chèn nó vào đúng vị trí trong phần đã sắp xếp.
```python title:Insertion_Sort.py
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr
```
---
##### 3. Quick Sort ($O(n log(n)$):
Chọn một điểm chốt (pivot) và chia mảng thành hai phần: nhỏ hơn pivot và lớn hơn pivot.
```python title:Quick_Sort.py
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)
```
---
##### 4. Merge Sort ($O(n log(n)$):

Để cài đặt thuật toán này, chúng ta cần hai phần:
	1. **Hàm chia:** Chia mảng thành các mảng con cho đến khi mỗi mảng chỉ còn 1 phần tử.
	2. **Hàm trộn (Merge):** So sánh và gộp các mảng con lại theo thứ tự.
```python title:merge_sort.py
	def merge_sort(arr):
	    # Điều kiện dừng: Nếu mảng chỉ còn 1 phần tử hoặc trống
	    if len(arr) <= 1:
	        return arr
	
	    # 1. Chia mảng làm đôi
	    mid = len(arr) // 2
	    left_half = arr[:mid]
	    right_half = arr[mid:]
	
	    # Đệ quy chia tiếp các mảng con
	    left_half = merge_sort(left_half)
	    right_half = merge_sort(right_half)
	
	    # 2. Trộn hai nửa đã sắp xếp lại với nhau
	    return merge(left_half, right_half)
	
	def merge(left, right):
	    result = []
	    i = j = 0
	
	    # So sánh từng phần tử của hai mảng và thêm phần tử nhỏ hơn vào result
	    while i < len(left) and j < len(right):
	        if left[i] < right[j]:
	            result.append(left[i])
	            i += 1
	        else:
	            result.append(right[j])
	            j += 1
	
	    # Nếu còn phần tử thừa ở mảng left hoặc right thì thêm nốt vào
	    result.extend(left[i:])
	    result.extend(right[j:])
	    
	    return result
```
- **Độ phức tạp thời gian:** Luôn là $O(n \log n)$ trong mọi trường hợp (tốt nhất, trung bình, xấu nhất). Điều này giúp nó ổn định hơn Quick Sort trong một số tình huống dữ liệu cực đoan.
- **Tính ổn định (Stability):** Nó giữ nguyên thứ tự tương đối của các phần tử bằng nhau. Điều này rất quan trọng khi bạn sắp xếp các đối tượng phức tạp (ví dụ: sắp xếp danh sách sinh viên theo tên, sau đó theo tuổi).
- **Nhược điểm:** Nó cần thêm bộ nhớ để tạo các mảng tạm thời trong quá trình trộn, nên độ phức tạp không gian là $O(n)$.
---
### <font color="#ff0000">Searchs</font>
##### 1. Tìm kiếm Tuyến tính (Linear Search)

Đây là cách thô sơ nhất: Đi qua từng phần tử từ đầu đến cuối cho đến khi tìm thấy thứ mình cần.

- **Điều kiện:** Dữ liệu không cần sắp xếp.
- **Độ phức tạp:** $O(n)$.
- **Khi nào dùng:** Khi mảng nhỏ hoặc dữ liệu chưa được sắp xếp.
``` python title:Linear_search.py
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # Trả về vị trí tìm thấy
    return -1  # Không tìm thấy
```
---
##### 2. Tìm kiếm Nhị phân (Binary Search)

Đây là thuật toán "siêu nhanh". Thay vì xem từng cái, nó luôn kiểm tra phần tử ở giữa:

1. Nếu phần tử giữa là mục tiêu $\rightarrow$ Xong.
2. Nếu mục tiêu nhỏ hơn $\rightarrow$ Bỏ qua nửa bên phải, tìm ở nửa bên trái.
3. Nếu mục tiêu lớn hơn $\rightarrow$ Bỏ qua nửa bên trái, tìm ở nửa bên phải.

- **Điều kiện bắt buộc:** **Dữ liệu đã được sắp xếp.**
- **Độ phức tạp:** $O(\log n)$. (Cực nhanh, ví dụ với 1 tỷ phần tử, bạn chỉ mất tối đa ~30 lần kiểm tra).
``` python title:Binary_search.py 
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```
---
### <font color="#ff0000">Recursion</font>
1. Backtracking (Quay lui):

	1. Thuật toán tìm kiếm lời giải bằng cách xây dựng dần dần các ứng viên cho lời giải và loại bỏ các ứng viên không thỏa mãn ngay khi xác định được chúng không thể dẫn đến một lời giải hợp lệ.
	2. **Chọn:** Thử một lựa chọn.
	3. **Kiểm tra:** Lựa chọn này có vi phạm ràng buộc nào không?
	4. **Đi tiếp (Đệ quy):** Nếu ổn, lặp lại bước 1 cho lựa chọn tiếp theo.
	5. **Quay lui:** Nếu không ổn hoặc đã thử hết các nhánh, quay lại bước trước đó để thử lựa chọn khác.

	VD: Bài toán N-Queens (8 quân Hậu)
	
	``` python title:example_N-Queens.py
	def is_safe(board, row, col, n):
    # Kiểm tra cột này ở các hàng phía trước
    for i in range(row):
        if board[i] == col or \
           board[i] - i == col - row or \
           board[i] + i == col + row:
            return False
    return True

	def solve_queens(n, row, board, results):
	    # Nếu đã đặt xong hậu ở tất cả các hàng
	    if row == n:
	        results.append(board[:])
	        return
	
	    for col in range(n):
	        if is_safe(board, row, col, n):
	            board[row] = col          # Bước chọn
	            solve_queens(n, row + 1, board, results)  # Đi tiếp
	            # Bước quay lui thực chất nằm ở việc vòng lặp tiếp tục 
	            # và ghi đè giá trị board[row] ở lần lặp sau.
	
	def print_board(result, n):
	    for row in result:
	        line = ["Q" if i == row else "." for i in range(n)]
	        print(" ".join(line))
	    print("\n")
	
	# Chạy thử với bàn cờ 4x4
	n = 4
	results = []
	solve_queens(n, 0, [0]*n, results)
	
	print(f"Tìm thấy {len(results)} cách xếp:")
	for res in results:
	    print_board(res, n)
	```
---
2. 