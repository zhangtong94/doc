# Docker

### 设置docker存储库

```shell
yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

### 安装

```shell
yum install docker-ce docker-ce-cli containerd.io
```

### 启动

```shell
systemctl start docker
```



参考[官网](https://docs.docker.com/engine/install/centos/)相关内容
