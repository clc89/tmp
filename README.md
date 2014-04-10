list databases
	    GET /database

drop database
	 DELETE /database?dbname=foo

get db stat
	 GET /database?dbname=foo&op=stats

list collections
	 GET /collection?dbname=foo

get col stat
	 GET  /collection?dbname=foo&op=stats&colname=test

create col
	 PUT  /collection?dbname=foo&colname=test


add record
	 PUT /write?dbname=foo&colname=test

add multi record must be separated by newline
	 PUT /write?dbname=foo&colname=test

update record, first field is condition, must be separated by newline
	POST /write?dbname=foo&colname=test

delete records with condition
	DELETE /write?dbname=foo&colname=test

read all records in collection
	GET  /query?dbname=foo&colname=test

with limit
	 GET /query?dbname=foo&colname=test&limit=3
with limit and skip
	 GET /query?dbname=foo&colname=test&limit=3&skip=3
with condition
	 GET /query?dbname=foo&colname=test -XPOST -d'{name:newfoo}'
with condition and sort
	 GET /query?dbname=foo&colname=test -XPOST --data-binary $'{name:newfoo}\n{name:1}'
only return certain fields
	 GET /query?dbname=foo&colname=test&fields=name,age
