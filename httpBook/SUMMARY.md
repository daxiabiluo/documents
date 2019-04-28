
# HTTP接口文档 #

## 1) 实时数据 ##


### 接口功能：

>获取此时网关中所有采集点的实时数据

###URL（获取实时数据地址）：

>http://192.168.0.12/API/V1/real(192.168.0.12为需要查询的网关的ip地址)

###HTTP请求方式：

>HTTP post

### 请求参数:

>无参数

### 返回结果格式:

>JSON

### 返回结果字段:
|返回字段       |字段类型         |字段返回值            |说明           |
| -------------|:--------------:|:--------------:|:--------------:|
|deviceCode|string||tag点所属的设备名|
|tagCode|string||tag点的名称|
|val |string||tag点的数据|
|status|string|Good/Error|tag点的数据质量|
|timestamp|timestamp|1537007573|tag点采集的时间戳|
|description|string||tag点的描述信息|


### 返回结果示例:

>[
{"status":"Good","val":"999.36","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0001","description":""},
{"status":"Good","val":"2.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0002","description":""},
{"status":"Good","val":"3.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0003","description":""},
{"status":"Good","val":"4.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0004","description":""}]


### Postman截图:
![real](C:\Users\Administrator\Desktop\http 接口文档\real.png)



## 2) 历史数据

###接口功能：

> 获取请求参数timestamp之后24小时的数据

###URL（获取历史数据地址）：

>http://192.168.0.12/API/V1/history(192.168.0.12为需要查询的网关的ip地址)

###HTTP请求方式：

>HTTP post，form-data

### 请求参数:

|字段名称       |字段类型         |必填          |说明           |
| -------------|:--------------:|:--------------:|:--------------:|
|deviceCode|string|2018-05-22 00:00:00|查询的起始时间|

### 返回结果格式:

>JSON

### 返回结果字段:
|返回字段       |字段类型         |字段返回值            |说明           |
| -------------|:--------------:|:--------------:|:--------------:|
|deviceCode|string||tag点所属的设备名|
|tagCode|string||tag点的名称|
|val |string||tag点的数据|
|status|string|Good/Error|tag点的数据质量|
|timestamp|timestamp|1537007573|tag点采集的时间戳|
|ontime|timestamp|1537007573|Tag点存储的时间戳|
|description|string||tag点的描述信息|

### 返回结果示例:
>
>[
{"status":"Good","val":"999.36","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0001","description":"", "ontime": 1537021846},
{"status":"Good","val":"2.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0002","description":"", "ontime": 1537021846},
{"status":"Good","val":"3.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0003","description":"", "ontime": 1537021846},
{"status":"Good","val":"4.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0004","description":"", "ontime": 1537021846},
{"status":"Good","val":"5.00","timestamp":1537007573,"deviceCode":"Device_1",
"tagCode":"tag0005","description":"", "ontime": 1537021846}]


### Postman截图:
![history](C:\Users\Administrator\Desktop\http 接口文档\history.png)




## 3) 写操作

###接口功能：

> 进行单个采集点的写操作

###URL（进行写操作地址）：

>http://192.168.0.12/API/V1/ctrlRequest(192.168.0.12为需要进行写操作的网关的ip地址)

###HTTP请求方式：

>HTTP post，raw

### 请求参数:

|字段名称       |字段类型         |必填          |说明           |
| -------------|:--------------:|:--------------:|:--------------:|
|id|string|Device_1.tag0001|指明进行写操作的采集点|
|val|string|10|需要写入的值|

### 返回结果格式:

>string

### 返回结果:
HTTP通讯成功返回结果都为true，指明网关接收到发送的写操作的数据。

### Postman截图:
![write](C:\Users\Administrator\Desktop\http 接口文档\write.png)