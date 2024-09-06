---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# HBASE

Following configurations are required to interact with HBase:

- **hbase.zookeeper.quorum**= : Zookeeper servers separated by a ',', like this: ZK_SERVER_1,ZK_SERVER_2,ZK_SERVER_3
- **hbase.zookeeper.port**= : Zookeeper port
- **hbase.zookeeper.znode**= : Znode for HBase like: ZNODE

Optional to specify how to discover HBase using hbase-site.xml file:

- **hadoop.hbase.site.path**=

Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **hbase.auth.kerberos**=#{kerberos.enabled}
- **hbase.security.user**=#{kerberos.user}
- **hbase.security.keytab**=#{kerberos.keytab}
