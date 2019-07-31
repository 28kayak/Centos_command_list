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
