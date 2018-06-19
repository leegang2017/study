
ubuntu安装
sudo apt-get install nginx




nginx命令
 ```js
//重新启动nginx:
/etc/init.d/nginx stop
/etc/init.d/nginx start

nginx -s reload //刷新服务器的配置文件
stop — fast shutdown 
quit — graceful shutdown 
reload — reloading the configuration file 
reopen — reopening the log files 
 ```

配置静态资源
 ```js
 server {
        listen       80;
        server_name  localhost;
        location /file/img/ {
                default_type  'application/octet-stream';
                alias /home/lee/Picturesj/;
        }

    }
 ```
 配置相同端口多应用
 ```js
 server {
        listen       80;
        server_name  localhost;
        location /home/ {
                proxy_pass http://localhost:9000/jkweb/;
        }

        location /hcc-service/ {
                proxy_pass http://localhost:8080/hcc-service/;
        }

    }
 ```