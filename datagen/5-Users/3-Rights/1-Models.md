---
layout: default
title: Models Rights
parent: Rights
grand-parent: Users
has_children: false
nav_order: 1
---

# Models

Once a user created or imported a model, it is considered as its **owner**, hence it has all rights on it.

Only the **owner** (or datagen admin or model admin) can then **modify rights** of a model in _Models Management_ view to **add user/groups** or **admin users/groups**.

**User** of a model can see a model, test it and generate data with it, or import it to create a new model.

**Admin** of a model have same rights than users but also can delete it, modify it, and modify its rights.

_Note: An admin user of Datagen can see, use, create, delete, modify any models_

|-----|See model|Test model|Generate data|Load model|Modify model|Delete model|Mofify ACLs|
|Datagen Admin|X|X|X|X|X|X|X|
|Model Owner|X|X|X|X|X|X|X|
|Model Admin|X|X|X|X|X|X|X|
|Model User|X|X|X|X||||
|Datagen User||||||||

