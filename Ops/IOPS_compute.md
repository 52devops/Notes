## 概念
IOPS 就是每秒钟I/O的操作。  
是衡量计算机存储设备性能的一种指标。  
> 一般厂商给出的IOPS数与实际不符，因为环境不一样。 
## 测试
大多数情况下测试IOPS都是测量其"连续"和"随机"操作。  
- 连续操作
以连续的方式访问存储上的位置，并且通常与大数据的传输有关，例如128kb。  
- 随机操作
以不连续的方式访问存储设备上的位置。并且通常与小数据传输有关 例如 4kb  

HDD以及类似的机械存储设备，随机IOPS值通常取决于随机的寻道时间。  
SSD以及相关的存储设备其IOPS主要取决于网络和内存接口的速度。  
在机械和固态两种设备中，连续IOPS值(尤其适用大的block size)最能反映出存储设备的最大带宽。

## 计算
- IOPS与MB/s值转化公式如下
Bytes/s = IOPS * 传输大小(单位字节)
- IOPS
IOPS = 1 / (寻道时间+延迟)  将磁盘旋转周期的一半作为旋转延迟的近似值
- IOPS与MBps的转换
	IOPS = ( MBps 吞吐量 / 每个IO的KB ) * 1024
	MBps = ( IOPS * 每个IO的大小KB)/1024
通过提高HDDS设备的IO队列(未解决的IO)，可以提高其性能
- IO数
	Total_IO_number = IOPS * TIME
	IO_SIZE = IO * blocksize(default 4k)

## 常见不同转速的机械硬盘对不同IOPS表  rpm(Revolutions Per Minute)每分钟转速
设备|IOPS|
----|----|
5400转 SATA|  15-50IOPS|
7200转 SATA|75-100IOPS|
10000转 SATA| 125-150 IOPS|
10000转 SAS|140IOPS|
15000转 SAS|175-210IOPS|

[具体参考表可见](https://en.wikipedia.org/wiki/IOPS#Performance_characteristics)
