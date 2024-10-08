---
layout: default
title: Installation Troubleshooting
parent: CDP
grand_parent: Installation
nav_order: 2
---


# Troubleshooting

## Service does not exists

- [ ] Verify that the csd is well present in `/opt/cloudera/csd` 

- [ ] Restart Cloudera Manager

- [ ] Verify in its log: `/var/log/cloudera-scm-server/cloudera-scm-server.log` that DATAGEN CSD is well added and no errors pops up.


## No metrics - Error Querying Internal

- [ ] Restart Cloudera Management Service and especially Service Monitor.

- [ ] You can also check that the local cloudera-agent is well running and able to capture metrics from Datagen Web server.


## No Datagen status - Test has invalid configuration 

It is possible that Service Monitor is not able to get some configuration values from Datagen.

- [ ] Go to _Datagen > Configuration_ and make following changes:

    **unexpected_exits_thresholds** to set Warning to _Any_ and Critical to _Never_.
    **process_swap_memory_thresholds** to set Warning to _Any_ and Critical to _Never_.
    **process_swap_memory_rate_thresholds** to set Warning to _Any_ and Critical to _Never_.
    **log_directory_free_space_percentage_thresholds** to set Warning to _80_ and Critical to _80_.

- [ ] Restart Cloudera Management Service.

- [ ] The warning: `Test disabled because of an invalid configuration: Test of whether enough DATAGEN_SERVER roles are healthy` could be safely ignored and removed using _suppress_ button.

