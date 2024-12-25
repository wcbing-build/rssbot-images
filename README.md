为 [iovxw/rssbot](https://github.com/iovxw/rssbot)（Telegram [@RustRssBot](http://t.me/RustRssBot)）构建镜像的 Containerfile。

## 使用方式

```
docker run -d -v <data_path>:/mnt \
    -e TOKEN=<token> \
    --name rssbot \
    wcbing/rssbot:latest
```

- 数据文件 `rssbot.json` 存放在 `/mnt` 中，建议挂载该目录到本地。
- 机器人 token 可通过环境变量 `TOKEN` 设置，也可在最后追加。
- 有其他参数也可以直接在后面追加，如：
    ```
    docker run -d -v <data_path>:/mnt \
        -e TOKEN=<token> \
        --name rssbot \
        wcbing/rssbot:latest --min-interval 3600
    ```

Docker Hub 上只上传了 x86_64 的镜像，有需要可以使用 Containerfile 自行构建。
