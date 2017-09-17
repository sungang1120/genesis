# LCN分布式事务框架的设计原理 

框架基于协调spring事务，通过控制协调本地事务与全局事务的一致性从而达到分布式事务的效果。

备注：LCN框架 非TCC机制，非2PC机制 非3PC机制。

## TxManager启动说明

见[启动](start.md)

## LCN名称的得来

在设计框架之初的1.0 ~ 2.0的版本时，框架设计的步骤是如下的，各取其首字母得来的LCN命名。

锁定事务单元（lock）   
确认事务模块状态(confirm)   
通知事务(notify)     



## TxManager与控制方的通讯协议

见 [TxManager与事务控制方的通讯协议](protocol.md)    



## LCN设计原理 

v1.0设计原理  - LCN的第一个版本

[v2.0设计原理](README2.0.md) -替换了通讯框架
 
[v2.1设计原理](README2.1.md) -简化了操作步骤

[v2.2设计原理](README2.2.md) -增加了事务补偿

[v2.3设计原理](README2.3.md) -合并增加和修改事务组，简化分布式启动模块业务处理，优化模块二次调用

[v3.0设计原理](README3.0.md) -将事务控制权转移给代理连接池



## LCN的版本史

从1.0 到 2.0 性能提升了4倍。   
从2.0 到 2.1 性能提升了33%，增加了高可用性。    
从2.1 到 2.2 增加了事务补偿，更加完美的确保了事务的一致性。   
从2.2 到 2.3 性能提升了50%，减少了一步操作，提高了模块连接资源利用率。   
从2.3 到 3.0 性能可给本地事务相媲美。   

... ...   

