0. MCV 框架：
```
櫃檯：routes / web.php
橋樑：app / Http / Controller.php
包廂：resources / views / 123.blade.php
// route = 路由 = 帶位員
```

1. 複製指令：
   官網 https://laravel.com/docs/12.x/controllers
   搜索 Basic Controllers
```
// 筆記本修改備查
php artisan make:controller UserController
php artisan make:controller CarController
```

2. 執行指令：
```php
// 終端機執行，建立控制器
php artisan make:controller CarController
// 執行後：獲得控制器文件

```

3. 獲得文件：
   app / Http / Controllers / CarController.php
```php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class CarController extends Controller
{
    // ......
}
```

5. 複製代碼：
   官網 https://laravel.com/docs/12.x/controllers
   搜索 Single Action Controllers
```
use App\Http\Controllers\UserController;
Route::get('/user/{id}', [UserController::class, 'show']);
```

4. 編輯文件：
   routes / web.php：
```php
<?php
use Illuminate\Support\Facades\Route;

// use App\Http\Controllers\UserController;
// Route::get('/user/{id}', [UserController::class, 'show']);

use App\Http\Controllers\CarController;
Route::get('cars', [CarController::class, 'index']);

Route::get('/', function () {
    return view('welcome');
});
```

5. 編輯文件：
   app / Http / Controllers / CarController.php：
```php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class CarController extends Controller
{
    /* ===== 新增開始 ===== */
    public function index(){
        dd('Carcontroller index ok');
        return "List of cars";
    } 
    /* ===== 新增結束 ===== */
}
```

6. 確認結果：
   [瀏覽器] http://localhost/cars
```php
[代碼呈現]
"Carcontroller index ok" // app\Http\Controllers\CarController.php:10
```

7. 變更路徑：
   目錄：views\ car_view \
   文件：views\ car_view \ index.blade.php
```html
<html>
    Hello Cars View!
</html>
```

8. 修改路徑：
   app \ Http \ Controllers \ CarControlle.php
```php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class CarController extends Controller
{
    public function index(){
        dd('Carcontroller index ok');
        // return "List of cars";
        // ===== 變更路徑 =====
        // 對應 view/car_view/index.blade.php
        return view('car_view.index');   
    }    
}
```

9. 確認結果：
   [瀏覽器] http://localhost/cars
```
[HTML呈現]
Hello Cars View!
```