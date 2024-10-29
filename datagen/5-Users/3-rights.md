---
layout: default
title: Rights
parent: Users
has_children: true
nav_order: 3
---

# Rights

Once users are logged in, they have a role assigned among:

- **Admin**: An admin user sees everything and can manage everything (create, modify, delete): users, models, generation of data.
- **User**: A user has limited power restricted by policies managed by admin and itself on its resources.

This assignment is based on properties:

- **datagen.auth.ldap\|internal.group.admins**=
- **datagen.auth.ldap\|internal.user.admins**=
- **datagen.auth.ldap\|internal.group.users**=
- **datagen.auth.ldap\|internal.user.users**=

