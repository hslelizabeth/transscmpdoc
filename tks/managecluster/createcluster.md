# 创建集群

传音云容器集群（Transsion Kubernetes Service，TKS）当前仅提供托管版本，即 Master 节点由传音云容器服务创建并托管，从而您可以更多关注业务本身。本文介绍如何通过容器服务控制台创建 TKS 托管版集群。

## 前提条件

* 注册传音云账号（Palm ID），并完成实名认证。
* 创建集群前，需要在目标地域创建一个私有网络，并且在私有网络下的目标可用区创建一个子网。

## 操作步骤

1. 登录[容器服务管理控制台](https://eu-central-1.console.eagllwin.com/cluster)。
2. 在控制台左侧导航栏中，单击**集群管理-集群列表**。
3. 在**集群列表页面**中，单击页面上方的**新增**。
4. 在**新增集群**页面，完成集群配置。

a. 基本信息
|配置项|描述|
|----|----|
|集群名称|填写集群的名称。<br>集群名称应包含 2-50 个字符，以英文大小字母开头，可包含数字、中划线（-）。|
|所在地域|根据您所在地理位置选择靠近的地域，以降低访问延迟，提升下载速度。|
|付费类型|TKS 提供按量付费及包年包月两种集群及节点付费类型，选择包年包月时，需设置购买时长。|
|购买时长|目前支持选择 1、2、3、6 个月和 1-3 年。|
|Kubernetes 版本|当前 TKS 支持的 Kubernetes 版本。|
|容器运行时|当前仅支持 Docker，后续将开放 Containerd 等运行时支持。|

b. 节点池配置
|配置项|描述|
|----|----|
|Node 节点实例规格|当前集群仅支持单实例规格节点池。|
|Node 节点实例数量|集群初始 Node 节点数量。|
|系统盘|大小默认为 100G，您可以跟据实例规格和所在地域选择可用的存储类型。|

c. 组件配置
|配置项|描述|
|----|----|
|私有网络|集群所在 VPC 网络|
|子网|集群 Node 节点及 Pod 所在子网，请根据所需要的可用区及网段大小选择。<br>当前网络模式下，Pod 将与 Node 节点共享子网及网段。|
|Service CIDR|Service 类型为 ClusterIP 时 Service 在集群内部的范围地址。当前仅支持 192.168 网段。|
|镜像版本|Node 节点操作系统镜像。|
|配置 SNAT|集群及应用将默认具有公网访问能力。|
|APIServer 访问|TKS 默认为 APIServer 创建一个负载均衡实例，并提供 APIServer 外网访问功能。|
|时区|选择集群所要使用的时区，默认为 UTC 时间。|