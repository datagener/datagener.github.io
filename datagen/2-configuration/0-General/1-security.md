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
- **datagen.auth.type**=internal : Type of auth to make among: internal, ldap, ldap-embedded


## Internal

To configure internal users, a default admin user must be set with following properties:

- **datagen.admin.user**=admin
- **datagen.admin.password**=admin


Then, automatic setup of users or groups to be admin, can be set with following properties:

- **datagen.auth.internal.group.admins**=admin : comma separated list of admin groups
- **datagen.auth.internal.user.admins**=superman,batman : comma separated list of admin users

In this mode, users are managed directly from the UI by admin users (defined above) and persisted to disk using a file whose path is defined by property:

- **datagen.users.file.path**


## LDAP - Embedded

To configure an automatic embedded ldap (whose users are defined in an internal ldif file: src/main/resources/users.ldif), set following properties:

- **datagen.auth.type**=ldap-embedded
- **spring.ldap.embedded.ldif**=classpath:users.ldif
- **spring.ldap.embedded.base-dn**=dc=springframework,dc=org
- **spring.ldap.embedded.port**=8389


## LDAP

To setup and configure an LDAP to get users from, set following properties:

- **datagen.auth.type**=ldap
- **datagen.auth.ldap.url**=ldap://hostname.com:389/
- **datagen.auth.ldap.basedn**=dc=frisch,dc=com
- **datagen.auth.ldap.bind.user**=uid=admin,cn=users,cn=accounts,dc=frisch,dc=com
- **datagen.auth.ldap.bind.password**=Cloudera1234
- **datagen.auth.ldap.group.base**=cn=groups,cn=accounts
- **datagen.auth.ldap.group.filter**=(member={0})
- **datagen.auth.ldap.group.search.subtree**=true
- **datagen.auth.ldap.group.search.maxdepth**=5
- **datagen.auth.ldap.group.role.attribute**=cn
- **datagen.auth.ldap.group.convert.uppercase**=true
- **datagen.auth.ldap.group.attribute**=memberOf
- **datagen.auth.ldap.user.base**=cn=users,cn=accounts
- **datagen.auth.ldap.user.filter**=(uid={0})
- **datagen.auth.ldap.user.attribute**=uid


To also enable a reverse search where users are taken from a research on groups scoped to _datagen.auth.ldap.group.base_ defined earlier

- **datagen.auth.ldap.group.reverse.search**=true
- **datagen.auth.ldap.group.reverse.search.timeout**=60
- **datagen.auth.ldap.group.user.attribute**=member

Automatic mapping of user/groups to be admin in Datagen:

- **datagen.auth.ldap.group.admins**=admin_group
- **datagen.auth.ldap.user.admins**=superman


Automatic mapping of user/groups to be user in Datagen (if empty, then all users logged in can use Datagen):

- **datagen.auth.ldap.group.users**=
- **datagen.auth.ldap.user.users**=