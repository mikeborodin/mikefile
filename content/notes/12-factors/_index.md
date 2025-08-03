+++
date = '2025-01-06T21:55:08+01:00'
draft = false
title = '12 Factors'
showAuthor = false
+++

![feature](feature.jpg)

I saw somewhere this website https://12factor.net, looks interesting let's analyze it.

## Input: 

I. One codebase tracked in revision control, many deploys

II. Explicitly declare and isolate dependencies

III. Store config in the environment

IV. Treat backing services as attached resources

V. Strictly separate build and run stages

VI. Execute the app as one or more stateless processes

VII. Export services via port binding

VIII. Scale out via the process model

IX. Maximize robustness with fast startup and graceful shutdown

X. Keep development, staging, and production as similar as possible

XI. Treat logs as event streams

XII. Run admin/management tasks as one-off processes


## Analysis: 

>I. One codebase tracked in revision control, many deploys 
- basically trunk based dev, where you have frequent deploys and feature flags.

> II. Explicitly declare and isolate dependencies
- trying to pin the versions, keep variance low

> III. Store config in the environment
- not sure how to understand it, is it about process environment or dev environment? Assuming process environment (kinda make it possible tweak a program)

>IV. Treat backing services as attached resources
- meaning they can be offline / not compatible etc.

>V. Strictly separate build and run stages
- I think  it's already separated for us in mobile dev.

>VI. Execute the app as one or more stateless processes
- generally the less state the better, yes.

>VII. Export services via port binding
- looks like something backend.

>VIII. Scale out via the process model
- same.

>IX. Maximize robustness with fast startup and graceful shutdown
- yes :D

>X. Keep development, staging, and production as similar as possible
- test on prod, prefer single branch if possible.

>XI. Treat logs as event streams
- something like Sentry, don't expect the results to be available synchronously.

>XII. Run admin/management tasks as one-off processes
- as I understand basically about limiting the timespan of priviliged code.


## Takeaways

* Version it all: code, pin dependencies, including your dev environment
* External world is external, not in your control, accept it.
* Prefer loose coupling
* Less State - or let's say "more computable state".
* Minimal difference between environments

