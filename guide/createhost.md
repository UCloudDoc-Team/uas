# 绑定主机模板

## 创建主机模板
在绑定主机模版前，需要先在[主机启动模板](https://console.ucloud.cn/uhost/uhost_template)新建模板

> ⚠️ 注意镜像需要配置为自制镜像，镜像包含弹性伸缩的服务
>
> ⚠️ 绑定主机模板后，伸缩组的最大最小值的约束就会生效，如果不想立刻创建主机，可以设置最大最小值都为0。

![](/images/uhost_template_2.png)

![](/images/uhost_template_3.png)




## 伸缩组绑定主机模板

创建完伸缩组，根据提示或者在列表页点击`绑定主机模板`进入主机模板的绑定页面。对伸缩组自动创建的主机配置进行设置。

![](/images/uhost_template_1.png)

![](/images/uhost_template.png)

