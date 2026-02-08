### Sorts:
---
1. Bubble sort ($O(n^2)$):
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
3. Quick Sort ($O(n log(n)$):
	```
	```
---
4. Merge Sort ($O(n log(n)$):