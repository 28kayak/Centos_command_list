# How to set up Legacy Scaling with Solr



# Directory Structure  
## master-core
```bash
master-core
├── conf/
│   ├── lang/
│   │   ├── stoptags_ja.txt
│   ├── managed-schema
│   ├── solrconfig.xml 
│   ├── synonyms.txt 
│   └── params.json
├── data/
├── solr.xml
└── core.properites
```

## slave-core
```bash
slave-core
├── conf/
│   ├── lang/
│   │   ├── stoptags_ja.txt
│   ├── managed-schema
│   ├── solrconfig.xml 
│   ├── synonyms.txt
│   ├── synonyms.txt
│   └── params.json
├── data/
├── solr.xml
└── core.properites
```
# starting order 
When you set up a system of master-slave Apache solr cores, you must start from master-core first. 
With the running master-core and having its IP address, we need to rewrite a slave's solrconfig.xml. 
Each samples are below:
