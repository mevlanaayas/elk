
ELK Stack - Spring Boot
---------------------

* Introduction
* Testing
* Dependencies
* Installation
* Configuration

Introduction
------------
this project is a sample app to demonstrate spring boot logging with elk stack
* filebeat will listen for changes on given file
  * it will push changes to logstash
* logstash responsible from parsing message and passing it to elastic search
* with kibana we can create a data view and search results in our structured logs

Testing
------------
```
curl localhost:8080/test
```

Dependencies
------------

```
Spring Boot
Logback + Jackson   => structured logging 
Lombok              => 
Sleuth              => to inject request tracing fields (trace id etc.) to logs
Actuator            => testing/health checking
```

Installation
-------------
* install filebeat
``` 
https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-installation-configuration.html
```
* install logstash
``` 
https://www.elastic.co/guide/en/logstash/current/installing-logstash.html
```
* install elasticsearch
``` 
https://www.elastic.co/guide/en/elasticsearch/reference/current/targz.html#install-linux
```
or
``` 
https://cloud.elastic.co/registration
```
or
``` 
https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started.html
```
* install kibana (optional)

Configuration
-------------

``` 
check elk-configs folder
```

Maintainers
-----------

* Mevlana - https://github.com/mevlanaayas
