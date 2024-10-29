---
layout: default
title: Users
has_children: true
nav_order: 6
permalink: /users/
---

# Users

As of now, Datagen can be configured to get users from 3 different ways:

- **Internal**: Users are created inside Datagen by an administrator and are managed into it
- **Ldap**: Users are authentified against the LDAP each time they connect. Rights are then managed in Datagen.
- **Ldap-embedded**: Datagen will run an embedded ldap, only made for testing purposes.


To enable authentication and set which type, following configurations are required:

- **security.basic.enabled**=true
- **datagen.auth.type**=internal : Type of auth to make among: internal, ldap, ldap-embedded