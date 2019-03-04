mcf_api.md

## login
```sh
[ec2-user@mcf ~]$  curl -X POST -H "Content-Type: application/json" http://localhost:8345/mcf-api-service/json/LOGIN -d "{\"userID\":\"admin\", \"password\":\"admin\"}"
```

##Output connector
```sh
## create an output connector
curl -X PUT -H "Content-Type: application/json" http://localhost:8345/mcf-api-service/json/outputconnections/ -d  "{\"outputconnection\": {\"description\":\"solr_conn\", \"class_name\":\"Solr\"} }"


## get list of output connector 
curl -X GET  http://localhost:8345/mcf-api-service/json/outputconnections


## delete list of output connector
curl -X DELETE  http://localhost:8345/mcf-api-service/json/outputconnections/
```

##Repository Connector
```sh
##create an repository connector
curl -X PUT -H "Content-Type: application/json" http://localhost:8345/mcf-api-service/json/repositoryconnections/ -d  "{\"repositoryconnection\": {\"description\":\"DMI_conn\", \"class_name\":\"Web\"} }"

## get list of repository connector 
curl -X GET  http://localhost:8345/mcf-api-service/json/repositoryconnections

```

## Create a job'
```sh
curl -X POST -H "Content-Type: application/json" http://localhost:8345/mcf-api-service/json/jobs/ -d  "{\"repositoryconnection\": 
	{\"description\":\"job\", 
	 \"repository_connection\":\"Web\",
	 \"id\":\"dmi1\",


	} 
}"


```
