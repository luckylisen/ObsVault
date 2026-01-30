```php
<?php

/* 設定資料庫連線 */
$dsn='mysql:host=localhost;dbname=my_dbase;charset=utf8mb4';

/* 開啟錯誤拋出模式 */
/* 撈取模式為關聯陣列 */
/* 防止資料庫注入攻擊 */
$opt=[
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES => false, 
];

/* 建立PDO連線 */
try{
    $pdo=new PDO($dsn,"root","",$opt);    
}catch(\PDOException $e) {
    // 將訊息寫入指定日誌文件(db_error.log)
    // 代表寫入檔案，後面接檔案路徑
    error_log("連線錯誤: " . $e->getMessage(), 3, "db_error.log");
    die("無法連線！");
}
    
/* 讀取資料表 */
try{
    $sql="SELECT * FROM my_table";
    $stmt=$pdo->query($sql);
}catch(\PDOException $e) {
    error_log("讀取錯誤: " . $e->getMessage(), 3, "db_error.log");
    die("無法讀取！");
}


?>
```