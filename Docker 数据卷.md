# Docker 数据卷

数据卷: 将宿主机的一个目录,映射到容器的一个目录中,可以在宿主机操作目录时,容易内映射的文件,也会一期变化.

## 创建数据卷

```
docker volume create <name>
# 创建数据卷之后,默认会存放在一个目录下 /var/lib/docker/volumes/<name>/_data
```

## 查看数据卷的详细信息

```
docker volume inspect <name>
```

## 查看所有数据卷

```
docker volume ls
```

## 删除数据卷

```
docker volume rm <name>
```

## 使用数据卷

```
docker run -v 数据卷名称:容器内部的路径 镜像id
# 举例子
docker run -d -p 8080:8080 -v v1:/user/local/ --name <name> id

# 方法二(常用)
docker run -v 路径:容器内部的路径 镜像id
# 举例子(映射的文件夹为空)
docker run -d -p 8080:8080 -v /home/local:/user/local/ --name <name> id
```

