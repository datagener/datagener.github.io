---
layout: default
title: Ldap
parent: Users
has_children: false
nav_order: 2
---

# LDAP - Embedded

To configure an automatic embedded ldap (whose users are defined in an internal ldif file: src/main/resources/users.ldif), set following properties:

- **datagen.auth.type**=ldap-embedded
- **spring.ldap.embedded.ldif**=classpath:users.ldif
- **spring.ldap.embedded.base-dn**=dc=springframework,dc=org
- **spring.ldap.embedded.port**=8389


# LDAP

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