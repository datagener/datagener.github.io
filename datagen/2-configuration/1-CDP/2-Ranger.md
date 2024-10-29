---
layout: default
title: Ranger
parent: CDP Configuration
grand_parent: Configuration
has_children: false
nav_order: 2
---

# Ranger

When running on CDP, it is not required, but you can specify a ranger user and its password with ADMIN role.

This is only used by the _Initialize service dirs and policies_ command to create required default policies in Ranger.

If this is not set, you will have to create required policies by yourself.

_N.B.: If you generate data to some other paths/databases/topics than default ones of datagen, you will need to grant privileges for user datagen, unless you specified another user_
