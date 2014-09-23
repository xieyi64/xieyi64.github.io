---
layout: postlayout
title: Nginx日志格式
categories: [web服务端]
tags: [nginx]
---

##示例

~~~
http {
	log_format main '$remote_addr - $remote_user [$time_local] "$request" '
	'$status $body_bytes_sent "$http_referer" '
	'"$http_user_agent" $http_x_forwarded_for "$request_time"';
	
	access_log /var/log/nginx/access.log main;
}

server {
	server_name  test.com;
	root html;
	index  index.html;
	access_log logs/access.log main;
}
~~~

##log_format指令

语法|log_format name string ...
默认值|combined "..."
使用字段|http

##log_format参数说明
- `$remote_addr` 和 `$http_x_forwarded_for`：记录客户端的ip地址。
- `$remote_user`：记录客户端用户名称。
- `$time_local`：记录访问时间与时区。
- `$request`：记录请求的URL与HTTP协议。
- `$status`：记录请求状态；成功是200。
- `$body_bytes_sent`：记录发送给客户端文件主体内容大小。
- `$http_referer`：记录从那个页面链接访问过来的。
- `$http_user_agent`：记录客户端浏览器的相关信息。
- `$request_time`：响应时间

##access_log指令

语法|access_log path \[ format \[ buffer = size \]\] access_log off
默认值|logs/access.log combined
使用字段|http server location limit_except
