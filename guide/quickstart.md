# 快速试用

本文档描述如何快速试用 UAS

## 环境准备

1. 创建一台闲置云主机( UHost ) ，这里以 Ubuntu 22.04 镜像云主机为例。

![创建云主机](/images/uhost_create.png)
2. 点击负载均衡( ULB ), 点击上方网络型负载均衡( NLB )，创建一台网络型负载均衡，购买 `1m` 外网带宽，命名为 `Nginx-Service`。

![创建 NLB](/images/nlb_create.png)
3. 点击上方监听器管理，创建一个监听器，开启 80 端口，命名为 `Nginx-Service-Listener`。

![创建监听器](/images/nlb_listener_create.png)

## 部署示例服务

1. 点击云主机 UHost, 进入云主机主机管理页面，点击下方操作栏中的 `登录` 按钮，登录云主机。

2. 在浏览器终端中安装 nginx 服务。

```bash
# 更新软件包列表
sudo apt-get update

# 安装 nginx
sudo apt-get install -y nginx

# 启动 nginx 服务
sudo systemctl start nginx
```

3. 验证服务是否正常运行。

```bash
curl http://localhost
```

![验证服务](/images/nginx_test.png)

## 制作主机镜像

1. 点击云主机 UHost, 进入云主机主机管理页面，点击之前配置的云主机，从下方操作栏中点击 `...` 按钮，打开操作菜单，点击 `更多操作`， 点击 `制作镜像`。

![制作镜像](/images/uhost_image_create.png)

2. 制作镜像，命名为 `Nginx-Service-Image`。

![制作镜像](/images/uhost_image_create_2.png)
3. 等待镜像制作完成。

## 制作主机启动模版

1. 点击云主机 UHost, 进入云主机主机管理页面，点击上方主机启动模版，点击 `新建模版`。

2. 新建模版，命名为 `Nginx-Service-Template`，操作系统选择部分点击自制镜像，选择之前制作的镜像 `Nginx-Service-Image`。

![新建模版](/images/uhost_template_create.png)
3. 点击立即保存。

## 创建伸缩组

1. 点击弹性伸缩，点击 `创建伸缩组`。

2. 使用主机模版创建伸缩组，选择之前制作的模版 `Nginx-Service-Template`，配置伸缩组参数，点击下一步。

![创建伸缩组](/images/auto_scaling_create.png)
3. 命名为 `Nginx-Service-Group`，点击负载均衡下的立即绑定，选择之前创建的网络型负载均衡，选择`Nginx-Service`，选择`Nginx-Service-Listener`，点击确定，端口配置为 `80`。

![创建伸缩组](/images/auto_scaling_create_2.png)
4. 点击完成创建。
5. 刷新页面查看伸缩组云主机是否正常运行。

## 验证服务

1. 点击负载均衡，点击之前创建的网络型负载均衡，查看之前购买的 `Nginx-Service` 的公网 IP，访问公网 IP，查看服务是否正常运行。
