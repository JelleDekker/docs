---
title: "Modeler 5.21.0"
space: "Release Notes"
category: "Modeler"
---

***Date: October 28, 2015***

<div class="alert alert-warning">{% markdown %}

Mendix 5.21.0 is no longer available for download, please use version [5.21.1](modeler-5.21.1) instead. If you use entities with inheritance more than 3 levels deep, you are advised to upgrade to 5.21.1 or higher.

{% endmarkdown %}</div>

Page templates are now out of beta!

## Backwards compatibility breaking changes

*   Having virtual attributes specified in an OQL select clause or in a retrieval schema will cause an exception, because that kind of attributes will be handled as non existing attributes. Previously, only an error was logged and the attribute was skipped.

## New features

*   The new and shiny radio buttons widget can be used to show enumeration and boolean attributes. When generating a page or when dragging a boolean attribute from the connector to a page, the Modeler will now generate radio buttons instead of a check box. For enumerations with less than six values, the Modeler will also generate radio buttons, otherwise a drop down will be inserted. Radio buttons will not be generated if page templates are disabled.
*   Mendix objects can be stored in the session by associating them to System.Session. See [custom session data] ([https://world.mendix.com/display/refguide5/ISession.getData%28%29+API+usage](https://world.mendix.com/display/refguide5/ISession.getData%28%29+API+usage)).

## Improvements

*   Every security check error is now reported separately, instead of reporting only the first one.
*   The stand-alone "New" button is hidden if you do not have create rights or access to the page.
*   Upgraded Bootstrap from 3.3.2 to 3.3.4.

## Changed Behavior

*   When persistent sessions are enabled, the 'LastActive' value is committed to the database only once every ClusterManagerInterval (default: 5 minutes), instead of every request. This drastically improves performance when using persistent sessions. See [here] ([https://world.mendix.com/display/refguide5/Keep+alive+mechanism+for+Persistent+Sessions](https://world.mendix.com/display/refguide5/Keep+alive+mechanism+for+Persistent+Sessions)) for more information.
*   User actions now need to be registered before they are referenced in Before, After or Replace events of the ActionListener API. Doing the registration too late will result in a warning, not doing it at all results in undesired behavior of the Mendix Business Server (exceptions).

## Fixes

*   Fixed an issue in the Modeler where opening a project from a UNC path (`\\server\share\...`) was not possible anymore. This especially affected users who run the Modeler in Parallels on Mac, as Parallels exposes the shared documents folder as a UNC path in Windows by default. (Tickets 356950, 448574)
*   Resolved a crash in the Modeler that could occur when converting a Mendix 4.x project.
*   Added project setting "Enable widget bundling" to always bundle custom widgets when deploying. (Ticket 384320)
*   Order of client refresh responses is now guaranteed, to ease parsing of client traffic (Ticket 416509)
*   Enabled download buttons if there is a file to download even if the surrounding data view is disabled. (Ticket 313170)
*   Clicking on a list view item nested in another list view item will no longer trigger the action of the parent item. (Ticket 102835)
*   Search fields for dates on grids now respect the custom date formats specified in the language options. (Ticket 101024)
*   Fixed concurrency issue which in rare cases (heavy load and advanced security constraints) could cause a runtime to keep on running at 100% CPU and become unresponsive (Ticket 447237).
*   Fixed an issue in the Mendix Business Server where the output value of a microflow could still be processed, despite the return type being 'Nothing'. Now all return values of return type `Nothing` will be ignored as expected. (Ticket 397625)
*   Fixed ActionListener API to accept both Action Names as Class Names as valid input for the Before, After and Replace events (Tickets 100510 & 21646).
*   Removed confusing log warning which could occur when an object could not be retrieved ("Object with id '%ID%' could not be retrieved.") (Ticket 262163).
*   Fixed list views using a microflow data source. (Ticket 462867)

## Remarks

*   If you upgrade your database from a pre-Mendix 5.21 model, the default values of date and float attributes will cause a change in the system tables of Mendix. This has no effects on any user data but is only necessary for the database synchronization handling.

## Known issues

*   Converting a project with duplicate Role-based home pages causes an exception. A workaround is possible by removing the duplicates before converting.
*   Queries involving entities with more than 3 levels of inheritance may be constructed incorrectly. This issue is solved in version 5.21.1.

## Removed features

*   None

## Deprecated features

*   MxObjectCache, available through LocalComponent, has been deprecated. MxObjectCache is an internal construct, as such it is not part of our public API, consider using [custom session data](https://world.mendix.com/display/refguide5/ISession.getData%28%29+API+usage) instead.
*   ISession.getData(), ISession.retain(), ISession.release(): These methods have been deprecated, use an association to System.Session to store objects in a session instead. Consider using [custom session data] ([https://world.mendix.com/display/refguide5/ISession.getData%28%29+API+usage](https://world.mendix.com/display/refguide5/ISession.getData%28%29+API+usage)) instead.