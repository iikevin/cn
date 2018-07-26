## 基础架构 

### 概述

京东云私有网络产品完全由京东云虚拟网络团队自主研发，针对传统SDN网络进行了一系列的性能优化，例如在不同层面上去单点、去单链路等等。具体逻辑架构如下图： 

![](../Image/Basic-Infrastructure.png)



### 组件

VPC：VPC是用户网络在京东云上的表现形式，包含了一系列的网络功能，与其他的VPC逻辑隔离。VPC有一个网络地址空间，用户可以在其中继续划分子网。

子网：子网是对VPC地址空间的再一次划分，用户可以在子网中创建云主机。

路由表：路由表实现在Vrouter上，Vrouter本身并未对用户暴露，用户可以通过路由表配置路由。

ACL：ACL实现在Vrouter上，Vrouter本身并未对用户暴露，用户可以通过ACL配置子网级别东西向和南北向的访问控制。

安全组：安全组实现在每个计算节点上，用户可以通过安全组配置实例级别东西向和南北向的访问控制。

公网网关：公网网关实现在VPC之外，京东云默认为每个用户都配置了公网网关，用户可以在路由表中配置路由使用公网网关。

BGW：BGW实现在VPC之外，承载专线通道和托管通道，用户根据需求自行购买，并通过配置路由表使用BGW网关。



### 多AZ架构

子网：子网为跨AZ产品。用户创建的子网时无需选择AZ区，子网内的资源可以仅基于某一个AZ区创建使用，也可以分布到多个AZ区进行创建使用。

私网IP：私有IP为跨AZ产品。私网IP的AZ属性由关联资源（如云主机）的AZ属性决定。

公网IP：公网IP为跨AZ产品。用户申请公网IP时无需选择可用区属性，公网IP默认在所有AZ区内均可使用。

负载均衡：负载均衡为多AZ产品。用户创建负载均衡时需自选AZ属性，用户可根据需求指定负载均衡所在的可用区。