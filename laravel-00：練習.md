laravel routing：
https://laravel.com/docs/12.x/routing
laravel helper dd
https://laravel.com/docs/12.x/helpers#method-dd

```php
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



composer create-project "laravel/laravel:^10.0" example-app
composer create-project "laravel/laravel:^12.0" laravel_0121