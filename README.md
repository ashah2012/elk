# elk


```
cd elasticsearch-7.4.2\bin
.\elasticsearch.bat

.\elasticsearch.bat -E path.data=data2 -E path.logs=log2
.\elasticsearch.bat -E path.data=data3 -E path.logs=log3
```

curl -X GET "localhost:9200/_cat/health?v&pretty"

curl -X PUT "localhost:9200/customer/_doc/1?pretty" -H 'Content-Type: application/json' -d'
{
  "name": "John Doe"
}
'


Response -
{
  "_index" : "customer",
  "_type" : "_doc",
  "_id" : "1",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 2,
    "successful" : 2,
    "failed" : 0
  },
  "_seq_no" : 26,
  "_primary_term" : 4
}

curl -X GET "localhost:9200/customer/_doc/1?pretty"
{
  "_index" : "customer",
  "_type" : "_doc",
  "_id" : "1",
  "_version" : 1,
  "_seq_no" : 26,
  "_primary_term" : 4,
  "found" : true,
  "_source" : {
    "name": "John Doe"
  }
}


