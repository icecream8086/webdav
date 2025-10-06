# !仅供测试,配置为确保兼容性，未提供任何安全设置

## nginx搭的简易款简易对象存储服务

基于WebDAV协议 免去了自己在web服务器实现文件存储的阴间问题

模拟CDN图床行为,服务器管理URL即可，成功解耦后端和数据库和存储池

利用了现有的Nginx，免去了自己造轮子的问题

内存占用极小 几mb左右内存消耗，镜像大小仅200m

推荐WSL容器化隔离，省事，也可以直接放主机上，理论上跨平台

易于复刻，哪怕不懂容器也能使用cockpit.podman GUI填写内容一键启动

## 使用方法

### 端口

0.0.0.0:5500 → 5500/tcp

---

### 文件映射

host/nginx.conf ↔ /etc/nginx/nginx.conf

host/webcdn.conf ↔ /etc/nginx/conf.d/webcdn.conf

host/dir ↔ /data/nginx-upload-storage

---

## 注:需要创建文件夹然后赋权,详见webdav-api.http，官方原版Nginx没有这个`/data/nginx-upload-storage`文件夹

---

## api文档

### 见webdav-api.http文件
