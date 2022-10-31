
## Export from SQL server

```sql
SELECT '[{"name":' + name + '}]' FROM [USER] AS JSON
```

Manually save it to a file.

## Import to SQL
```sql
SELECT * FROM OPENROWSET (BULK '/home/sanodariya_1/users.json', Single_CLOB) AS import;

output 
+-------------------------------------------------------------+
| BulkColumn                                                  |
|-------------------------------------------------------------|
| {"_id":{"$oid":"6328bca5e99f2384ea2e82c0"},"name":"kshitij"}|
+-------------------------------------------------------------+

Declare @JSON varchar(max)
SELECT @JSON=BulkColumn
FROM OPENROWSET (BULK '/home/sanodariya_1/users.json', SINGLE_CLOB) import
SELECT * FROM OPENJSON (@JSON)
WITH  (
   [_id] varchar(200),  
   [name] varchar(20) );
```


## Download exported file 

```
path: /home/sanodariya_1/users.json


```
