---
layout: default
title: CDP Configuration
parent: Configuration
has_children: true
nav_order: 0
permalink: /configuration/cdp
---

# Settings in Cloudera Manager

Cloudera Manager makes a bunch of auto-configuration such as kerberos or auto-TLS.

In Cloudera Manager, under _Datagen > Configuration_, all properties are listed but usually not set.

Most important ones, are the auto-discovery ones (described in next section), as they allow to not specify any and let Datagen discover itself the configuration to connectors.

However, it is still possible to override some in Configuration.

_Note: All properties are injected into the application file and passed to the application before starting it._
