
[foreach 迴圈]
```
foreach ($array as $value) {
    ********
}
```
==語義：從陣列[$Array]中逐一取出元素，暫存於變數[$value]中，放入 {......} 中執行。

[傳統 for 迴圈] 
```
for ($i=1; $i<=count($colors); $i++) {
	echo "顏色是".$colors[$i]; 
}
```

[foreach 遍歷鍵+值]
```
foreach ($array as $index => $value) {
	echo "第 $index 個顏色是：$value";
}
```

- **有了 `$value`：** 你可以把變數命名為更具意義的名字。
    - `foreach ($users as $user)` （處理每一個使用者）
    - `foreach ($orders as $price)` （處理每一筆訂單價格）
    - 程式碼讀起來是「**對於這個陣列裡的每一個元素，做這件事**」。