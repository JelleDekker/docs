---
title: "Modeler 5.19.0"
space: "Release Notes"
category: "Modeler"

---

***Date: September 2, 2015***

{% modelerdownloadlink 5.19.0 %}  

## Backwards compatibility breaking changes

*   Microflow sorting is now case insensitive and consistent with database sorting. Consequently, a sorted list A, B, a, b will be changed to a, A, b, B after upgrading to this version.

## New features

### Text widget

The text widget is a new widget with support for client-sided templating. A template can contain placeholders which will be substituted by the values of selected attributes at runtime. For example, it is possible to create a template "Hello, {1}!" and have placeholder "{1}" replaced by a user's name.

The text widget is rendered as a span in the client, but it can be configured to render as a paragraph or a heading (sizes 1 to 6). It is recommended to represent static or dynamic text using the text widget as it is also semantically correct.

Render mode is removed from the label widget. All labels that have non-default render modes specified are converted to text widgets.

### Dynamic text

Besides the text widget two more widgets have support for client-sided templating:

*   Button captions
*   Group box captions

### Other new features

*   Stand-alone action buttons triggering a microflow can be disabled while the action is running (tickets 204392, 204406).

## Improvements

*   Added an action parallelism configuration setting: mendix.action.parallelism, to configure the parallelism of request handling. Default value is 300, which should be enough for most applications. If in load tests dead locks occur this number can be increased to resolve possible thread starvation.
*   Show a support category label in the overview tab of an App in the App Store page of the Business Modeler.
*   On pages, a region that can be collapsed with the side bar toggle button is no longer visualized to save space.
*   Reflect form orientation and label width in the rendering of input widgets with labels in the Modeler.
*   Navigation list items can be made conditionally visible (ticket 337776).
*   Render main placeholder and form call higher to visualize where the main content should go.
*   Data views listening to another widget keep the listening data source if an entity is dropped on the widget from the connector. Also auto-fill is checked by default if the setting is enabled in the Modeler.
*   Mendix UI Framework:
    *   Lots of library feedback processed.
    *   New folder structure, more distinction between CSS and Sass.
    *   Users are now able to use a custom.css file filled with predefined CSS elements.
    *   Dropped compass as a default in our Sass files, it's now easier to use different compilers besides Scout (forum feedback).
    *   Added how to's: Setup Mendix UI Framework with Sass ([https://world.mendix.com/display/howto50/Setup+Mendix+UI+Framework](https://world.mendix.com/display/howto50/Setup+Mendix+UI+Framework)) and Setup Mendix UI Framework with just CSS ([https://world.mendix.com/display/howto50/Setup+Mendix+UI+Framework](https://world.mendix.com/display/howto50/Setup+Mendix+UI+Framework)).
*   Page Templates: new Master Detail Template added.

## Fixes

*   Asynchronous actions are now no longer erroneously listed as running when the action has finished after the browser has been closed. (Tickets 102468, 206674, 295676, 326217)
*   Case insensitive sorting for microflows. Therefore, sorting in microflows is now consistent with database sorting. (Ticket 206311)
*   Fixed storing files into S3 when uploaded by the web client file uploader (using the multipart content type). (Ticket 359621)
*   Fix thread starvation in the action dispatcher for high concurrency. (Ticket 355219)
*   Fixed that a microflow was continued after a submicroflow with return type 'Enumeration' and error handling 'Rollback' threw an error. (Ticket 359677)
*   Added executeAsync method for named parameters to Core class for Java actions. Non-named parameter method is discouraged for microflows. (Tickets 358405, 204398)
*   Allow break and continue events as the only object in a loop. (Ticket 205074)
*   Do not allow before delete action execution without appropriate rights. (Ticket 203288)
*   Do not attempt to calculate the calculated attribute value in the debugger when paused in that calculated attribute microflow. Omit this attribute when showing the object variable in the debugger. (Ticket 237743)
*   Fixed unwanted removal of associations for just committed objects in some special cases. (Ticket 319005)
*   When deleting a sequence flow from a microflow by selecting it with the mouse, and then pressing the 'Delete' key on the keyboard, the Business Modeler would sometimes crash. This has been resolved.
*   Extracting a submicroflow when one or more annotations are selected would fail with the message that associated annotations must be selected. Also, extracting an action without its associated annotation would succeed but this would delete the annotation flow. Extraction of a submicroflow in combination with annotations now works as expected. (Ticket 205463)
*   When retrieving data for the 'My Apps' page failed (for example due to a network problem), the Business Modeler would sometimes crash. This situation is now handled by showing a user friendly message.
*   Resolved a compile error during deployment when the domain model contains an entity called 'String'. (Ticket 274160)
*   When deploying a project from the team server in the cloud which includes deploying WSDLs belonging to Consumed Web Service documents, the contents could differ when compared to a version from local deployment. This is now made consistent.
*   Fix layout thumbnails in the "Create Page" dialog in projects not using Page Templates.
*   Creating horizontal and vertical split panes is once again possible. Note that they are still deprecated and will be removed in the next major version.
*   Fix an issue with building data retrievals schemas, which caused a crash of the runtime on application start. (Ticket 339946)
*   Fix to reduce the number of data requests for Input Reference Set Selectors.
*   Fix issue in the Modeler where pasting a widget with the same name as an existing one changed the name of that existing widget.
*   Pass correct context to a microflow called from a static image. (Ticket 400589, 530493)
*   Enable "Abort on validation errors" for microflow action buttons on grid. (Ticket 102896)
*   Apply Mendix rounding (modeler-20.8) to decimal values when sending them to the client. (Ticket 314846)

## Known issues

*   Internet Explorer 8 does not support responsive features like the layout grid.

## Removed features

*   None

## Deprecated features

*   Deprecate "apply context" and "remove from context" for reference selector, data grid and template grid datasources. Prefer using XPath constraints instead.