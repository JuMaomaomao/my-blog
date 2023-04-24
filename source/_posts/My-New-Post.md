---
title: My New Post
date: 2023-04-24 20:10:32
tags:
---

1. 生成配置文件`config.yml`，选择`1：HTTP通信`

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
