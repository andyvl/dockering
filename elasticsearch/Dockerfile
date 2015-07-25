## Elastic search image ##
#  dockering/elasticsearch
#
## https://github.com/andyvl/dockering ##

FROM dockering/oracle-java8

# Set the WILDFLY_VERSION env variable
ENV ELASTICSEARCH_VERSION 1.7.0

# Download and extract elasticsearch in $HOME directory
RUN \
  cd $HOME && \
  curl https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-$ELASTICSEARCH_VERSION.tar.gz | tar zx && \
  ln -s $HOME/elasticsearch-$ELASTICSEARCH_VERSION $HOME/elasticsearch && \
  rm -f elasticsearch-$ELASTICSEARCH_VERSION.tar.gz

# Copy elasticsearch settings
ADD config/elasticsearch.yml $HOME/elasticsearch/config/elasticsearch.yml

# Create /data directory and make it mountable
RUN mkdir /data
VOLUME ["/data"]

# Expose ports.
EXPOSE 9200
EXPOSE 9300

# Define working directory.
WORKDIR /data

# Define default command.
CMD ["$HOME/elasticsearch/bin/elasticsearch"]
