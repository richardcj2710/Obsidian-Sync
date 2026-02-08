### Sorts:
---
##### 1. Bubble sort ($O(n^2)$):
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