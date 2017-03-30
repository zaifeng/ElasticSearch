### 更新现有所有副本数量

```
PUT index_name/_settings
{
    "index" : {
        "number_of_replicas":5
    }
}
```



根据实际需求修改 **索引名称** 和 **副本数量**