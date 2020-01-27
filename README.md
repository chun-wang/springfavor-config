# springfavor-config

### 网址维护

| 网址                           | 用途             | 详细 |
| ------------------------------ | ---------------- | ---- |
| http://blog.springfavor.cn     | 个人博客         |      |
| http://wallabag.springfavor.cn | wallabag稍后阅读 |      |
| http://frps.springfavor.cn     | frp管理面板      |      |
| https://nas.springfavor.cn     | 内网nas          |      |



### 数据文件夹

~~~bash
/opt/
~~~

### 启动Nginx

~~~bash
docker run --restart=always --name nginx-container -p 80:80 -v /root/springfavor-config/nginx/nginx.conf:/etc/nginx/nginx.conf:ro -d nginx
~~~

### 启动wallabag

~~~bash
docker run --restart=always --name wallabag-container -v /opt/wallabag/data:/var/www/wallabag/data -v /opt/wallabag/images:/var/www/wallabag/web/assets/images -p 8080:80 -e SYMFONY__ENV__DOMAIN_NAME=http://wallabag.springfavor.cn/ -d wallabag/wallabag
~~~

### 启动frps

~~~bash
supervisorctl start frps
~~~

