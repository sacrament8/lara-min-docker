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

## Access
```
$ docker exec -it lara-min-app php artisan serve
```
- localhostの8080portに接続

```
|*****************************************|
|********** ENJOY DEVELOPMENT !! *********|
|*****************************************|
```