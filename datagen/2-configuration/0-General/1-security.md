---
layout: default
title: Security Configuration
parent: General Configuration
grand_parent: Configuration
has_children: false
nav_order: 1
---

# Security - TLS

_Note: Default deployment comes without TLS_

To enable TLS for the server, following configurations must be set:

- **ssl.server.enabled**=true : To enable TLS
- **server.ssl.key-store**=dev-support/test_files/keystore.jks : Path to keystore
- **server.ssl.key-store**-password=Test1234 : Password of the keystore
- **server.ssl.key-store-type**=JKS : Type of the keystore
- **server.ssl.key-alias**=test-keystore : Alias to use in the keystore
- **server.ssl.key-password**=Test1234 : Password of the key in the keystore
- **server.ssl.trust-store**=dev-support/test_files/truststore.jks : Path of the truststore
- **server.ssl.trust-store-password**=Test1234 : Password of the truststore


# Security - Auth

To enable authentication and set the default admin user, following configurations are required:

- **security.basic.enabled**=true
- **admin.user**=admin
- **admin.password**=admin