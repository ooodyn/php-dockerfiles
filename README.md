# php-dockerfiles
docker php开发环境

基于 [zPhal-dockerfiles](https://github.com/goozp/zPhal-dockerfiles) 修改

# 简介
相关软件皆未指定版本，适合折腾。

构建时的相关软件版本：
- PHP 7.4.10
- MySQL 8.0.21
- Nginx 1.19.2
- Redis 6.0.8

PHP扩展：
- redis 5.3.1
- swoole 4.5.4

# 使用
###  1.修改本地开发目录
修改docker-compose.yml中映射到php-fpm及nginx镜像下/data/www的本地目录

### 2.docker-compose 构建项目
进入 docker-compose.yml 所在目录： 执行命令：
```docker-compose up -d```