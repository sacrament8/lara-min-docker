## Start Up
```
$ git clone git@github.com:sacrament8/lara-min-docker.git
$ cd lara-min-docker
$ mikdir server
$ docker-compose build
$ docker-compose up -d
$ docker exec -it lara-min-app laravel new
```

## すでにイメージ、コンテナがあって起動できない場合
```
$ docker stop $(docker ps -q) && docker rm $(docker ps -q -a) && docker rmi $(docker images -q)
```

## Migration
- .envを書き換え
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=database
DB_USERNAME=root
DB_PASSWORD=root
```
- migrateを実行
```
$ docker exec -it lara-min-app php artisan migrate:fresh --seed
```
- migrateに失敗するなら
```
$ docker exec -it lara-min-app composer dump-autoload
```

## Access To PHPMYADMIN
- localhost:8888にアクセス

## Access To APP
```
$ docker exec -it lara-min-app php artisan serve
```
- localhost:8080portアクセス
- user_name: root
- password: root

```
|*****************************************|
|********** ENJOY DEVELOPMENT !! *********|
|*****************************************|
```