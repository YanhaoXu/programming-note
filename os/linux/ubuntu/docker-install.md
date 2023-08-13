# Ubuntu系统上安装Docker

### 1：更新软件包

```shell
sudo apt update
```

### 2：安装Docker依赖

```shell
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

### 3：添加Docker官方GPG密钥

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### 4：添加Docker存储库
```shell
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 5：安装Docker引擎
```shell
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```

### 6：启动Docker服务
```shell
sudo systemctl start docker
# 系统启动时自动启动Docker服务
sudo systemctl enable docker
```

### 7：验证安装
```shell
docker --version

# 下载nginx的镜像
docker pull nginx
# 启动nginx镜像
docker run --name sc-nginx-1 -p 8080:80 -d --cpu-shares 10 --cpus 1 --cpuset-cpus 0 -m 10000000 nginx
# 访问本机的8080端口
```


- ### 使用腾讯云 Docker 镜像源加速镜像下载

```shell
# 打开 /etc/docker/daemon.json 配置文件
vim /etc/docker/daemon.json

# 按 i 切换至编辑模式，添加以下内容，并保存
{
   "registry-mirrors": [
   "https://mirror.ccs.tencentyun.com"
  ]
}

# 重启 Docker
sudo systemctl restart docker
```

