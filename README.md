# NSER 作用
>提供服务注册与发现的轻量级注册中心

作为远程RPC调用服务的一环，注册中心提供了服务注册与发现的功能，让RPC远程调用通过第三方建立调用者与被调用者的联系，实现更易于管理的服务架构。
该注册中心（NSER）仿照[Nacos](https://github.com/alibaba/nacos)实现了三个API，且暂仅支持原生Java调用，它目前提供了四大基本功能：
-  **服务注册和发现**
	- NSER 使得服务可以轻松注册自己并通过API接口发现其它服务
-  **服务健康检查与心跳发送**
    - *服务端(Server)* 将定时对实例进行健康检查，自动剔除失效实例，提供实例变更推送
    - *用户端(Client)* 定时发送心跳以维持健康状态；自动订阅实例服务，当订阅的服务状态发生变化则会接收推送
-  **服务注册表持久化**
	- 实例状态变更时将会持久化服务注册表到磁盘，*服务端(Server)* 启动时则会自动加载已经持久化到磁盘的注册表文件
-  **自定义配置文件**
	- NSER通过 *.properties* 文件来配置*服务端(Server)* 的相应配置

# 快速开始
**第一步：您可以下载releases中最新版的压缩包来启动 服务端**
Linux平台：
>解压后您只需将目录中jar包通过java命令启动即可

Windows平台：
>解压后双击startup.bat即可启动服务端	

**第二步：您可以从NSER-Client 或 公共Maven仓库坐标得到 用户端**
> 导入项目然后开始您的旅途

# 详细说明
- NSER是基于gRPC远程调用实现的一个轻量级注册中心，提供了基本的服务发现与注册功能，暂不支持集群服务。

- 在阅读源码时，您只需要具备gRPC的相关使用经验即可。如果您对[Nacos](https://github.com/alibaba/nacos)的使用较为熟悉，在使用NSER用户端时您无需阅读任何说明文档。

 - NSER并未使用任何中间件以及数据库，因为持久化文件是基于gRPC原生的protocol协议序列化，所以NSER较市面上的任何注册中心都更为轻量级。

- 基本架构


[![XOxWzF.png](https://s1.ax1x.com/2022/06/18/XOxWzF.png)](https://imgtu.com/i/XOxWzF)



[![XOxRRU.png](https://s1.ax1x.com/2022/06/18/XOxRRU.png)](https://imgtu.com/i/XOxRRU)



#  贡献


欢迎贡献者加入 NSER 项目。对于这个项目，您有任何意见或建议都可以通过issue来发布
