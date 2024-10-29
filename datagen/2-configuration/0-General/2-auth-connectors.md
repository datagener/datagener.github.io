---
layout: default
title: Authentication to Connectors
parent: General Configuration
grand_parent: Configuration
has_children: false
nav_order: 2
---

# Connectors Security - Kerberos

To authenticate to some services that are using kerberos, it is possible to define a general setting that will apply for all connectors requiring kerberos.

- **kerberos.enabled**=true
- **kerberos.user**=datagen
- **kerberos.keytab**=datagen.keytab


# Connectors Security - TLS

To authenticate or secure connection to connectors requiring TLS, it is possible to define a general setting that will apply for all connectors requiring TLS:

- **tls.enabled**=true
- **truststore.location**=
- **truststore.password**=
- **keystore.location**=
- **keystore.password**=


# (Optional) Connector Security - Hadoop

To setup Datagen's user and home for Hadoop compoennts:

- **hadoop.user**=datagen
- **hadoop.home**=/user/datagen