
# My Stuff
## SQL
```python
python3 -m mssqlcli.main
k247 for sa


Declare @JSON varchar(max) SELECT @JSON=BulkColumn FROM OPENROWSET (BULK '/home/sanodariya_1/users.json', SINGLE_CLOB) import SELECT * FROM OPENJSON (@JSON)

DECLARE @sql varchar(1000)

SET @sql = 'bcp "SELECT * FROM [user] ' +
    'FOR JSON PATH, INCLUDE_NULL_VALUES" ' +
    'queryout  "/home/sanodariya_1/user_sql.json" ' +
    '-c -S MACWIN2 -d WideWorldImporters -T'

EXEC sys.XP_CMDSHELL @sql

GO

```

```sql
SELECT * FROM [user] FOR JSON PATH INCLUDE_NULL_VALUES
GO

+---------------------------------------------+
| JSON_F52E2B61-18A1-11d1-B105-00805F49916B   |
|---------------------------------------------|
| [{"name":"kshitij"}]                        |
+---------------------------------------------+

SELECT * FROM [user] FOR JSON AUTO, INCLUDE_NULL_VALUES
GO

%%
SELECT 
    CONCAT("[",
        CONCAT("{name:'",name,"'}")
    ,"]") 
AS json FROM user
%%

```sql
EXEC master xp_cmdshell'bcp "SELECT * FROM [user]" queryout "text.txt" -c -T -x'

```sql
EXEC master..xp_cmdshell 'bcp "SELECT * FROM [user]" queryout "text.txt" -c -T -x'
```
```




```

## Import to SQL
```sql
SELECT * FROM OPENROWSET (BULK '/home/sanodariya_1/users.json', Single_CLOB) AS import;


SELECT * FROM OPENROWSET (BULK 'C:\Users\azadk\Downloads\users.json', Single_CLOB) AS import;

```

## MongoDB

`mongoexport collection db filename`

```javascript
mongo admin -u admin -p 'password'

db.posts.find()

mongoexport -u admin -p "password" --collection=users --db=admin --out=users_exported.json

mongoimport -u admin -p "password" --collection=users --db=admin --type=json --file "/home/sanodariya_1/users_final.json"
```

```mongoDB




mongoimport --host=127.0.0.1 -d database_name -c collection_name --type csv --file csv_location --headerline

```






## 2021-09-24

### Install Microsoft SQL Server on Debian

Short howto on how to best install MSSQL on Debian (bullseye). Based on [Microsoft's documentation for Ubuntu](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver15).

Import the public repository GPG keys:

`curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -`

Register the Microsoft SQL Server Ubuntu repository for SQL Server 2019:

`curl https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2019.list | sudo tee /etc/apt/sources.list.d/mssql-server.list`

Install SQL Server

`sudo apt update   sudo apt-get install mssql-server`

Run setup

`sudo /opt/mssql/bin/mssql-conf setup`

If you plan to connect remotely, you might also need to open the SQL Server TCP port (default 1433) on your firewall.

Next, we'll install the client tools. First add the repository:

`curl https://packages.microsoft.com/config/ubuntu/21.04/prod.list | sudo tee /etc/apt/sources.list.d/msprod.list`

Next, install the tools

`sudo apt update   sudo apt install mssql-tools`

The sqlcmd command is installed to /opt/mssql-tools/bin/. To ensure that the command is available on your default PATH environment, create a symbolic to /usr/bin/ 

`sudo ln -s /opt/mssql-tools/bin/sqlcmd /usr/bin/`

That's it! Give the mssql-server a quick restart for good meausure and you're good to go!

`sudo service mssql-server restart`

Posted by [RobIII](https://www.blogger.com/profile/04573618019707966117 "author profile") at [11:39](https://blog.robiii.nl/2021/09/install-microsoft-sql-server-on-debian.html "permanent link") 

[Email This](https://www.blogger.com/share-post.g?blogID=8639202304732503665&postID=1588110287015090131&target=email "Email This")[BlogThis!](https://www.blogger.com/share-post.g?blogID=8639202304732503665&postID=1588110287015090131&target=blog "BlogThis!")[Share to Twitter](https://www.blogger.com/share-post.g?blogID=8639202304732503665&postID=1588110287015090131&target=twitter "Share to Twitter")[Share to Facebook](https://www.blogger.com/share-post.g?blogID=8639202304732503665&postID=1588110287015090131&target=facebook "Share to Facebook")[Share to Pinterest](https://www.blogger.com/share-post.g?blogID=8639202304732503665&postID=1588110287015090131&target=pinterest "Share to Pinterest")

Labels: [Debian](https://blog.robiii.nl/search/label/Debian), [Linux](https://blog.robiii.nl/search/label/Linux), [SQL Server](https://blog.robiii.nl/search/label/SQL%20Server)

## Labels

[C#](https://blog.robiii.nl/search/label/C%23) [Entity Framework](https://blog.robiii.nl/search/label/Entity%20Framework) [ErrorCodes](https://blog.robiii.nl/search/label/ErrorCodes) [SQL Server](https://blog.robiii.nl/search/label/SQL%20Server) [ssl](https://blog.robiii.nl/search/label/ssl) [tls](https://blog.robiii.nl/search/label/tls) [18650](https://blog.robiii.nl/search/label/18650) [802.11r](https://blog.robiii.nl/search/label/802.11r) [CIDR](https://blog.robiii.nl/search/label/CIDR) [Captcha](https://blog.robiii.nl/search/label/Captcha) [Controller](https://blog.robiii.nl/search/label/Controller) [Data Protection](https://blog.robiii.nl/search/label/Data%20Protection) [Debian](https://blog.robiii.nl/search/label/Debian) [Dependency Injection](https://blog.robiii.nl/search/label/Dependency%20Injection) [Error codes](https://blog.robiii.nl/search/label/Error%20codes) [Exceptions](https://blog.robiii.nl/search/label/Exceptions) [IBM](https://blog.robiii.nl/search/label/IBM) [IDataProtectionProvider](https://blog.robiii.nl/search/label/IDataProtectionProvider) [IDataProtector](https://blog.robiii.nl/search/label/IDataProtector) [IP Address](https://blog.robiii.nl/search/label/IP%20Address) [IPNetwork](https://blog.robiii.nl/search/label/IPNetwork) [Linux](https://blog.robiii.nl/search/label/Linux) [MQ](https://blog.robiii.nl/search/label/MQ) [MongoDB](https://blog.robiii.nl/search/label/MongoDB) [MongoVue](https://blog.robiii.nl/search/label/MongoVue) [Network](https://blog.robiii.nl/search/label/Network) [Ordering](https://blog.robiii.nl/search/label/Ordering) [Reason codes](https://blog.robiii.nl/search/label/Reason%20codes) [ReasonCodes](https://blog.robiii.nl/search/label/ReasonCodes) [Sorting](https://blog.robiii.nl/search/label/Sorting) [Swagger](https://blog.robiii.nl/search/label/Swagger) [Swashbuckle](https://blog.robiii.nl/search/label/Swashbuckle) [TimerWheel](https://blog.robiii.nl/search/label/TimerWheel) [UX](https://blog.robiii.nl/search/label/UX) [Udemy](https://blog.robiii.nl/search/label/Udemy) [WebSphere](https://blog.robiii.nl/search/label/WebSphere) [a/c](https://blog.robiii.nl/search/label/a%2Fc) [ac](https://blog.robiii.nl/search/label/ac) [aircon](https://blog.robiii.nl/search/label/aircon) [airconditioner](https://blog.robiii.nl/search/label/airconditioner) [airconditioning](https://blog.robiii.nl/search/label/airconditioning) [battery shield](https://blog.robiii.nl/search/label/battery%20shield) [certificate](https://blog.robiii.nl/search/label/certificate) [courses](https://blog.robiii.nl/search/label/courses) [diymore](https://blog.robiii.nl/search/label/diymore) [e-learning](https://blog.robiii.nl/search/label/e-learning) [e110s](https://blog.robiii.nl/search/label/e110s) [e110se](https://blog.robiii.nl/search/label/e110se) [e125s](https://blog.robiii.nl/search/label/e125s) [electronics](https://blog.robiii.nl/search/label/electronics) [fast bss transition](https://blog.robiii.nl/search/label/fast%20bss%20transition) [forward secrecy](https://blog.robiii.nl/search/label/forward%20secrecy) [hack](https://blog.robiii.nl/search/label/hack) [haori](https://blog.robiii.nl/search/label/haori) [https](https://blog.robiii.nl/search/label/https) [kazumi](https://blog.robiii.nl/search/label/kazumi) [learning](https://blog.robiii.nl/search/label/learning) [module](https://blog.robiii.nl/search/label/module) [ninebot](https://blog.robiii.nl/search/label/ninebot) [openssl](https://blog.robiii.nl/search/label/openssl) [poodle](https://blog.robiii.nl/search/label/poodle) [rc4](https://blog.robiii.nl/search/label/rc4) [rdp](https://blog.robiii.nl/search/label/rdp) [scooter](https://blog.robiii.nl/search/label/scooter) [segway](https://blog.robiii.nl/search/label/segway) [sha1](https://blog.robiii.nl/search/label/sha1) [speed limit](https://blog.robiii.nl/search/label/speed%20limit) [toshiba](https://blog.robiii.nl/search/label/toshiba) [troubleshooting](https://blog.robiii.nl/search/label/troubleshooting) [unlock](https://blog.robiii.nl/search/label/unlock) [wifi](https://blog.robiii.nl/search/label/wifi) [wifi not connecting](https://blog.robiii.nl/search/label/wifi%20not%20connecting)

©2012 - 2018 RobIII. Powered by [Blogger](https://www.blogger.com/).