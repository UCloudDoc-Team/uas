# UAS主机模板支持字段说明

本文档详细列出主机模板在UAS中的支持字段，按模块分类，包含字段名称和描述说明，为伸缩组创建、模板配置提供标准化参考依据。

## 1. 核心元数据 (Meta)
| 字段       | 说明                     | 
|----------------|--------------------------|
| UTemplateId    | 模板 ID                  |
| UTVersion      | 版本号                   |
| Default        | 默认版本标记              |
| DefaultVersion | 默认版本号               |
| BindResource   | 绑定该模板的资源 ID 列表  |
| CreateTime     | 创建时间                 |

## 2. 基础与计费 (Basic)
| 字段   | 说明          | 
|------------|----------------|
| Region     | 地域           |
| Zone       | 可用区         |
| ChargeType | 付费类型       |
| Quantity   | 购买时长       |

## 3. 计算与系统 (Compute & OS)
#### （1） 规格
| 字段           | 说明               |
|--------------------|--------------------|
| CPU                | CPU          |
| Memory             | 内存大小           |
| MachineType        | 机型               |
| MinimalCpuPlatform | 最低CPU平台        |

#### （2） 镜像
| 字段  | 说明         |
|------------|----------------|
| ImageId    | 镜像ID         |
| ImageName  | 镜像名称       |
| ImageType  | 镜像类型       |
| OsName     | 操作系统名称   |

#### （3） 监控
| 字段             | 说明                    |
|----------------------|--------------------------|
| UboltAgentReinforce  | 是否开启主机监控（True/False） |
| UboltAgent           | 监控代理开关             |

## 4. 存储配置 (Storage)

| 字段 | 说明          |
|----------|----------------|
| Disks    | 磁盘数组           |
| AutoDataDiskInit     | 是否自动挂载数据盘开关    |

#### （1）基础配置
| 字段 | 说明          |
|----------|----------------|
| Type     | 磁盘类型           |
| Size     | 磁盘大小（GB）     |
| IsBoot   | 是否系统盘     |

#### （2）进阶配置
| 字段     | 说明         |
|--------------|----------------|
| BackupMode   | 备份策略       |
| BackupType   | 备份方案       |
| SnapshotId   | 快照ID         |



## 5. 网络配置 (Network)
#### （1） 内网配置
| 字段   | 说明          |
|------------|----------------|
| VpcId      | 私有网络ID     |
| SubnetId   | 子网ID         |

#### （2） 网络特性
| 字段           | 说明             |
|--------------------|--------------------|
| Features.UNI       | 是否开启虚拟网卡   |
| NetCapability      | 网络增强           |

#### （3） 公网配置（NetworkInterface.EIP）
| 字段           | 说明             |  可选值 | 
|--------------------|----------|------------------------------|
| OperatorName       | 线路     | BGP/International  |
| Bandwith           | 带宽值 (Mbps)|                          |
| PayMode            | 计费模式 |Traffic/Bandwidth/ShareBandwidth|
| ShareBandwidthID   | 共享带宽 ID  |                           |

## 6. 安全与防护 (Security)
#### （1） 防火墙与安全组
| 字段           | 说明                                  |
|--------------------|----------------------------------------|
| SecurityGroupId    | 防火墙 ID                               |
| SecGroupId         | 安全组（数组），包含 Id 和 Priority（优先级） |

#### （2） 其他安全配置
| 字段           | 说明             |
|--------------------|--------------------|
| SecurityMode       | 安全规则模式       |
| SecurityReinforce  | 安全加固开关       |
| IsolationGroup     | 隔离组             |

## 7. 高级特性 (Advanced)
| 字段           | 说明                   |
|-------------------|--------------------------|
| UserData          | 自定义启动脚本 (Base64)  |
| HotplugFeature    | 热升级特性 (String)      |