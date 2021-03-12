## Mongo Shell Commands

Launch mongo shell

```console
$ mongo
```

Test connection to default DB

```console
> db
test
>
```

Show DBs

```console
> show dbs
admin          0.000GB
airbnb         0.051GB
config         0.000GB
local          0.000GB
>
```

Switch to another DB/or create empty one

```console
> use sample
switched to db sample
>
```

Create collectiion

```console
> db.tutorial
sample.tutorial
>
```

DB and collections are created *lazily*, ie. only when you inserted document.

Insert document

```console
db.tutorial.insertOne({
"theaterId" : 1000,
    "location" : {
        "address" : {
            "street1" : "340 W Market",
            "city" : "Bloomington",
            "state" : "MN",
            "zipcode" : "55425"
        },
        "geo" : {
            "type" : "Point",
            "coordinates" : [ 
                -93.24565, 
                44.85466
            ]
        }
    }
})
```



