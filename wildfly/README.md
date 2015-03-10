# dockering/wildfly

### Summary

JBoss wildfly running on Oracle Java 8.


### Base image

[dockering/oracle-java8](https://github.com/andyvl/dockering/)


### Execution

Run a container using the following command:

  `docker run -d -p 8080:8080 -p 9990:9990 -v /home/andy/apps/wildfly:/opt/jboss/wildfly dockering/wildfly`
