---
layout: default
title: GCP Connectors
parent: Configuration
has_children: false
nav_order: 4
permalink: /configuration/gcp
---

_NOTE: Configuring these credentials is not required, as they can also be configured directly when creating a model or when generating data_


# GCP Configuration

To interact with GCP connectors, following configuration is required:

- **gcs.project.id**= : project ID in GCP
- **gcs.accountkey.path**= : Optional as Only if using a service account key, otherwise use any other ADC login
- **gcs.region**= : Region in upper case, for example : EUROPE-WEST9
