---
title: "Modeler 6.3.1"
space: "Release Notes"
category: "Modeler"

---


***Date: March 3, 2016***

See also the release notes for Mendix [6.3.0](modeler-6.3.0).

{% modelerdownloadlink 6.3.1 %}

## New Features

*   Add a setting to the Cloud Foundry configuration to specify the buildpack to use when deploying your Mendix application to Cloud Foundry. This setting is updated in the Cloud Foundry app every time the app is deployed from the Modeler. When a custom buildpack is specified in an app that already exists in Cloud Foundry, you should update this buildpack setting in the Modeler to prevent it from being overwritten the next time the app is deployed.

## Known issues

*   The PostgreSQL JDBC driver shipped with 6.3.1 contains a bug which may result in queries not being executed correctly. If you are running into this issue, you will see messages similar to this in the logs: org.postgresql.util.PSQLException: ERROR: prepared statement "S_16" does not exist. A patch will be released with Mendix 6.4.1