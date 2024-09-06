---
layout: default
title: HDFS
parent: Connectors
grand_parent: Configuration
has_children: false
nav_order: 1
---

# OZONE

Following configurations are required to interact with Ozone:

- **ozone.service.id**=

Following is required to have ozone-site.xml if it is not in classpath or usual locations or if program is unable to solve nameservice:

- **hadoop.ozone.site.path**=


Required only if KERBEROS is activated: (It is advised to let these values, so this is controlled by main parameter on kerberos)

- **ozone.auth.kerberos**=#{kerberos.enabled}
- **ozone.auth.kerberos.user**=#{kerberos.user}
- **ozone.auth.kerberos.keytab**=#{kerberos.keytab}

