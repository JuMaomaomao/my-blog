---
title: 个人自用docker镜像
date: 2023-04-26 23:53:14
cover: https://cdn.jsdelivr.net/gh/JuMaomaomao/images@latest/docker.webp
tags:
---

> **go-cqhttp**

1. 生成配置文件`config.yml`，选择`反向ws`

   ```bash
   docker run --rm -it --name="gocq" -v $PWD/gocq:/data xzsk2/gocqhttp-docker:latest
   ```

2. 修改`gocq/config.yml`，参考 [go-cqhttp 帮助中心](https://docs.go-cqhttp.org/guide/config.html)

3. 运行

   ```bash
   docker run -d --name="gocq" -v $PWD/gocq:/data xzsk2/gocqhttp-docker:latest
   ```

4. 登陆

   ```bash
   docker logs gocq
   ```

> **autman**

```sh
docker run -d --name autman --restart always --net=host -v $PWD/autman:/autMan lanb3996/autman:1.2
```

> **qinglong**

```sh
docker run -dit \
  -v $PWD/ql:/ql/data \
  -p 5700:5700 \
  --name qinglong \
  --hostname qinglong \
  --restart unless-stopped \
  whyour/qinglong:2.11.3
```

> **sign** Docker搭建GetSign服务（KR库可更换本地接口使用）

```sh
docker run -dit \
  --name offical \
  --restart always \
  --hostname official \
  -p 9527:80 \
  eyesouls/official:latest
```

配置文件sign配置

```sh
## 自定义SIGN接口变量：
export JD_SIGN_KRAPI="http://<ip>:9527/jd/sign"
```
