# HDFS

## 1.HDFS 架构
![](https://github.com/Hi-world-DF/BigDataLearning/blob/main/imgs/hdfs.png)

### 1.1 HDFS基本认识和工作模式

#### 1.1.1 HDFS基本特征：
* 1）大规模数据分布存储能力。HDFS是建立在一组分布式服务器节点的本地文件系统之上的分布式文件系统。
* 2）高并发能力。HDFS以多节点并发访问方式提供很高的数据访问带宽（高数据吞吐率），并且可以把带宽大小等比例扩展到集群的全部节点上。
* 3）容错性。多副本数据存储，心跳检测，自动恢复，确保数据不丢失。
* 4）顺序访问。大数据批处理大多情况都是大量简单数据记录的顺序处理。
* 5）简单一致性（一次写多次读）。HDFS支持大量数据一次写入，多次读取，不支持已写入数据的更新，但允许在文件末尾添加新的数据。
* 6）数据采用块形式存储。HDFS采用大粒度的数据块方式存储文件，可以减少元数据数量，且块大小固定，可以随机选择节点分布式存储。

#### 1.1.2 HDFS基本组成：NameNode和DataNode
HDFS采用主从结构，一个HDFS包括一个主控节点NameNode和一组DataNode从节点。
* NameNode是一个主服务器，用来管理整个文件系统的命名空间和元数据，以及处理外界的文件访问请求；
* NameNode保存的元数据包括：（1）命名空间（2）数据块与文件名的映射表（3）每个数据块副本的位置信息；
* 每个DataNode的数据实际存储在每个节点的本地Linux文件系统中。

## 2.HDFS 组成部分


## 3.HDFS 上传文件和下载文件流程

### 3.1 HDFS上传流程
![](https://github.com/Hi-world-DF/BigDataLearning/blob/main/imgs/hdfs_write.png)

### 3.2 HDFS下载流程
![](https://github.com/Hi-world-DF/BigDataLearning/blob/main/imgs/hdfs_read.png)
