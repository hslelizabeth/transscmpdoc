# 管理节点池

您可以通过节点池管理集群中的一组 Node 节点，他们一般具有相同的实例规格、标签污点、操作系统镜像等。本文介绍如何基于 TKS 中的节点池功能，进行创建节点池等操作。

## 前提条件

* 已创建 [TKS 集群](/tks/managecluster/createcluster)

## 创建节点池

1. 登录[容器服务管理控制台](https://eu-central-1.console.eagllwin.com/cluster)。
2. 在控制台左侧导航栏中，单击**集群管理 > 集群列表**，进入**集群列表**页面，单击目标集群名称进入集群管理页面。
3. 在集群管理页左侧导航栏中，选择**节点管理 > 节点池**。
4. 在**集群列表页面**中，单击页面上方的**新增**。
5. 在**节点池/创建**页面，完成节点池配置。

a. 基本信息
|配置项|描述|
|----|----|
|节点池名称|根据业务需求自行命名。<br>集群名称应包含 2-50 个字符，以英文大小字母开头，可包含数字、中划线（-）。|
|所在地域|跟随集群所在地域。|
|子网|节点池节点及 Pod 所在子网，请根据所需要的可用区及网段大小选择。<br>当前网络模式下，Pod 将与 Node 节点共享子网及网段。|
|付费类型|提供按量付费及包年包月两种集群及节点付费类型，选择包年包月时，需设置购买时长。|
|购买时长|目前支持选择 1、2、3、6 个月和 1-3 年。|
|容器运行时|当前仅支持 Docker，后续将开放 Containerd 等运行时支持。|
|镜像版本|Node 节点操作系统镜像。|

b. 节点池配置
|配置项|描述|
|----|----|
|规格|当前集群仅支持单实例规格节点池。|
|系统盘|大小默认为 100G，您可以跟据实例规格和所在地域选择可用的存储类型。|
|期望节点数量|请根据实际需求进行设置。|

c. 标签与污点
|配置项|描述|
|----|----|
|标签|为节点池中节点添加标签，关于节点标签的使用请参照[官方文档](https://kubernetes.io/zh/docs/concepts/overview/working-with-objects/labels/)|
|污点|为节点池中节点添加污点，关于节点污点的使用请参照[官方文档](https://kubernetes.io/zh/docs/concepts/scheduling-eviction/taint-and-toleration/)|