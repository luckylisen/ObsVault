流程：
1. 安裝 PHP
   xampp
### 安裝 Composer 
   https://getcomposer.org/
   
### 創建 laravel 專案目錄

   
1. 確認安裝正確
   php artisan serve
   


打開檔案管理員
進入網站目錄(
在目錄中鼠標右鍵：Open Git Bash Hear 
輸入創建新專案指令：如下

1. 打開檔案總管
2. 進入專案目錄：C:/xampp/htdocs/laravel/
3. 鼠標右鍵開啟：Open Git Bash Hear 
4. 訪問laravel官網：https://laravel.com/docs/10.x/installation
5. 複製代碼：Creating a Laravel Project
```
composer create-project "laravel/laravel:^10.0" rcsmplr-app
```
6. 修改版本與專案名稱
```
composer create-project "laravel/laravel:^10.0" rcsmplr-app
composer create-project "laravel/laravel:^12.0" project01
// 版本：12.0
// 目錄：project01
```
7. 
進入專案目錄
```
$ ls   // dir當前目錄
$ cd project01  // 進入子目錄
$ php artisan // 測試連線 
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



route(路由) = 帶位服務員
櫃檯：routes / web.php
Ctrl+P -> web.php
包廂：resources / views / 123.blade.php

laravel routing：
https://laravel.com/docs/12.x/routing


laravel helper dd
https://laravel.com/docs/12.x/helpers#method-dd

```
// 路徑：routes > home0114 > web.php
<?php
use Illuminate\Support\Facades\Route;

Route::get('/sum/{num}', function (string $num) {
    // dd($num);
    $sum = 0;
    for($i=1; $i<=$num; $i++){
        $sum += $i;
    };
    dd($sum);
    // return 'sum '.$num;
});

// URL：http://localhost/sum/2
3 // routes\web.php:11
```

從 GitHub 還原 Laravel 套件：
https://stackoverflow.com/questions/38602321/cloning-laravel-project-from-github
1. Run `git clone 'link projer github'`
2. Run `composer install`
3. Run `cp .env.example .env`  // Linux
   或 `copy .env.example .env`  // Windows 
4. Run `php artisan key:generate`
5. phpmyadmin：創建資料庫[laravel_260114]
   vscode：設定資料庫[env 23~28行]
```
	DB_CONNECTION=mysql  [*修改*]
	DB_HOST=127.0.0.1
	DB_PORT=3306
	DB_DATABASE=lavravel_260114  [*添加*]
	DB_USERNAME=root
	DB_PASSWORD=
```
   Run `php artisan migrate`
   
6. php artisan migrate
7. Run `php artisan db:seed`
8. Run `php artisan serve`
9. Go to link [localhost:8000] 

route > controller > view
```
// 複製代碼：
// https://laravel.com/docs/12.x/controllers */
use App\Http\Controllers\UserController;
Route::get('/user/{id}', [UserController::class, 'show']);

// 修改
use App\Http\Controllers\CarController;
Route::get('car', [CarController::class, 'index']);

```