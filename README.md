# docker-laravel

Laravel用のdocker

## バージョン
- nginx - 1.17.2
- php - 7.2.21
- mysql - 8.0.17
- Laravel - 5.8.30

## 動かし方
`docker-compose up -d`

`docker-compose exec app bash`

`cd laravel-app`

`php artisan migrate`

## 気になる
- laravelのmigrateが動かない
  - user ではなく root なら動く
  - 認証方式をcaching_sha2_passwordからmysql_native_passwordに変更した。
```mysql
ALTER USER 'ここを変えたいユーザー名に'@'%' IDENTIFIED WITH mysql_native_password BY 'secret';
```