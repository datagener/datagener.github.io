---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# SOLR

Following configurations are required to interact with SolR:

- **solr.zookeeper.quorum**= : Zookeeper quorum with port like this: ZK_SERVER_1:ZK_PORT,ZK_SERVER_2:ZK_PORT,ZK_SERVER_3:ZK_PORT
- **solr.zookeeper.znode**= : Zookeeper znode for SolR like: /ZNODE

Optional to specify how to discover SolR using solr-env.sh file:

- **solr.env.path**=

Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **solr.auth.kerberos**=#{kerberos.enabled}
- **solr.auth.kerberos.keytab**=#{kerberos.keytab}
- **solr.auth.kerberos.user**=#{kerberos.user}

Required only if TLS is activated: (It is advised to let these values, so this is controlled by main parameter on TLS)

- **solr.tls.enabled**=#{tls.enabled}
- **solr.truststore.location**=#{truststore.location}
- **solr.truststore.password**=#{truststore.password}
- **solr.keystore.location**=#{keystore.location}
- **solr.keystore.password**=#{keystore.password}
