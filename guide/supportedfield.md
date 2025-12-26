# UAS主机模板支持字段说明
本文档详细列出主机模板在UAS中的支持字段，未列出的字段暂不支持，若有需求可提工单。按模块分类，包含字段名称和描述说明，为伸缩组创建、模板配置提供标准化参考依据。

### 1. 核心元数据 (Meta)
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>UTemplateId</td>
    <td>模板 ID</td>
  </tr>
  <tr>
    <td>Name</td>
    <td>模板名称</td>
  </tr>
  <tr>
    <td>Remark</td>
    <td>描述信息</td>
  </tr>
  <tr>
    <td>UTVersion</td>
    <td>版本号</td>
  </tr>
  <tr>
    <td>Default</td>
    <td>是否为默认版本</td>
  </tr>
  <tr>
    <td>DefaultVersion</td>
    <td>默认版本号</td>
  </tr>
  <tr>
    <td>LastVersion</td>
    <td>最新版本号</td>
  </tr>
  <tr>
    <td>BindResource</td>
    <td>绑定该模板的资源 ID 列表</td>
  </tr>
  <tr>
    <td>CreateTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>Labels</td>
    <td>资源标签（*注：伸缩组扩容时，新建主机的资源标签以当前关联主机模板及模版规则所匹配的版本标签值为准。）</td>
  </tr>
</table>

### 2. 基础与计费 (Basic)
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>Region</td>
    <td>地域</td>
  </tr>
  <tr>
    <td>Zone</td>
    <td>可用区</td>
  </tr>
  <tr>
    <td>ChargeType</td>
    <td>付费类型</td>
  </tr>
  <tr>
    <td>Quantity</td>
    <td>购买时长</td>
  </tr>
</table>

### 3. 计算与系统 (Compute & OS)
#### （1）规格
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>CPU</td>
    <td>CPU</td>
  </tr>
  <tr>
    <td>Memory</td>
    <td>内存大小</td>
  </tr>
  <tr>
    <td>MachineType</td>
    <td>机型</td>
  </tr>
</table>

#### （2）镜像
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>ImageId</td>
    <td>镜像ID</td>
  </tr>
  <tr>
    <td>ImageName</td>
    <td>镜像名称</td>
  </tr>
  <tr>
    <td>ImageType</td>
    <td>镜像类型</td>
  </tr>
  <tr>
    <td>OsName</td>
    <td>操作系统名称</td>
  </tr>
</table>

### 4. 存储配置 (Storage)
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>Disks</td>
    <td>磁盘数组</td>
  </tr>
  <tr>
    <td>AutoDataDiskInit</td>
    <td>是否自动挂载数据盘开关</td>
  </tr>
  <tr>
    <td>Type</td>
    <td>磁盘类型</td>
  </tr>
  <tr>
    <td>Size</td>
    <td>磁盘大小（GB）</td>
  </tr>
  <tr>
    <td>IsBoot</td>
    <td>是否系统盘</td>
  </tr>
</table>




### 5. 网络配置 (Network)
#### （1）内网配置
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>VpcId</td>
    <td>私有网络ID</td>
  </tr>
  <tr>
    <td>SubnetId</td>
    <td>子网ID</td>
  </tr>
</table>

#### （2）网络特性
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>Features.UNI</td>
    <td>是否开启虚拟网卡</td>
  </tr>
  <tr>
    <td>NetCapability</td>
    <td>网络增强</td>
  </tr>
</table>

#### （3）公网配置（NetworkInterface.EIP）
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>OperatorName</td>
    <td>线路（BGP/International）</td>
  </tr>
  <tr>
    <td>Bandwith</td>
    <td>带宽值 (Mbps)</td>
  </tr>
  <tr>
    <td>PayMode</td>
    <td>计费模式（Traffic/Bandwidth/ShareBandwidth）</td>
  </tr>
</table>

### 6. 安全与防护 (Security)
<table width="100%" border="0">
  <tr>
    <td width="30%" align="left"><strong>字段</strong></td>
    <td width="70%" align="left"><strong>说明</strong></td>
  </tr>
  <tr>
    <td>SecurityGroupId</td>
    <td>防火墙 ID</td>
  </tr>
  <tr>
    <td>SecGroupId</td>
    <td>安全组（数组），包含 Id 和 Priority（优先级）</td>
  </tr>
</table>





