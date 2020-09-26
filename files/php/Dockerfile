FROM php:fpm

# set timezome
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

COPY zhongkeda.list /etc/apt/sources.list

# 更新安装依赖包和PHP核心拓展
RUN apt-get update && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libzip-dev curl \
        && rm -r /var/lib/apt/lists/* \
        && docker-php-ext-configure gd --with-freetype --with-jpeg \
        && docker-php-ext-install -j$(nproc) gd zip opcache pdo_mysql gettext sockets opcache mysqli

# 安装 PECL 拓展，安装Redis，swoole
RUN pecl install redis \
    && pecl install swoole \
    && docker-php-ext-enable redis swoole

WORKDIR /data

# Write Permission
RUN usermod -u 1000 www-data
