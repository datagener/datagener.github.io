---
layout: default
title: Credentials Rights
parent: Rights
grand-parent: Users
has_children: false
nav_order: 3
---


# Credentials

Credentials are visible in _Models > Credentials_ view.

_WARNING: Once a credential has been created, it cannot be modified neither retrieved_

Only **Datagen Admin** can see, modify ACLs, delete and use for data generation all credentials.

**Owner** of a credentials can see, modify ACLs, delete it and use it for data generation.

**User** of a credentials can only see it and use it for data generation.

|-----|See Metadata|Use for Generation|Modify ACLs|Delete|
|Datagen Admin|X|X|X|X|
|Credential Owner|X|X|X|X|
|Credential User|X|X|||
|Datagen User|||||

