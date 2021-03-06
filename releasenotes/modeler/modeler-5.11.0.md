---
title: "Modeler 5.11.0"
space: "Release Notes"
category: "Modeler"
---


***Date: December 8, 2014***

{% modelerdownloadlink 5.11.0 %}

## Backwards compatibility breaking changes

This release contains a change that might impact the published web services in your Mendix projects. The response that is passed to the consumer of your service in case of a fault is now slightly different. Mendix versions 5.10 and below would set the HTTP status code to '200 OK' regardless of the success or failure outcome of invoking a web service operation. With 5.11, we are more standards compliant and set the status code to '400' if your web service client sends an invalid request, or '500' in case we encounter an internal server error.

<div class="alert alert-warning">{% markdown %}
When only other Mendix apps are consuming your web service, the impact of this change is negligible. We cannot, however, predict how third party clients will react to this change in behavior. So please be aware of this when you upgrade your project to 5.11 and **double check that your clients can handle the new behavior**, for example by intentionally sending an invalid request.
{% endmarkdown %}</div>

## New features

*   GitHub information is shown in the built-in App Store in the Modeler.
*   Redesigned the progress bar to make it less intrusive; removed default "Loading.." message; show at most a single progress bar.
*   Added a new widget called 'Container'. This widget is rendered as a `div` element with provided styles and classes. It can also be made conditionally visible. (Ticket 203593)

## Improvements

*   Improved transparency of which elements in imported XML schemas are supported and which are not (such as "any attribute" and "mixed content"). Previously this was only shown at the time of import but now it is also shown in XML schema trees and mapping documents.
*   Web service operations have icons that show whether an operation is one-way or two-way.
*   Thumbnail files are now associated with a database object which derives from the 'System.FileDocument' entity with an association to the original 'System.Image' instance. They are moved away from the 'thumbs' folder to where the other files are. The new way of handling thumbnails is migrated automatically when a project is launched for the first time.

## Fixes

*   In webservice documentation, show the proper host URL in referred web services and inside WSDL definitions. (Ticket 21185)
*   Shows the details about the unsupported constructs again when elements in an imported WSDL file are not supported. (Ticket 203558)
*   In case of a missing schemaLocation attribute in a WSDL, give a more informative error. The namespace for XML is now supported regardless of whether schemaLocation is specified. (Ticket 203557)
*   When a SOAP fault is returned in response to a web service, the HTTP status code is now set to 400 (bad request) in case of a client error, and 500 in case of a server error. (Ticket 204051)
*   Fixed Italic font being used for attributes in the XML in the object mapping representation.
*   Fixed an issue where the Modeler could become non-responding when 'Expand All' was pressed in a Domain-to-XML or XML-to-Domain mapping element selection dialog. We limited the maximum number of nodes expanded to 10000 to avoid unlimited memory usage.
*   Fixed user selected root element in import mapping wizard is not reflected in 'Select Elements' tab.
*   When converting a project containing old app services to a newer version (5.10.0 and above), the project could not be opened anymore in some cases. This happened for old app services where an entity name was changed after the app service was created. If such an app service is encountered, a dialog appears and the project loads (Ticket 204523).
*   Make sure microflow error messages contain the names of the microflow and activity that generated the error. (Ticket 204449)
*   Fixed recognition of date variables in where terms when tokens and epoch values are used. (Ticket 203029)
*   Fixed an issue in the Modeler where some dialogs, for example the Java Action dialog and the Module Security dialog, would become taller when typing or changing values. (Tickets 204235, 203827)
*   Assign active class to items in Menu bar and Simple menu bar. This feature allows developers to add indication of the current page to menus, but only in cases when nothing on a page except a menu causes navigation. (Tickets 203898, 19068)
*   Fix issue where unjustified error messages were shown about widgets not being destroyed correctly.
*   Fixed an issue where abstract element with an element type is used in the schema but the type cannot be found by runtime code due to faulty path construction. (Ticket 203952)

*   Navigation tree / menu works again in snippets. (Ticket 204528)

## Known issues

*   If you have existing projects using the Community Commons module, you will have to update this module from the Mendix AppStore. Older versions of the module are incompatible with Mendix 5.11.0 and will cause a compilation error.

## Removed features

*   None

## Deprecations

*   None
