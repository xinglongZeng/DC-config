# DC-config
分布式配置中心

## 功能点
1. 能够分工程、分环境存储配置；
2. 配置数据具有状态，用来区分配置是否成功发送给其他应用服务器。服务器总数量为N，使用该配置的服务器数量为 Z  状态值：未启用（ Z == 0 ） 、全部启用（ Z == N ）、部分启用（ 0 < Z < N ）
3. 分布式配置中心通过心跳与其他应用服务器保持连接，心跳周期可配置
4. 账户认证 （优先级低）
6. 配置改动要有历史记录

## 架构
按功能分层，从上到下为：核心层（核心层只有3个模块 “配置、用户、通信”），扩展层（除核心层的3个模块，其他所有功能都是扩张层的，因为配置中心的核心功能就是对配置的处理，所有其他功能都是为其服务的）、

 - 配置模块（处理配置项）
 - 用户模块 (处理账户信息以及权限配置)
 - 通信模块 (处理网络与心跳等通信相关的内容)



## 开放语言
 - 主要使用golang