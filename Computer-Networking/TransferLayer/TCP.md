# TCP
------


## TCP连接

TCP是**面向连接**的，这是因为在一个应用进程可以开始向另一个应用进程发送数据之前，这两个进程必须先相互“握手”，即它们必须相互发送某些预备报文段，以建立确保数据传输所需要的参数。

由于TCP是工作在端系统中，所以不存在中间的网络元素，即中间要素不会维持TCP的连接状态，这就确定了TCP必须自己实现状态的保存以及维护。当客户机进程通过套接字传递数据流时，一旦数据通过该门户，它就由客户机中运行的TCP控制了。TCP将这些数据引导到该连接的**发送缓存**里，这是在三次握手的时候设置的。TCP可从缓存中取出并且放入报文段中的数据量受限于**最大报文段长**，而最大报文段长又受限于**最大传输单元**，这是链路层所允许的最大帧长度。


## TCP报文段结构

TCP报文段的首部比UDP报文段的首部长了12个字节。其结构如下：

+ **源端口号** 发送端的端口号。

+ **目的端口号** 接收端的端口号。

+ **序号** TCP把数据看成是无结构的有序字节流，如果传输的字节流超过了MSS，那么数据流将会被分割成很多个MSS，而序号就是每个MSS的首字节的字节流编号。

+ **确认号** 确认号指明了主机所期望从发送方收到的下一个字节的序号。

+ **首部长度** 由于TCP报头有可选字段，所以首部长度是必要的，这样方便计算数据的偏移量。

+ **标志字段** 标志字段有如下几个：
    * ACK _用于指示确认字段中的值是有效的。_
    * SYN _用于请求发起TCP连接。_
    * FIN _用于关闭TCP连接请求。_
    * RST _也是用于连接的建立与拆除。_
    * PSH _当这一个位被设置的时候，接收方应该立刻将数据交付给上层。_
    * URG _指明数据的紧急。_

+ **检验和**以及**紧急数据指针**


## TCP的可靠数据传输

TCP的可靠数据传输服务确保一个进程从其接受缓存中读出非损坏的，无间隔的，非冗余的和按序的数据流，即该字节流与连接的另一方端系统发送出的字节流完全一样。

TCP发送方主要处理三个方面的内容，**从上层应用程序接收数据**，**定时器超时**以及**收到ACK报文**。当从上层应用程序接收到数据的时候，TCP用nextseqnum来为该数据的分组进行编号，然后将其交给IP，如果此时定时器并没有开启，则将其开启，并更新nextseqnum的值。当定时器发生了超时，TCP将会重传引起超时的报文段，并重启计时器。当收到ACK报文的时候，TCP将窗口进行前移。由于TCP也是采用累计确认的方式，所以当收到序号为N的ACK时，可以确定序号比N要小的分组都已经发送成功，即使它们的ACK确认报文还没有到。

当TCP接收方收到一个不连续的分组时（比如具有序号N，且序号为M到N-1的分组还没有收到），接收方由于不能发送否定确认，于是就发送一个序号为M的冗余ACK，指名接收方现在还是期望着分组M的到来。当TCP发送方收到3格冗余ACK后，便会立刻执行**快速重传**。快速重传序号为M的分组。

TCP其实是GBN与SR的结合。从发送方来看，TCP只需要维护一个确认分组的最小序号，以及下一个要发送分组的序号，这是GBN的风格；但是当连续分组中有丢包出现时，TCP并不会像GBN那样将丢包以及丢包后面的所有分组重新发送，而是仅仅重新发送丢包（这是由于接收方会先将之后的不连续分组缓存起来，而发送冗余ACK通知发送方重新发送丢包分组）。


## TCP连接管理

### TCP连接建立

1. 首先，客户端向服务端发送一个请求报文，其SYN标志位为1，并选择了一个客户端起始序列号。

2. 一旦包含TCP SYN的报文段的IP数据到达服务器主机，服务器会从该数据报中提取出TCP SYN报文段，为该TCP连接分配TCP缓存和变量，并向客户机TCP发送允许连接的报文段，即SYNACK报文段。在此报文段中，服务器也附上了它选择的一个服务端起始号。

3. 在客户端收到SYNACK报文段以后，客户机也要给该连接分配缓存和变量。并且对服务端的SYNACK报文段进行确认。自此一条TCP连接就建立了。

### TCP连接拆除

以下步骤假定是客户端要求拆除连接的（其实客户端与服务端都可以发起连接的拆除）。

1. 客户端发送连接拆除请求，其FIN标志位为1。

2. 服务器收到FIN报文以后，就向客户端发送确认的报文。

3. 服务器对为这个TCP连接分配的缓存以及变量进行释放，然后发送一个FIN报文。

4. 最后客户端收到服务器发来的FIN报文以后，也对TCP连接的缓存以及变量进行释放，发送FIN的确认报文从而使TCP连接成功拆除。