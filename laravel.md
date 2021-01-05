---
title: Laravel Note
tags: laravel, note
description: View the slide with "Slide Mode".
---

# laravel 筆記
<!-- [TOC] -->
## 重新建立Git上 laravel project
**1. 第一步 clone 專案**
```
git clone https://github.com/username/someproject ProjectName
```
**2.還原 composer.json** 
```
composer install
```
註：須事先安裝安裝 [composer](https://getcomposer.org/)

**3. 還原 packages.json**
```
npm install
```
註：須事先安裝 npm

**4. 複製 .env.example .env**
```
cp .env.example .env
```
**5. 修改 .env 檔內的設定，例如：**
```
...
DB_DATABASE=YourDatabase
DB_USERNAME=YourUserName
DB_PASSWORD=YourPassword
...
```
**6. 取得 APP_KEY**
```
php artisan key:generate
```
**7. 建立資料庫**
```php
//資料庫不存在，直接使用此指令
php artisan migrate --seed
//資料庫已存在，可以加上 :refresh 刷掉
php artisan migrate:refresh --seed
```
**8. 啟動服務**
```php
php artisan serve --port=8000
```



## 資料庫遷移
* **新建類別(class not found)**
```
composer dump-autoload -o
```
* **建立遷移**
```
php artisan make:migration create_users_table
php artisan make:migration create_users_table --create=users
```
* **建立遷移(新增欄位)** 
```
php artisan make:migration add_votes_to_users_table --table=users
```
* **執行遷移**
```
php artisan migrate
```
* **還原遷移(上一個)**
```
php artisan migrate:rollback
```
* **還原遷移(所有)**
```
php artisan migrate:reset
```
* **還原或執行遷移** 
```
php artisan migrate:refresh
php artisan migrate:refresh --seed
```
* **建立Resource Controller** 
```
php artisan make:controller DataController --resource
```
* **新增model** 
```
php artisan make:model Post
```

## 資料庫: 資料填充
* **新增資料填充** 
```
php artisan make:seeder UsersTableSeeder
```
* **執行資料填充** 
```
php artisan db:seed        
php artisan db:seed --class=UserTableSeeder
```
* **重建資料庫並進行填充** 
```
php artisan migrate:refresh --seed
```
* **使用指令清除快取** 
```
php artisan cache:clear  
php artisan config:cache 
php artisan config:clear
php artisan view:clear
php artisan route:clear
```
## 常用指令
* **檢視目前的 Laravel 版本** 
```
php artisan --version
```

## RESTful 資源控制器

Artisan 指令快速建立
https://laravel.tw/docs/5.2/controllers