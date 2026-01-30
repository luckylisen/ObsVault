1. 安裝 Composer：
   https://getcomposer.org/
   
2. 訪問官網：
   https://laravel.com/docs/10.x/installation
   
3. 複製指令：
```
composer create-project "laravel/laravel:^10.0" rcsmplr-app
```

4. 修改指令：
```
composer create-project "laravel/laravel:^10.0" rcsmplr-app
// 版本：12.0
// 目錄：laravel_0115
composer create-project "laravel/laravel:^12.0" laravel_0115
```

5. 進入根目錄：
   C:/xampp/htdocs/laravel
   
6. 右鍵開終端：
   Open Git Bash Hear
   
7. 執行指令：
```
composer create-project "laravel/laravel:^12.0" laravel_0115
// 如果執行報錯可能是xampp安裝路徑不在c:\
// 參考底部錯誤排除法
```

8. 修改路徑：
    [XAMPP] httpd.cof
```
#Laravel 練習 
DocumentRoot "F:\Repository\akai0910\laravel\home0115\public"
<Directory "F:\Repository\akai0910\laravel\home0115\public">
```

9. 重啟apache： 
   
10. 確認結果：
```
[終端機] 
$ ls                     // 查看當前目錄
$ cd home0115  // 進入專案目錄
$ ls                     // 查看專案目錄
$ php artisan      // 測試連線 
$ php artisan serve

[瀏覽器]
http://localhost:8000
```
----------

[錯誤1：php: command not found]

執行安裝命令(7) 出現誤訊息(php: command not found)：這個錯誤訊息顯示你的系統找不到 PHP 執行檔，導致 Composer 無法執行。可能是 xampp 未安裝在默認路徑( c:\ )下，導致 composer 找不到 xampp/php。 
```
// 執行命令
$ composer create-project "laravel/laravel:^12.0" laravel_0121
// 錯誤訊息
which: no php in (/c/Users/User/bin:/mingw64/.....dor/bin:/usr/bin/vendor_perl:/usr/bin/core_perl)
/c/composer/composer: line 14: php: command not found
```

1. 查詢 php 與 composer 版本，確認連線正確。
```
php -v
composer -v
```

2. 檢查 xampp/php 的正確路徑
   
3. 修正 Windows 環境變數 (PATH)
   - 在 Windows 搜尋列輸入 **「編輯系統環境變數」**
   - 點擊 **「環境變數」** 按鈕
   - 在「系統變數」清單中找到 **`Path`**，點擊「編輯」
   - 檢查是否有 `C:\xampp\php`，編輯路徑後保持
   - 將 `C:\xampp\php` 移到清單的最頂端，避免被其他軟體干擾
   - 確認 `C:\composer` (或你安裝 Composer 的路徑) 也在 Path 中
     
2. 清緩存重啟 git bash，重新執行安裝命令
   
3. **參考對話(kinfly885)：**
   https://gemini.google.com/app/72bb7153769a3e8e
