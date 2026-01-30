
PDOExceptio：精準攔截(限資料庫連線與存取錯誤) 
Throwable：全能攔截(包含資料庫的所有錯誤)

```php
<?php

try{ 
	 /*..........*/   
} catch (\PDOException $e) {
    // PDOExceptio
    // 精準攔截(限資料庫連線與存取錯誤) 
    // errorMessage
    // 格式化錯誤訊息(時間、訊息、檔案位置、行號)
    $errorMessage = " | 時間: " . date('Y-m-d H:i:s') .
                    " | 錯誤: " . $e->getMessage() . 
                    " | 檔案: " . $e->getFile() . 
                    " | 行號: " . $e->getLine() . PHP_EOL;

    // 3=發送到指定的文件(參數三)
    // 1=發送到指定的信箱(參數三)
    // 0=發送到系統日誌(php.ini決定)
    error_log($errorMessage, 3, 'db_error.log');

    // 對外顯示(模糊即可)
    die("系統異常！");
    
} catch (\Throwable $e) {
    // Throwable
    // 全能攔截(包含資料庫的所有錯誤)
    $errorMessage = " | 時間: " . date('Y-m-d H:i:s') .
                    " | 錯誤: " . $e->getMessage() . 
                    " | 檔案: " . $e->getFile() . 
                    " | 行號: " . $e->getLine() . PHP_EOL;
    error_log($errorMessage, 3, 'db_error.log');
    die("系統異常！");    
}

?>
```