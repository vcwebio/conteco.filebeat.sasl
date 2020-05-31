# `filebeat.sasl` - ContEco

ContEco ElasticSearch Filebeat image, with SASL authentication.
See `conteco.docs.overview` for more information on the ContEco ecosystem.

## Configuration Changes

### Entrypoint

A custom entrypoint that reads the host name the container is running on  

The `volume` configuration must include the ``/etc:/hostfs/etc:ro` mapping for this to be active.

### Parameterised `filebeat.yml` Configuration

The configuration consumes files in raw format.

## Tags

* 7.1.1
