
![[Pasted image 20251003094240.png]]

默認情況下，瀏覽器中輸入 localhost 只可訪問 index.html。如果沒有 index.html，則顯示根目錄下全部文件與目錄。 
![[Pasted image 20251003094851.png]]

刪除 httpd.conf 文件中 “Indexes” 字樣，當根目錄中沒有 Index.html 文件時，整個目錄將被拒絕訪問。
![[Pasted image 20251003095835.png]]