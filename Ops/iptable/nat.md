# 概念
NAT是一个或多个主机共享一个IP地址的一个解决方案。比如一个由5-10个client组成的本地网络,将默认网关设为NAT Server。  
NAT server通过转换不同地址发来的包的目的地址和原地址。NAT server收到包，并且重写其源或目的地址，并且重新计算包的校验码。  
NAT功能中最常用的一个功能就是SNAT。通常，会在不能提供足够多的公网地址时使用。在本地使用一个私有地址段然后使用SNAT功能将这个段的对外包进行处理，使者5-10个client或者更多的client来共享一个公网地址  
有了SNAT，当然也有DNAT,用来做目的地址转换。可以使用这个功能,在一个小型的公司服务器上运行一个webserver和ftp server，然后使用一台物理隔离的机器为在家或在公司的员工提供不同的聊天服务。  
除了上述的功能，还有一个port NAT称为PNAT。  
# 不足
NAT功能的主要问题就是不是所有应用能使用它，幸运的是，这些应用都是不常见的。  
第二个问题就是可能有部分复杂的协议和应用是不支持的  
# NAT的例子
## 前提
2个不同的网络通过一个NAT服务与一个公网进行连接，并且希望这两个网络能够相互连通。相同的网络中也能够互相访问并且上网。  
## 为什么要有专门的NAT机器
NAT非常吃资源。一个1-10个用户的网络，需要486及32MB内存才足够。  
除此之外，还要考虑到网卡，要通过NAT机器连接到几个网络，要插几个网卡。通常都是Internet连接。如果连接到因特网，name就需要两张网卡。
这就是比较复杂的计算情况，不过只有在非常大型的网络才会用到  

