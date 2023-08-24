# 7.2 深圳市建筑能耗监测平台

1. 添加参数

![shenzhen1](E:\markdownFile\documents\energyPlatform\assets\shenzhen1.png)

按照平台提供的参数，填写相应的文本并保存。

其中额外参数用作根据电表状态点的值，判断电表是否在线。



2. 添加电表ID

根据实际电表和平台中计量装置的数据采集功能编号，进行电表ID的添加

![shenzhen2](E:\markdownFile\documents\energyPlatform\assets\shenzhen2.png)



3. 添加电表正向有功数据点

一般只需要上传电表的正向有功数据项，所以每个电表ID下只需要添加一个数据点

![shenzhen3](E:\markdownFile\documents\energyPlatform\assets\shenzhen3.png)

高级参数中字段：

coding必填：能耗数据分类/分项编码，根据国家导则设置

suffix选填：采集参数编号，正向有功电能为1090，如果suffix不填，则将tagCode作为suffix