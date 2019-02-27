#  Manifold CF 
## Build by Apache ANT

1. バージョンを確認する
```sh
$ ant -version

Apache Ant(TM) version 1.10.5 compiled on July 10 2018
```
2. unpackとインストール lib artifact 
```sh
 ant make-core-deps
 ant make-deps
 ant build 
```
3. Run MCF
```sh
cd dist/example 
"$JAVA_HOME/bin/java" –jar start.jar 
```
If you want to run as debug mode, then you will do the following command.
```sh
java -jar -Xrunjdwp:transport=dt_socket,server=y,suspend=y,address=1044 start.jar
```
## About MCF Connector
MCF has 4 kinds of connectors. 
1.  Repository Connector 
2.  Output Connector 
3.  Transformer Connector
4.  Notification Connector 
These connectors have different roles to crawling and injecting data to other software. 
### Repository Connector 
A Repository connector is where you define an input data source. More specifically, what kind of source do you want to crawl. 
In this connector, you will define:
- what kind of data source (select one)
	- Alfresco webscript 
	- AmazonS3 
	- CMIS
	- Confluence 
	- Documentum
	- DropBox
	- Email
	- File system
	- File Net
	- Generic (origin of api call)
	- Google Drive 
	- GridFS
	- HDFS
	- JDBC
	- JIRA
	- Meridio
	- Nuxeo 
	- RSS
	- Sharepoint
	- Web
	- Wiki
- you will need to fulfill specific information for the Repository Connector of your choice. 

> In Repository Connector, you are not going to define the actual URL for your crawling task. So, you can re-use repository connector if you want to craw the same kind of repository.  

### Output Connector 
Output Connector, just as you read so, is to define the destination of your data. 
 


### Transformer Connector

### Notification Connector


### Jobs 
## Inclusion / Exclusion 
If you have an extension that you do not want to crawler, then you can restrict them.
```sh
.+\.ai
.+\.aif
.+\.aiff
```


## Observe logs
To print Solr's log, then you should go `sever/logs`  and run the following command.
```sh
#コンソール上にログを表示する。
tail -f logfilename.log 
```
If you want to look specifically at Solr's request logs from MCF, then your command will be like:
```sh
tail -f request.20yy_mm_dd.log
```

## Reference 
- [MCFの基本的な使い方](https://qiita.com/makaishi2/items/3c101c2494be4e119402) 
- [TransformarConnectorについて](https://www.mico-project.eu/manifoldcf-mico-transformation-connectors/)






> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjc4NzM0MjEzXX0=
-->