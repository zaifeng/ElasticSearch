####RPM方式安装
首先须确认JDK已经正确被安装
```
#rpm -ivh elasticsearch-5.1.1.rpm
```

添加服务
```
#chkconfig --add elasticsearch
```
修改集群名称`本机ip` `数据存储目录`
```
#vim /etc/elasticsearch/elasticsearch.yml
```

```
network.host: 10.127.92.43
#
# Set a custom port for HTTP:
#
http.port: 9200
```
去掉 `network` 和 `http.port` 前面的# 后面还要添加es集群名称

启动ES
```
#service elasticsearch start 启动
#service elasticsearch stop 停止
```
访问 `http://127.0.0.1:9200` 应该返回

```
{
  "name" : "p1RrFMs",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "yi5EQbb0RO-Ye6boeFu9kg",
  "version" : {
    "number" : "5.1.1",
    "build_hash" : "5395e21",
    "build_date" : "2016-12-06T12:36:15.409Z",
    "build_snapshot" : false,
    "lucene_version" : "6.3.0"
  },
  "tagline" : "You Know, for Search"
}
```
`cluster_name` 是默认的，如不指定`cluster_name`都会加入环境中的elasticsearch集群中