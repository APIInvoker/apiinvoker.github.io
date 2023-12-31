# Docker安装Redis
**2023-12-28**
***

```shell
sudo docker pull redis
```

```shell
cd ~
mkdir conf
cd conf
mkdir redis
cd redis
```

从Redis官网获取Redis配置文件。
获取后为了开启远程连接，将文件中其中的```bind 127.0.0.1 -::1```注释，
将```protected-mode yes```改成```protected-mode no```
```shell
wget http://download.redis.io/redis-stable/redis.conf
```

*你没看错，有的参数是两个斜杠，确实是两个！*
- ```--name 你要为这个容器起什么名称```
- ```-d 后台运行容器，返回容器ID```
- ```-p xxx:xxx``` 端口映射
系统端口:容器内部端口
- ```--restart always``` 自动启动容器
- ```-v aaa:bbb``` 文件挂载
aaa:容器外部文件 bbb:容器内部文件
```shell
sudo docker run --name redis -d -p 6379:6379 --restart always -v /home/zx/redis/conf/redis.conf:/etc/redis.conf redis redis-server /etc/redis.conf
```

进入容器
```shell
sudo docker exec -it redis /bin/bash
```

测试Redis连接功能
```shell
redis-cli
```