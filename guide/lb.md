# 在弹性伸缩使用负载均衡

## 管理负载均衡
在"伸缩组详情-概览页-负载均衡管理"，可以查看伸缩组绑定的负载均衡列表。点击“绑定”按钮,可以为伸缩组绑定新的负载均衡。
(注意：只能绑定同一vpc下的lb，且不能重复绑定lb中的listener)

![](/images/lb_manage_1.png)
![](/images/lb_manage_2.png)

### 注意事项

1. 不建议使用传统型负载均衡，报文转发型与弹性伸缩一起使用，其服务节点配置目前存在严苛条件，请参考 [报文转发模式服务节点配置
   ](https://docs.ucloud.cn/ulb/guide/realserver/editrealserver)