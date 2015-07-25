# dockering/elasticsearch

### Summary

Elastic search using Oracle JRE 8.

### Base image

[dockering/oracle-java8](https://github.com/andyvl/dockering/tree/develop/oracle-java8)


### Execution

Run a container using the following command:

    docker run -d -p 9200:9200 -p 9300:9300 dockering/elasticsearch

One can mount the elastic-search data directory (containing data, log, plugins) on a host directory  

    docker run -d -p 9200:9200 -p 9300:9300 -v <host-dir>:/data dockering/elasticsearch
