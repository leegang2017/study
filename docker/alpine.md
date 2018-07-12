alpine修改源,修改Dockerfile
```sh
 RUN echo http://mirrors.aliyun.com/alpine/v3.6/main > /etc/apk/repositories; \
echo http://mirrors.aliyun.com/alpine/v3.6/community >> /etc/apk/repositories
  ```

安装krb5
apk --no-cache add krb5
