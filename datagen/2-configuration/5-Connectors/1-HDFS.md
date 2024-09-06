---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# HDFS

Following configurations are required to interact with HDFS:

- **hdfs.uri**= : URI in following format: hdfs://NAMESERVICE:PORT/ (Nameservice can be replaced by Hostname of active Namenode)

Two following are required if hdfs-site.xml and core-site.xml are not in classpath or usual locations or if program is unable to solve nameservice:

- **hadoop.core.site.path**=
- **hadoop.hdfs.site.path**=

Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **hdfs.auth.kerberos**=#{kerberos.enabled}
- **hdfs.auth.kerberos.user**=#{kerberos.user}
- **hdfs.auth.kerberos.keytab**=#{kerberos.keytab}

Optional as these settings have no impact:

- **hadoop.user**=datagen
- **hadoop.home**=/user/datagen
