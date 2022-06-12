
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



Result
-------------
* an example document from elastic search index created
```
{
  "_index": "test-elk-0",
  "_id": "ht1RWIEBS_h6FS1HKd_s",
  "_version": 1,
  "_score": 1,
  "_source": {
    "level": "INFO",
    "log": {
      "file": {
        "path": "/var/logs/app_json.log"
      },
      "offset": 31802
    },
    "spanId": "cb9f0fc1623639a0",
    "message": "this is a test request",
    "@timestamp": "2022-06-12T14:28:39.993Z",
    "env": "staging",
    "logger_name": "com.mevl.elk.TestController",
    "@version": "1",
    "agent": {
      "type": "filebeat",
      "ephemeral_id": "755b9d93-b5a0-4470-be84-e5a34fb6df6c",
      "version": "8.2.2",
      "id": "5b53e2c9-9e6b-48b1-b966-63f52beddabb",
      "name": "test-elk"
    },
    "input": {
      "type": "filestream"
    },
    "level_value": 20000,
    "host": {
      "os": {
        "type": "linux",
        "version": "20.04.4 LTS (Focal Fossa)",
        "family": "debian",
        "platform": "ubuntu",
        "name": "Ubuntu",
        "kernel": "5.13.0-1029-azure",
        "codename": "focal"
      },
      "containerized": false,
      "architecture": "x86_64",
      "mac": [
        "00:0d:3a:d2:51:a8",
        "00:0d:3a:d2:51:a8"
      ],
      "name": "test-elk",
      "ip": [
        "10.0.0.4",
        "fe80::20d:3aff:fed2:51a8"
      ],
      "hostname": "test-elk",
      "id": "033973c8052a4cd9a01f6e5bada673b5"
    },
    "tags": [
      "beats_input_codec_plain_applied"
    ],
    "userId": "4856760e-282f-4d9a-ba6a-75eb838458ae",
    "ecs": {
      "version": "8.0.0"
    },
    "application": "elk",
    "traceId": "cb9f0fc1623639a0",
    "event": {
      "original": "this is a test request"
    },
    "thread_name": "http-nio-8080-exec-5"
  }
}
```

Maintainers
-----------

* Mevlana - https://github.com/mevlanaayas
