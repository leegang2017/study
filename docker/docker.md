docker安装

https://yq.aliyun.com/articles/110806


alpine修改源,修改Dockerfile
```sh
 RUN echo http://mirrors.aliyun.com/alpine/v3.6/main > /etc/apk/repositories; \
echo http://mirrors.aliyun.com/alpine/v3.6/community >> /etc/apk/repositories
  ```

创建镜像
docker build  -t my-node-rdkafka .

启动容器，保持启动
docker run -dit \
--rm \
 --volume "$PWD/work":/data/g7-work/docker/node-rdkafka/app \
 -p 3000:3000 \
  -p 9999:9999 \
 my-node-rdkafka

  复制文件
  docker container cp 7a2b4d075bc1:/data/g7-work/docker/node-rdkafka/app .

容器IP的查方法
docker inspect 容器ID或容器名 |grep '"IPAddress"'

连接、查看容器
docker exec -it 967c0976a0dd /bin/bash