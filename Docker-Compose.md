# Docker-Compose

可以通过一个 docker-compose.yml 维护容器

1. github 下载 Compose
2.  放到服务器上
3. 赋予权限 chmod 777 <name>
4. 使用 docker-Compose

## 官方文档

```
docs.docker.com
```

## 例子

```
version:'3.8'		# docker版本
services:
  mysql:		# 服务器的名称
    restart: always			# 只要docker启动,容器一起启动
    image: daocloud.io/library/mysql:5.7.4			# 指定镜像路径
    container_name: mysql		# 指定容器name
    ports:
      - 3306:3306		# 指定端口号的映射
    environment:
      MYSQL_ROOT_PASSWORD: 123456			# 指定MySQL的ROOT用户的登录密码
    volumes:
      - /usr/bin/:/var/lib/mysql			# 映射数据卷
  mysql2:
  	...

```

## 命令管理容器

开启容器

```
docker-compose up -d
```

重启

```
docker-compose restart
```

关闭容器

```
docker-compose stop
```

关闭并删除容器

```
docker-compose down
```

查看容器

```
docker-compose ps
```

## docker-compose 结合 dockerfile

```
# yml 文件
version:'3.8'		
services:
  mysql:		
    restart: always		
    build:										# 构建自定义镜像
      context: ../								# 指定dockerfile 文件路径
      dockerfile: Dockerfile					# 指定dockerfile 文件名称
    image: mysql:1.0							# 重命名
    container_name: mysql		
    ports:
      - 3306:3306		
    environment:
      MYSQL_ROOT_PASSWORD: 123456			
    volumes:
      - /usr/bin/:/var/lib/mysql			
```

dockerfile 文件

```
from ...
copy mysql ...
```

