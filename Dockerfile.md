# Dockerfile

Docker 可以读取 dockerfile 中的指令(命令行的命令)自动生成镜像 

```
docker build -f <位置/dockerfile>
```

## Dockerfile 的基本结构

第一条指令必须是 FROM
一个声明以 # 字符开头则被视为注释

## 例子

```
# 注释
# Version 1.0

# Base images 基础镜像
FROM centos

# MAINTAINER 维护者信息
MAINTAINER mucun

# ENV 设置环境变量
ENV PATH /usr/local/nginx/sbin:$PATH

# ADD 文件放在当前目录下, 拷贝过去会自动解压
ADD nginx-1.8.0.tar.gz /usr/local/ # ngix

# RUN 执行以下命令
RUN yum install update

# WORKDIR 相当于 cd
WORKDIR /usr/local/nginx-1.8.0

# EXPOSE 映射端口
EXPOSE 80

# CMD 运行以下命令
CMD ["nginx"]
```

