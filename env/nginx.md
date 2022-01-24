# Nginx

### 安装相关的编译工具

```shell
yum -y install make zlib zlib-devel gcc-c++ libtool openssl openssl-devel
```

### 安装pcre

访问[pcre](http://downloads.sourceforge.net/project/pcre/pcre)获取需要的版本号，如8.45，修改下方链接中的版本

```shell
cd /usr/local/src
wget http://downloads.sourceforge.net/project/pcre/pcre/8.45/pcre-8.45.tar.gz
# 下载后解压
tar zxvf pcre-8.45.tar.gz
cd pcre-8.45.tar.gz
# 编译安装
./configure
make && make install
```

### 安装Nginx

访问[Nginx](https://nginx.org/en/download.html)获取需要的版本号，如1.20.2，修改下方链接中的版本

```shell
cd /usr/local/src
wget http://nginx.org/download/nginx-1.20.2.tar.gz
# 下载后解压
tar zxvf nginx-1.20.2.tar.gz
cd nginx-1.20.2.tar.gz
# 编译安装
./configure --prefix=/usr/local/nginx --with-http_ssl_module --with-pcre=/usr/local/src/pcre-8.45
make && make install
```

> 参数说明：
>
> - --prefix  将所有可执行文件、库文件和配置文件放在配置的此目录中
>
> - --with-http_ssl_module  安装http ssl模块，支持ssl协议，提供https服务
>
> - --with-pcre  指定使用上一步中安装的pcre库解析
