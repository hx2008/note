Backup and remove
```
> db.<collection_name>.find().forEach(function(d){ db.getSiblingDB('<new_database>')['<collection_name>'].insert(d); });
$ mongoexport --db <new_database> --collection <collection_name> --out backup.json
> db.<collection_name>.remove();
```
