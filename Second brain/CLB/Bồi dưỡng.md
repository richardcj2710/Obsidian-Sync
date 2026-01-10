




**ISP (nhà cung cấp mạng) -> Modem (bộ điều chế tín hiệu điện từ) -> ...**

	LAN -> Switch (Bộ chuyển mạch)
	WLAN -> Access point (AP/ Điểm truy cập không dây)
	WAN -> Router (Bộ định tuyến)


**IP/ MAC**

	IP chỉ là duy nhất khi nó tham gia tại thời điểm đó
	MAC là luôn luôn duy nhất để gán cho các bộ giao tiếp mạng

________________________________________________________________________
# Lập trình

```
s = int(input()) # nhập số
s1 = input()     # kết quả sẽ là một xâu "<string>"
"""
Đếm xâu:

Python str
↑↑↑↑↑↑↑↑↑↑
0123456789 | hoặc
-8 -7 -6 -5 -4 -3 -2 -1

s = "" # sâu rỗng -> len = 0
" "    # sâu có độ dài bằng 1 -> len = 1
"""

print(s[1:9:2]) #:2 là bước nhảy

# Nếu bước nhảy là dương: trái -> phải
# Nếu bước nhảy âm: phải -> trái

print(::-2) # đảo ngược chuỗi
```


# Các hàm
```
len() # đếm độ dài hàm
<str>.count("<entry>,<vị trí đầu trong chuỗi>, <vị trí cuối>")
	-> 
index() # same count


# replace 
<str>.replace(str_old, str_new, [count])
# tách
<str>.split(str, num)

# map
a,b = map(int/float, input().split())

# join: nối
```

# Cách duyệt
```
s = 'python'
# cách 1
d = 0
for i in s:
	print(i)
	if i = 'o': d += 1
	print(d)

# cách 2 dùng tốt nhất
for i in range(len(s)):
	print(i)
	if s[i] = 'o' : d += 1
```