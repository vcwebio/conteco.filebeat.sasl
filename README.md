# `filebeat.base` - ContEco

Filebeat Base image, with templated default configuration.
See `conteco.docs.overview` for more information on the ContEco ecosystem.

## Configuration Changes

### Entrypoint

A custom entrypoint that reads the host name the container is running on  

The `volume` configuration must include the ``/etc:/hostfs/etc:ro` mapping for this to be active.

### Parameterised `filebeat.yml` Configuration

The configuration consumes files in raw format.

Below is a list of the environment variables exposed by the configuration.  
It is always followed by its default value.
```bash
# file path to monitor, single value or array
CONTECO_DC_FILEBEAT_ENVIRONMENT_FILEPATHS='/var/log/*.log'

# enabling console, ElasticSearch or Kafka output
# only one output can be enabled
ES_FILEBEAT_OUTPUT_CONSOLE=false
ES_FILEBEAT_OUTPUT_ELASTICSEARCH=false
ES_FILEBEAT_OUTPUT_KAFKA=false

# active when ElasticSearch output is enabled
# comma delimited list of ElasticSearch hosts
ES_FILEBEAT_OUTPUT_ELASTICSEARCH_HOSTS="elasticsearch:9200"
# kibana host to load the preconfigured dashboards
ES_FILEBEAT_OUTPUT_KIBANA_HOST="kibana:5601"
# flag to enable dashboard loading
ES_FILEBEAT_OUTPUT_KIBANA_DASHBOARDS=false

# active when Kafka output is enabled
# comma delimited list of Kafka hosts
ES_FILEBEAT_OUTPUT_KAFKA_HOSTS="kafka:9092"
# name of Kafka output topic
ES_FILEBEAT_OUTPUT_KAFKA_TOPIC=es_filebeat_kafka
```

## Tags

* 7.1.1
