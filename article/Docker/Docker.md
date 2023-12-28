# Ubuntu 安装 Docker
**2023-12-28**
***

cd到自己喜欢的目录，按顺序执行以下指令

从Docker官网获取安装脚本
```shell
curl -fsSL https://get.docker.com -o get-docker.sh
```

执行安装脚本
```shell
sudo sh get-docker.sh
```

启动Docker
```shell
sudo service docker start
```

删除脚本
```shell
rm get-docker.sh
```