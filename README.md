Run mysql in docker:

`docker run --name mysql -e MYSQL_ROOT_PASSWORD=password -p 3306:3306 -d mysql`

Mysql test databases:
https://dev.mysql.com/doc/index-other.html
https://github.com/datacharmer/test_db

Import data:
`mysql -u root -p --host 127.0.0.1 test < employees.sql`

Slow query log settings:
`SHOW VARIABLES LIKE 'slow%'`
`SHOW VARIABLES LIKE 'long_query%'`

Enable slow query log and log every query:
`set GLOBAL slow_query_log = 'ON';`
`set long_query_time = 0;`


Execute commnad in docker container (launch bash):
`docker exec -ti mysql bash`

Slow query log:
https://dev.mysql.com/doc/refman/8.3/en/slow-query-log.html

Copy slow log from container to local machine:
`docker cp mysql:/var/lib/mysql/slow.log .`

Mysql profile:
https://dev.mysql.com/doc/refman/8.0/en/performance-schema-query-profiling.html
