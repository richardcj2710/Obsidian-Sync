### Sorts:
---
##### 1. Bubble sort ($O(n^2)$):
	Hoạt động bằng cách hoán đổi liên tiếp các phần tử liền kề nếu chúng sai thứ tự.
	```
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
```
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
```
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
```
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
### Searchs
##### 1. Tìm kiếm Tuyến tính (Linear Search)

Đây là cách thô sơ nhất: Đi qua từng phần tử từ đầu đến cuối cho đến khi tìm thấy thứ mình cần.

- **Điều kiện:** Dữ liệu không cần sắp xếp.
- **Độ phức tạp:** $O(n)$.
- **Khi nào dùng:** Khi mảng nhỏ hoặc dữ liệu chưa được sắp xếp.
```
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
```
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