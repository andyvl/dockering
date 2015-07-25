# dockering/wildfly

### Summary

JBoss Wildfly `8.2.0.Final` using Oracle JRE 8. Installs a vanilla Wildfly and
start it with its `standalone.xml` configuration.


### Base image

[dockering/oracle-java8](https://github.com/andyvl/dockering/tree/develop/oracle-java8)


### Execution

Run a container using the following command:

    docker run -d -p 8080:8080 -p 9990:9990 dockering/wildfly


There is an option to mount in the host system the Wildfly directories for
`deployments` and `logging` for convenience:

    docker run -d -p 8080:8080 -p 9990:9990 -v $HOME/dev/docker/wildfly/deployments:/opt/jboss/wildfly/standalone/deployments -v $HOME/dev/docker/wildfly/log:/opt/jboss/wildfly/standalone/log dockering/wildfly

This will make Wildfly running in a new container to listen on `8080` for application requests and on port `9990` for administration requests. Administration concole may be reached at http://localhost:9990 and can be accessed using account `admin/admin`


A docker-compose YAML file that you can adjust to your needs is also supplied in order to avoid
specifying lengthy volume options. You may download the [docker-compose.yml](https://github.com/andyvl/dockering/tree/develop/wildfly/docker-compose.yml) and invoke:

    docker-compose up
