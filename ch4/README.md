# 第四章 数据存储

LMGateway网关具备数据存储功能，这种功能可以实现I/O点、用户点、计算点和系统点的数据存储，网关的数据只能存储到TF卡当中。（TF卡仅支持FAT32格式）

数据存储会在TF卡中新建一个名为history的文件夹，每隔一天生成一个新的数据库文件，当存储空间不足时，会将最早的一个数据库文件删除。

数据库文件可通过GC上传至用户指定目录，也可直接取出TF卡获取数据库文件（建议：网关断电后进行插拔TF卡操作）。

该数据库文件可以直接通过sqlite工具打开。