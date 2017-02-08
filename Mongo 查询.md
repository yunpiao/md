---
title: Mongo 查询
---
## mongo js 遍历
```bash
db.getCollection('CPU').find({}).limit(100).sort({"time":-1}).forEach(
function(a){
    a["v"]=(new Date(a["time"]).toString());
    printjson((a["v"]))
    })
```

## mongo 聚合
```bash
db.CPU.aggregate({
    $group:{_id:       
            
             {time:{ $mod: [ 4,1 ] }},
             "a":
             {$where: function() { return obj.credits - obj.debits < 0; }}
             
              
           }
    })
	
	
	db.CPU.aggregate({"$group":{"_id":{$ceil:{"$divide":["$time",60]}}}}).sum()
```	

## mongo 查询
```bash
db.getCollection('CPU').find({ $where: "this.time % 60 == 0" }).limit(360)
```

## mongo Mapreduce

```bash
db.CPU.mapReduce(
    function() {emit(this._id,this.time);},
    function(key,values) {return Array.sum(values)},
       {
           query:{},
           
           }
)
```