# Azure-900

## 1. Azure 基础知识

### 1.1. Azure 帐户

![Azure 帐户](https://docs.microsoft.com/zh-cn/learn/azure-fundamentals/intro-to-azure-fundamentals/media/scope-levels-12669ee1.png)

### 1.2. 不同类型的云模型

> ## 什么是公有云、私有云和混合云？

| 部署模型 | 说明                                                         |
| -------- | ----------------------------------------------------------- |
| 公有云   | 通过公共 Internet 提供服务，可供任何想要购买的人使用。 云资源（如服务器和存储）为第三方云服务提供商所有并且由其运营，并通过 Internet 提供。 |
| 私有云   | 私有云由计算资源组成，这些资源专供某个企业或组织的用户使用。 私有云可实际位于组织的现场（本地）数据中心，也可由第三方服务提供商托管。 |
| 混合云   | 混合云是一种计算环境，允许数据和应用程序相互进行共享，融合了公有云和私有云。 |

> 云模型比较
+ 公有云
  - 不需要资本支出即可扩大规模。

  - 可以快速地预配和取消预配应用程序。

  - 组织只需为其使用的内容付费。
+ 私有云
  - 必须购买硬件才能启动和维护。

  - 组织可全面控制资源和安全性。

  - 组织负责硬件维护和更新。
+ 混合云
  - 提供最大的灵活性。

  - 组织确定运行应用程序的位置。

  - 组织控制安全性、符合性或法律要求。

### 1.3 云的优点和注意事项

> 云计算有哪些优势？

+ 高可用性 High availability：根据你选择的服务级别协议 (SLA)，基于云的应用可以提供持续的用户体验，即使在出现故障时也不会有明显的停机时间。

+ 可伸缩性 Scalability：云中的应用可以垂直或水平缩放：

	> 垂直缩放可以通过向虚拟机添加 RAM 或 CPU 增加计算容量。
	> 水平缩放可以通过添加资源实例（例如将 VM 添加到配置中）来增加计算能力。

+ 弹性 Elasticity：可以将基于云的应用配置根据需要自动缩放，使应用始终具有所需的资源。

+ 敏捷性 Agility：根据应用需求的变化，快速部署和配置基于云的资源。

+ 地区分发 Geo-distribution：可以将应用和数据部署到全球各地的区域数据中心，从而确保客户在其区域中始终具有最佳性能。

+ 灾难恢复 Disaster recovery：通过利用基于云的备份服务、数据复制和地理分布，你可以放心地部署应用，因为你知道在发生灾难时数据是安全的。

> 资本费用与运营费用

+ 资本支出 (CapEx) 是指花在实体基础设施上的前期支出，然后逐渐扣除这笔前期费用。 CapEx 的前期成本的价值会随着时间的推移而降低。
+ 运营支出 (OpEx) 是现在花钱购买服务或产品，现在为其付费。 可以在消费的当年扣除此费用。 你可以在使用服务或产品时为其付费，无前期成本。

> 云计算是一种基于使用的模型

### 1.4 其他云服务

> 云服务模型

| Model | 定义                                          | 说明                                                         |
| ----- | --------------------------------------------- | ------------------------------------------------------------ |
| IaaS  | 基础结构即服务(*Infrastructure-as-a-Service*) | 此云服务模型是最接近于管理物理服务器的；云提供商将保持硬件是最新的，但是操作系统维护和网络配置则需要作为云租户的你完成。 例如，Azure 虚拟机是在 Microsoft 数据中心中运行的完全可操作的虚拟计算设备。 这种云服务模型的优点是快速部署新的计算设备。 设置新虚拟机比采购、安装和配置物理服务器快得多。 |
| PaaS  | 平台即服务(*Platform-as-a-Service*)           | 这种云服务模型是一种托管主机环境。 云提供商管理虚拟机和网络资源，云租户将其应用程序部署到托管主机环境中。 例如，Azure 应用服务提供托管的主机环境，开发人员可在其中上传其 Web 应用程序而无需担心物理硬件和软件要求。 |
| SaaS  | 软件即服务(*Software-as-a-Service*)           | 在这种云服务模型中，云提供商管理应用程序环境的所有方面，如虚拟机、网络资源、数据存储和应用程序。 云租户只需向由云提供商管理的应用程序提供数据。 例如，Microsoft Office 365 提供在云中运行的 Microsoft Office 的完全可用版本。 你只需创建内容，Office 365 会处理其他所有事项。 |

> 可以在每个云服务模型中运行的服务

![](https://docs.microsoft.com/zh-cn/learn/azure-fundamentals/fundamental-azure-concepts/media/iaas-paas-saas-575a09e9.png)

> 云服务模型比较

![](https://docs.microsoft.com/zh-cn/learn/azure-fundamentals/fundamental-azure-concepts/media/shared-responsibility-76efbc1e.png)