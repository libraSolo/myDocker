# Docker 容器操作

## 运行容器

```
docker run <标识>[:tag]
```

**常用参数**

```
docker run -d -p宿主机端口:容器端口 --name 容器名称 镜像的标识镜像名称[:tag]
-d: 后台运行
-p宿主机端口:容器端口: 为了映射当前Linux的端口和容器的端口
--name 容器名称: 指定容器的名称
```

## 查看正在运行的容器

```
docker ps [-qa]
-a: 查看全部容器,包括没有运行的
-p:之查看容器的标识
```

## 查看容器的日志

```
docker logs -f 容器ID
-f 可以滚动查看日志的最后几行
```

## 进入容器

```
docker exec -it 容器ID bash
```

## 删除容器

```
# 停止指定容器
docker stop <容器id>
# 停止所有容器
docker stop $(docker ps -qa)
# 删除指定容器
docker rm <容器id>
# 删除全部容器
docker rm $(docker ps -qa)
# 启动容器
docker start <容器id>
```

