---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# KAFKA

Following configurations are required to interact with Kafka:

- **kafka.brokers**= : Kafka list of brokers as: KAFKA_SERVER_1:KAFKA_PORT,KAFKA_SERVER_2:KAFKA_PORT
- **kafka.security.protocol**= : Kafka protocol among: PLAINTEXT, SASL_PLAINTEXT, SASL_SSL, SSL

Following configurations are required to interact with Kafka if using AVRO as message type:

- **schema.registry.url**= : Schema Registry URL as: SR_SERVER:SR_PORT


Optional to specify how to discover Kafka and Schema Registry using their configuration file:

- **kafka.conf.client.path**=
- **schema.registry.conf.path**=


Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **kafka.auth.kerberos.keytab**=#{kerberos.keytab}
- **kafka.auth.kerberos.user**=#{kerberos.user}

Required only if TLS is activated: (It is advised to let these values, so this is controlled by main parameter on TLS)

- **kafka.keystore.locatio**n=#{keystore.location}
- **kafka.truststore.location**=#{truststore.location}
- **kafka.keystore.password**=#{keystore.password}
- **kafka.keystore.key.password**=#{keystore.password}
- **kafka.truststore.password**=#{truststore.password}
- **schema.registry.tls.enabled**=#{tls.enabled}

Two below properties should not be changed, except under special circumstances:

- **kafka.sasl.mechanism**=GSSAPI
- **kafka.sasl.kerberos.service.name**=kafka
