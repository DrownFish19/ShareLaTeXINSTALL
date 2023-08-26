# ShareLaTeXINSTALL

## 系统环境

* ubuntu 22.04
* docker latest (Docker version 24.0.5, build ced0996)
* docker compose (docker-compose version 1.29.2, build unknown)

## 安装docker环境

参考 [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
```

2. Add Docker's official GPG key:
```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

3. Use the following command to set up the repository:
```bash
echo \
    "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

4. Update the apt package index:
```bash
sudo apt-get update
```

5. Install Docker Engine, containerd, and Docker Compose.
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo apt install docker-compose
```

## 文件下载
[链接] (https://pan.baidu.com/s/1t-M1zpo3IEQoksfVF_U6fg?pwd=utbs)

1. 下载docker镜像文件
下载后文件目录如下：
```text
docker镜像-2022-09-03/
├── docker-compose.yml
├── docker_images.sh
├── images
│   ├── a6fec987153c.dim
│   ├── e4e428a9b49b.dim
│   └── ef85efd58fca.dim
└── images.db
```

2. 安装docker镜像文件

```bash
cd docker镜像-2022-09-03 
sudo bash docker_images.sh load-images
```

3. 确认docker镜像已经导入

```bash
sudo docker image ls
```

导入镜像列表如下：
```text
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
sharelatex   2022      e4e428a9b49b   11 months ago   10GB
mongo        4.4       ef85efd58fca   11 months ago   438MB
redis        5         a6fec987153c   12 months ago   110MB
```


## 安装

1. 获取配置文件

```bash
git clone https://github.com/DrownFish19/ShareLaTeXINSTALL.git
cd ShareLaTeXINSTALL
sudo docker-compose up -d
```

2. 设置管理员账户网址

```
http://xx.xx.xx.xx/launchpad
```

3. 通过管理员账户登陆添加用户，正常使用

访问网址：http://xx.xx.xx.xx
