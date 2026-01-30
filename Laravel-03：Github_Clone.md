從 GitHub 還原 Laravel 套件：
https://stackoverflow.com/questions/38602321/cloning-laravel-project-from-github
1. Run `git clone 'link projer github'`
2. Run `composer install`
3. Run `cp .env.example .env`  // Linux
   或 `copy .env.example .env`  // Windows 
4. Run `php artisan key:generate`
5. phpmyadmin：創建資料庫[laravel_260114]
   vscode：設定資料庫[env 23~28行]
```c
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
8. 確認結果