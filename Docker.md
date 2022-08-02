## 安装 Docker

```
更新 yum 包
yum update
构建最快缓存
yum makecache fast
安装最新版
yum install docker-ce
```

## 启动 docker

```
启动 docker
systemctl start docker
设置开机启动
systemctl enable docker
```

## 测试 docker

```
docker pull hello-world
docker images
```

## 卸载 docker

```
yum list installed | grep docker
yum - y remove 版本

```

