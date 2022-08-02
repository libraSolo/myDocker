# Docker 镜像操作

## 拉取镜像到本地

```
docker pull <版本号>
```

## 查看本地所有镜像

```
docker images
```

## 删除镜像

```
docker rmi <镜像标识(image id)>
```

## 镜像导出导入

```
docker save -o <路径[/name]> <标识>
```

## 加载本地镜像

```
docker load -i 镜像文件
```

## 修改镜像名称

```
docker tag 镜像id 新name:版本
```

