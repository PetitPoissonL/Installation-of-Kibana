# Installation of Kibana for [Spark real-time project](https://github.com/PetitPoissonL/Spark_Streaming_Real_Time)

This README provides detailed instructions for installing and configuring Kibana on the server `hadoop102`.

## Prerequisites

- Ensure `hadoop102` is running a compatible Linux distribution.
- Elasticsearch should be installed and running on the server.
- Elasticsearch startup script: [es.sh](https://github.com/PetitPoissonL/Installation-of-Elasticsearch/blob/main/es.sh).
- Sudo or root access on the server.

## Step 1: Install Kibana
1. Download Kibana:
```
cd /opt/software/
wget https://artifacts.elastic.co/downloads/kibana/kibana-7.8.0-linux-x86_64.tar.gz
```

2. Extract Files:
```
tar -zxvf kibana-7.8.0-linux-x86_64.tar.gz -C /opt/module/
```

3. Rename Kibana in the `/opt/module` directory:
```
mv kibana-7.8.0-linux-x86_64/ kibana7
```

## Step 2: Configure Kibana
```
cd /opt/module/kibana7/config/
vim kibana.yml
```
```
#Modify the following content
server.host: "0.0.0.0"
elasticsearch.hosts: ["http://hadoop102:9200", "http://hadoop103:9200"]
```

## Step 3: Start testing
```
es.sh start
```
Access http://hadoop102:5601/ in a web browser
