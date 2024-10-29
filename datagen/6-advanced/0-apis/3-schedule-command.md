---
layout: default
title: Schedule Data Generation
nav_order: 3
has_children: false
parent: APIs
grand_parent: Advanced
---


# Scheduled Commands

All data generation APIs (seen before) allows a user to schedule them recurrently based on _scheduling_ parameters.

The endpoint _/command/getAllScheduled_ returns all scheduled commands.

Note that, a command is removed from being scheduled if one of its execution failed, if you search for it, it will print its error however if you look for the command, telling you to solve it before re-scheduling it.

The endpoint _/command/removeScheduled_ allows a user to remove a scheduled command using its UUID as a parameter.
