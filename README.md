# darkhttpd

本镜像主要用于快速的将本地目录临时开放给互联网访问。

[darkhttpd](https://unix4lyfe.org/darkhttpd/) 是一款及其轻量级的 HTTP 服务器，仅支持伺服静态内容，很适合开放一个本地目录给互联网用户临时访问。

## 使用方法

### 快速使用

以下命令将本地 `~/local-dir` 目录开放给给网络访问，使用 `http://host-ip:8080` 即可访问。

```
sudo docker run -d --name darkhttpd \
-p 8080:80 \
-v ~/local-dir/:/www \
getnas/darkhttpd:latest
```

### 查看 darkhttpd 帮助信息

```
sudo docker run --rm getnas/darkhttpd --help
```