---
title: 使用docker
---

### 下载并安装Docker

[下载链接](http://get.daocloud.io/)


### 修改Docker Daemon

> setting-->Docker Daemon

```json
{
  "registry-mirrors": [
    "https://docker.mirrors.ustc.edu.cn"
  ],
  "insecure-registries": []
}
```

### 拉取镜像

```vb
docker pull ubuntu:18.04
```

### 创建容器
```vb

docker create --name YOUR_CONTAINER_NAME ubuntu:18.04

```

### 运行容器
```vb
docker start ubuntuContainer
```

### 进入容器

```vb
docker exec -it YOUR_CONTAINER_ID /bin/bash
```

### 退出容器

```vb
exit
```
### 停止容器

```vb
docker stop YOUR_CONTAINER_ID
```

### 删除容器

```vb
docker rm -f YOUR_CONTAINER_ID 
```

[更多操作](https://www.runoob.com/docker/docker-container-usage.html)
