流程：
1. 安裝 PHP
   xampp
### 安裝 Composer 
   https://getcomposer.org/
   
### 創建 laravel 專案目錄

   
1. 確認安裝正確
   php artisan serve
   

https://laravel.com/docs/10.x/installation
打開檔案管理員
進入網站根目錄(C:/xampp/htdocs)
鼠標右鍵(Open Git Bash Hear) 
創建新專案(Composer create-projec)

```
composer create-project "laravel/laravel:^12.0" project01
// 版本：12.0
// 目錄：project01
```

進入專案目錄
```
$ ls   [顯示當前目錄]
$ cd project01  [進入子目錄]
// ls = 顯示根目錄
// cd = 進入專案目錄
```

執行php artisan
```
$ php artisan serve
```

查看是否成功
```
http://localhost:8000
// 瀏覽器確認
```




櫃檯：routes / web.php
Ctrl+P -> web.php
包廂：resources / views / 123.blade.php