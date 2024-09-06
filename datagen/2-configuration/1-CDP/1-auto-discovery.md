---
layout: default
title: Auto Configuration 
parent: CDP Configuration
grand_parent: Configuration
has_children: false
nav_order: 1
---

# Auto Configuration with Auto-Discovery

When starting up, Datagen is loading the _application.properties_ in-memory and proceeds to what is called an auto-discovery.

When setup in CDP, Datagen (if _cm.autodiscovery_ is true) will make an auto-discovery of **ALL** services using CM API. (User does not need to specify anything).

It also possible rely on fields described as **AUTO-DISCOVERY**, that are by defaults are filled in. 

These fields, referenced properties file such as _hdfs-site.xml, hive-site.xml_ etc... 
With this, Datagen parsed these files and automatically configure all possible other fields.

Once started, you can see such logs in Datagen Web Server:


If using CM auto-discovery:

```shell
9:35:04.701 AM INFO PropertiesLoader [main] Going to auto-discover hbase.zookeeper.quorum with CM API
9:35:04.701 AM 	INFO PropertiesLoader [main] Going to auto-discover hbase.zookeeper.port with CM API
```

If not using CM auto-discovery but configuration files auto-discovery:

```shell
2022-10-13 13:33:49,220 INFO  [main] com.cloudera.frisch.randomdatagen.config.PropertiesLoader: Going to auto-discover hbase.zookeeper.quorum
2022-10-13 13:33:49,222 DEBUG [main] com.cloudera.frisch.randomdatagen.Utils: Return value: server_zk1,server_zk_2,server_zk_3 from file: dev-support/test_files/hbase-site.xml for property: hbase.zookeeper.quorum
2022-10-13 13:33:49,222 INFO  [main] com.cloudera.frisch.randomdatagen.config.PropertiesLoader: Going to auto-discover hbase.zookeeper.port
2022-10-13 13:33:49,223 DEBUG [main] com.cloudera.frisch.randomdatagen.Utils: Return value: 2181 from file: dev-support/test_files/hbase-site.xml for property: hbase.zookeeper.property.clientPort
```

# Using a specific Cloudera Manager for Auto-Discovery

If running the program locally or non CDP managed, it is still possible to specify a CM server and use auto-discovery from it to automatically configure services.

Required Configurations are the following:

- **cm.autodiscovery**=true
- **cm.url**= : URL to reach CM in the form of: https://<SERVER>:<PORT>
- **cm.user**= : user that can read configuration from CM
- **cm.password**= : password of that user
- **cm.cluster.name**= : name of the cluster in CM that will be used