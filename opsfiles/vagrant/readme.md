# How to Use

### 目的

product-api

### 構築方法

+ Mac上での準備(PHPは導入済み)

```
### clone
$ git clone git@github.com:Nature-Cue/aszoo-product-api.git
$ cd aszoo-product-api

### composer周りのupdate
$ sudo mkdir -p  /var/log/laravel/bootstrap/cache
$ sudo chmod 777 /var/log/laravel/bootstrap/cache
$ php composer.phar install
```

+ vagrant環境構築

```
$ cd opsfiles/vagrant
$ vagrant up
```

下記にアクセスする。

+ TOPページ

http://192.168.33.101

+ PHPチェックページ

http://192.168.33.101/chkpage/index.php


### migration

```
### webサーバに入る(Mac)
$ cd opsfiles/vagrant
$ vagrant ssh web


### webサーバ上(※ コマンドライン限定)
$ cd /develop/aszoo-product-api/
$ export APP_ENV="development"
$ php artisan migrate:refresh --seed
```

### vagrantがうまく動かない場合

```
### PHPのビルトインサーバを立ち上げ(Mac上にて)
$ php -S 0.0.0.0:8080 -t public
```

上記をコマンド後、下記にアクセスする。

http://0.0.0.0:8080


### 環境メモ

+ version確認方法
    + OS
    ```
    $ cat /etc/redhat-release
    ```

    + php
    ```
    $ php --version
    ```

    + nginx
    ```
    $ nginx -v
    ```

    + mysql
    ```
    $ mysql --version
    ```

    + laravel
    ```
    $ php artisan --version
    ```



+ nginx_log
    + `/var/log/nginx/`

+ php(laravel)_log
    + `/var/log/laravel/`
