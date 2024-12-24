## Docker

### install

### image

### container

### Dockerfile

### Docker Compose

### port

### command

#### run

`-t` 选项让 Docker 分配一个伪终端（pseudo-tty）并绑定到容器的标准输入上
`-i` 则让容器的标准输入保持打开
`-d` 则让容器运行在后台
`-p` 端口映射：主机端口：容器端口
`-v` 挂载主机目录：主机目录：容器目录

```
docker run -itd \
    -p 80:3000\
    -v /sources/node:/sources \
    --name node \
    node:16.20.0
```

#### cp

```
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH
docker cp [OPTIONS] SRC_PATH CONTAINER:DEST_PATH
```

- copy from container

```
docker cp container_id:/sources /sources
## cd /sources
## mv ./sources ./node
```

- copy to container

```
docker cp /sources/node container_id:/
## docker exec -it container_id /bin/bash
## mv ./node ./sources
```
