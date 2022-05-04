# 容器集群服务

传音云容器集群（Transsion Kubernetes Service，TKS）是一项基于 Kubernetes 的可扩展、高性能的容器管理服务。您可以在 TKS 容器集群上部署、管理您的容器化应用，而无需自行搭建、维护 Kurbenetes 集群管理基础设施。TKS 兼容原生的 Kubernetes API，只需通过简单的 API 调用或控制台操作，便可部署、启动和停止您的容器化应用程序，查询集群的完整状态，以及使用计算、存储、网络、负载均衡等各种云服务。

## 名词解释

* 集群：指 Kubernetes 集群，是容器运行所需云资源的集合，包含了集群控制面，及若干台云服务器等。
* APIServer：操作集群的唯一入口，并提供认证、授权、访问控制、API 注册和发现等机制，APIServer 作为一个组件运行在控制面上。
* Master 节点：Kubernetes 集群控制面节点，安装了用于控制和管理集群的如组件，如 APIServer、Scheduler、Controller Manager、Cloud Controller Manager、ETCD 等。TKS 当前仅提供托管版本，即 Master 节点由传音云容器服务创建并托管，从而您可以更多关注业务本身。
* Node 节点：Kubernetes 集群的工作节点，Kubernetes 通过将容器放入在节点（Node）上运行的 Pod 中来执行你的工作负载。 节点可以是一个虚拟机或者物理机器，目前 TKS 只支持虚拟机（云服务器）作为 Node 节点。每个节点包含运行 Pods 所需的服务，这些组件包括 kubelet、 容器运行时以及 kube-proxy 等。
*   Pod 实例：可以在 Kubernetes 中创建和管理的、最小的可部署的计算单元，由一个或多个容器构成，这些容器共享相同的存储和网络空间。
* Workload 工作负载：Kubernetes 资源对象，用于管理 Pod 副本的创建、调度以及整个生命周期的自动控制，常见工作负载包括 ReplicaSet、Deployment、StatefulSet、Job、CronJob 等。
* Service 服务：将运行在一组 Pods 上的应用程序公开为网络服务的抽象方法，由多个相同配置的实例（Pod）和访问这些实例（Pod）的规则组成。

如果你希望了解更多内容，请移步[Kubernetes 官方文档](https://kubernetes.io/zh/)

## 使用须知

在使用 TKS 容器集群前，您需要知晓以下事项或完成以下操作：

* 注册传音云账号（Palm ID），并完成实名认证。
* 创建集群前，需要在目标地域创建一个私有网络，并且在私有网络下的目标可用区创建一个子网。
* 单个UK8S集群最多添加 100 个 Node 节点，如需要更大规模的集群，请联系技术支持团队。
* TKS 支持的 Kubernetes 版本一般落后社区最新 1-2 个版本，具体以产品页面为准。