# Routing Algorithm
-------------------

一台主机肯定于一台路由器相连，该路由器称为该主机的**默认路由器**，又称为该主机的**第一跳路由器**。每当某主机发送一个分组时，该分组都被传送给它的默认路由器，源主机的默认路由器称为**源路由器**，把目的主机的默认路由器称为**目的路由器**。


## 选路算法的分类

选路算法是从源路由器到目的路由器的选路问题。一般有以下几种分类方法：

### 全局选路算法与分布式选路算法

+ **全局选路算法**是用完整的，全局性的网络知识来计算从源到目的之间的最低费用路径。具有全局状态信息的算法通常被称为**链路状态**算法。

+ **分布式选路算法**是以迭代的，分布式的方式计算出最低费用路径，没有节点拥有整个网络费用的完整信息，而每个节点仅有与其直接相连链路的费用知识集开始工作。**距离向量**算法是一种分布式选路算法。

### 静态选路算法与动态选路算法

+ **静态选路算法**中，路由的变化非常缓慢，通常是由于人工干预进行调整。

+ **动态选路算法**能够在网络流量负载或拓扑变化发生变化时改变选路路径。

### 负载敏感算法于负载迟钝算法

+ **负载敏感算法**中，链路费用会动态地变化以反应出底层链路的当前拥塞水平。

+ **负载迟钝算法**中，某条链路的费用不明显地反应当前的拥塞水平。


## 链路状态选路算法

链路状态选路算法实际上是Dijkstra算法的一个变种，在链路状态选路算法中，每个路由器都知道网络中的每一条边的代价，这可以通过链路广播来实现。

算法从一个起始节点开始。输出是从这个节点到网络中其他节点的最短路径集合。算法维护一个已访问路由集合，开始的时候只有开始节点在集合中。在循环的每次迭代中，选择最新加入集合的那一个节点，比如是N，选择与N费用最低的N的邻居，比如为M，那么就将M加入到集合中，并且找出M的邻居。