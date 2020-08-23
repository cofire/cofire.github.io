~~~bash
#user  nobody;
worker_processes  1;

#error_log  logs/error.log;
#error_log  logs/error.log  notice;
#error_log  logs/error.log  info;

#pid        logs/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       mime.types;
    default_type  application/octet-stream;

    #log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
    #                  '$status $body_bytes_sent "$http_referer" '
    #                  '"$http_user_agent" "$http_x_forwarded_for"';

    #access_log  logs/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    #keepalive_timeout  0;
    keepalive_timeout  65;


    server {
       listen 443 ssl;
       server_name njyeq.com; 
       root /opt/ylreports/vue/; 
       index index.html index.htm;
       ssl_certificate  /opt/ylreports/nginx-https/4069996_www.njyeq.com.pem; 
       ssl_certificate_key /opt/ylreports/nginx-https/4069996_www.njyeq.com.key; 
       ssl_session_timeout 5m;
       ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:ECDHE:ECDH:AES:HIGH:!NULL:!aNULL:!MD5:!ADH:!RC4;
       ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
       ssl_prefer_server_ciphers on;
       location / {
         index index.html index.htm;
        }
       location /img/ {
         root /opt/ylreports/;  
       }
       location /ylsports-api{
	  proxy_pass http://localhost:9006;
	}
      location /ylsports-admin{
          proxy_pass http://localhost:9008;
        } 
    }
    server {
       listen 80;
       server_name njyeq.com;
       rewrite ^(.*)$ https://$host$1 permanent;
    }

    #gzip  on;

}


stream {

    upstream cloudsocket {
       hash $remote_addr consistent;
      # $binary_remote_addr;
       server 192.168.0.3:3306 weight=5 max_fails=3 fail_timeout=30s;
    }
    server {
       listen 3306;#数据库服务器监听端口
       proxy_connect_timeout 10s;
       proxy_timeout 300s;#设置客户端和代理服务之间的超时时间，如果5分钟内没操作将自动断开。
       proxy_pass cloudsocket;
    }
    upstream redis {
       hash $remote_addr consistent;
      # $binary_remote_addr;
       server redis-564708f-dcs-0ll9.dcs.huaweicloud.com:6379 weight=5 max_fails=3 fail_timeout=30s;
    }
    server {
       listen 6379;#数据库服务器监听端口
       proxy_connect_timeout 10s;
       proxy_timeout 300s;#设置客户端和代理服务之间的超时时间，如果5分钟内没操作将自动断开。
       proxy_pass redis;
    }
}

~~~

