# ELK (Elasticsearch-Logstash-Kibana)

##docker Images
`elasticsearch:7.4.1`  get [images](https://hub.docker.com/_/elasticsearch)

`kibana:7.4.1` get [images](https://hub.docker.com/_/kibana)

`logstash:7.4.1` get [images](https://hub.docker.com/_/logstash)

`elastic/filebeat:7.4.1` get [images](https://hub.docker.com/r/elastic/filebeat)

###docker volumes
    
  ` ./filebeat => /usr/share/filebeat `
  
  ` ./logstash/config => /usr/share/logstash/config`
  
  ` ./logstash/pipeline => /usr/share/logstash/pipeline `
  
  
###Work Flow

```
example : 
    nginx =>  error.log   <---listening--- filebeat  
    filebeat => logstash  ----throwing---> filter
    logstash => elasticsearch 
    kibana show   ==>>> log 
```



#####TODO

在生产环境中,filebeat 和 logstash 不会一起部署,当filebeat单独部署的时候，需要修改filebeat.yml
的 output 指向 logstash

