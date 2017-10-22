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

使用 `--rm` 参数，退出容器时同时销毁容器。

```
sudo docker run --rm getnas/darkhttpd --help
```

同样的，你可以在创建容器命令后面使用其他可用的参数，例如指定 `index` 文件，假设本地 `~/local-dir/` 目录中有一个 `index.html` 文件。

```
sudo docker run -d --name darkhttpd \
-p 8080:80 \
-v ~/local-dir/:/www \
getnas/darkhttpd:latest /www --index index.html
```

> 注意：与打印帮助列表不同，使用其他参数时一定要指定容器中的伺服目录即 `/www`。