### Sorts:

1. Bubble sort ($O(n^2)$):
---
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
2. Insertion Sort($O(n^2)$):
	
3. Quick Sort ($O(n log(n)$):
4. Merge Sort ($O(n log(n)$):