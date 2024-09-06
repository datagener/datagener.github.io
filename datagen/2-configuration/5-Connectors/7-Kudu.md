---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# KUDU

Following configurations are required to interact with Kudu:

- **kudu.master.server**= : Kudu masters servers as: KUDU_MASTER_1:KUDU_PORT,KUDU_MASTER_2:KUDU_PORT,KUDU_MASTER_3:KUDU_PORT

Optional to specify how to discover Kudu using its configuration file:

- **kudu.conf.path**=

Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **kudu.auth.kerberos**=#{kerberos.enabled}
- **kudu.security.user**=#{kerberos.user}
- **kudu.security.keytab**=#{kerberos.keytab}

Required only if TLS is activated: (It is advised to let these values, so this is controlled by main parameter on TLS)

- **kudu.truststore.location**=#{truststore.location}
- **kudu.truststore.password**=#{truststore.password}
