---
title: "Modeler 5.16.1"
space: "Release Notes"
category: "Modeler"
---


***Date: June 12, 2015***

See also the release notes for Mendix [5.16.0](modeler-5.16.0).

{% modelerdownloadlink 5.16.1 %}

## Fixes

*   Projects that were converted from version 5.9 or below to 5.16 did not convert properly in case the project contained published web or app services.
*   Resolve an error that could occur when a versioned deployment package is created of the current project in the Modeler (Ticket 292717).
*   Fixed error that occurred when copying a data view with a microflow data source (Ticket 293023).
*   Make sure it's still possible to concat string literals to empty string variables (Ticket 288502).
*   Clarified error when bundling widgets fails.
*   Fixed an issue in 5.16.0 where if you upgrade a project and another team member has already committed the conversion to the team server you could see changes.
*   Fixed cookie support check on Windows Phone when running on Phonegap.
*   Extended client API to support datagrid extension and tab extension widgets.

## Migration

*   As of Mendix 5.16.0 widgets are compiled to validate that they use documented client APIs only, and use a dependency loading mechanism that is compatible with all platforms supported by Mendix. Compilation of widgets is part of the "Create Deployment Package..." action. We advise you to perform this shortly after opening your project in 5.16.0, so you known upfront what widgets are incompatible with 5.16.0.