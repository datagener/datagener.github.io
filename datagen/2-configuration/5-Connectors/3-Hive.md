---
layout: default
title: Hive
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 4
---

# HIVE

Following configurations are required to interact with Hive:

- **hive.zookeeper.quorum**= : Zookeeper quorum with port like this: ZK_SERVER_1:ZK_PORT,ZK_SERVER_2:ZK_PORT,ZK_SERVER_3:ZK_PORT
- **hive.zookeeper.znode**= : Zookeeper znode for hive like: ZNODE

Optional to specify how to discover Hive using hive-site.xml file:

- **hadoop.hive.site.path**=

Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **hive.auth.kerberos**=#{kerberos.enabled}
- **hive.security.user**=#{kerberos.user}
- **hive.security.keytab**=#{kerberos.keytab}

Required only if TLS is activated: (It is advised to let these values, so this is controlled by main parameter on TLS)

- **hive.truststore.location**=#{truststore.location}
- **hive.truststore.password**=#{truststore.password}

