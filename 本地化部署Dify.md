# **本地化部署Dify**

Dify官方地址提供了一定的免费额度，不过只支持上传 50 个文档，且支持 RAG 的向量空间也只有 5 MB。如果不想付费，且对自己的私有数据安全有更高要求，那么建议本地私有化部署Dify。
本地化部署Dify主要有两种部署方式，分别是Docker安装和源码安装，这里我们只介绍Docker安装方式。

## 步骤一：准备Docker

 1. 自定义路径安装：
从[Docker官网](https://www.docker.com/get-started/)根据设备的操作系统选择对应版本下载安装。
 
 2. 验证Docker：
在命令行输入下列指令：
	```
	docker -v
	docker-compose -v
	```
    显示下图所示内容后说明安装成功：
	![Docker 和 Docker Compose版本号](https://notes.sjtu.edu.cn/uploads/upload_c1ded7258f1f3950ce17b5514e6f86d4.png)
    
 3. 切换镜像源
 ![切换路径](https://notes.sjtu.edu.cn/uploads/upload_e331cac345bdf40e1bb4d74fc179bec3.png)
 将文本框内的内容修改为下列代码：
    ```
    {
      "builder": {
        "gc": {
          "defaultKeepStorage": "20GB",
          "enabled": true
        }
      },
      "experimental": false,
      "registry-mirrors": [
        "https://docker.feng.cx",
        "https://docker.m.daocloud.io",
        "https://docker.imgdb.de",
        "https://docker-0.unsee.tech",
        "https://docker.hlmirror.com",
        "https://docker.1ms.run",
        "https://func.ink",
        "https://lispy.org",
        "https://docker.xiaogenban1993.com",
        "https://docker.xuanyuan.me",
        "https://docker.rainbond.cc",
        "https://do.nark.eu.org",
        "https://dc.j8.work",
        "https://docker.hpcloud.cloud",
        "https://docker.unsee.tech",
        "https://docker.1panel.live",
        "http://mirrors.ustc.edu.cn",
        "https://docker.chenby.cn",
        "http://mirror.azure.cn",
        "https://dockerpull.org",
        "https://dockerhub.icu",
        "https://hub.rat.dev"
      ]
    }
	```
    修改后点击保存。
    
## 步骤二：准备Dify
下载Dify源码：
* 方法一：从[Github](https://github.com/langgenius/dify/)下载代码压缩包，自定义路径解压。
* 方法二：克隆Dify源码到本地，在命令行窗口输入指令：
    ```
    git clone https://github.com/langgenius/dify.git
    ```
## 步骤三：部署启动Dify
进入 docker 目录，复制一份环境变量，采用默认端口，一键启动：
```
cd dify/docker
cp .env.example .env
docker compose up -d
```
启动完成后，验证一下：
```
docker compose ps
```
同时可以在Docker应用中看到启动的容器以及资源占用情况：
![](https://notes.sjtu.edu.cn/uploads/upload_01bec7ae6701cf9077611bf1f9816626.png)

## 打开进入Dify
在浏览器中访问：```localhost/install```，注册账号后登陆即可开始使用。

## 后续更新操作
```
进入 dify 源代码的 docker 目录，按顺序执行以下命令：
 
cd dify/docker
git pull origin main
docker compose down
docker compose pull
docker compose up -d
```