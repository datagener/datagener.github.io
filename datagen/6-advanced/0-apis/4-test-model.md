---
layout: default
title: Test Model
nav_order: 4
has_children: false
parent: APIs
grand_parent: Advanced
---

# Model Tester API

An endpoint exists to allow a user to test its model.

Located at _/model/test_ it inputs either the model file path (on the machine where Datagen runs) or a direct upload of the model file.

It parses the file, returns an error if the model is not working, otherwise a row made using this model.

Hence a user can test its model before generating data.
