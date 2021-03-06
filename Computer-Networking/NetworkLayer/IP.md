# IP
----

## 网络层组件

网络层有三个主要的组件：

+ IP协议
+ 选路组件
+ 报告数据中的差错和对某些网络层信息请求进行相应的设施


## 数据报格式

这里所说的数据报是指IPv4数据报

+ **版本号** 指明所使用的IP协议的版本。
+ **首部长度** 由于IPv4数据报有可选字段，所以用这个字段来指明报头的长度。
+ **服务类型** 指明不同类型的IPv4数据报。
+ **数据报长度** IPv4数据报的总长度。
+ **标识、标志、位偏移** 与IP分片有关。
+ **寿命** 数据报存活寿命，每经过一台路由器，寿命减1。
+ **上层协议** 指明数据报中的数据所用到的运输层协议。_协议号是将网络层与运输层绑定到一起的粘合剂，而端口号则是将运输层与应用层绑定在一起的粘合剂。_
+ **首部检验和**
+ **源和目的地的IP地址**
+ **可选选项**


## IP数据报分片

一个链路层帧能承受的最大数据量称为**最大传输单元**，因为每个IP数据报封装在链路层帧中，在从一台路由器运输到下一台路由器，故链路层协议MTU严格限制着IP数据报的长度。对IP数据报长度的限制并不是主要问题，真正的问题是在发送方与目的地路径上的每段链路可能使用不同的链路层协议，且每种协议可能具有不用的MTU。

路由器会将IP数据报中的数据分片成两个或更小的数据报，用单独的链路层帧来对他们进行封装。这些较小的数据报称为**帧**。

对于每个数据报，它的所有分片共享一个标识号，且最后一个片具有标志位0，其余的标志位都为1，偏移记录了每个分片在原来数据报的起始位置。数据报分片由端系统中的运输层协议来进行重新组合。
