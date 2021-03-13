## write db tables into liquibase xml file
```
liquibase \
--driver=com.mysql.cj.jdbc.Driver \
--classpath="/Users/nijat.aghayev/Custom/liquibase_drivers/mysql-connector-java-8.0.23.jar" \
--url="jdbc:mysql://localhost:3306/thymeleaf_test?autoReconnect=true&useSSL=FALSE" \
--changeLogFile=dbchangelog-1.0.xml \
--username=root \
--password=root1991 \
generateChangeLog 
```



## write changesets into database 
```
liquibase update
```


## write changesets into database (using different property file)
```
liquibase --defaultsFile=psql.properties update
```


## diff the difference (referenceUrl diff url) to new-changelog.xml (dbchangelog-3.0.xml file will be created automatically)
```
liquibase --defaultsFile=liquibase-mysql-mysql.properties diffChangeLog
```


### You can not migrate from one database into another one (e.g. from mysql to postgresql). You have to `generateChangeLog` with mysql connection properties and then adjust .xml file and call `update` with postgresql connection properties
