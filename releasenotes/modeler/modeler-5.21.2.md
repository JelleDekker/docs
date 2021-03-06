---
title: "Modeler 5.21.2"
space: "Release Notes"
category: "Modeler"

---


***Date: February 22, 2016***

See also the release notes for Mendix [5.21.0](modeler-5.21.0) and [5.21.1](modeler-5.21.1).

{% modelerdownloadlink 5.21.2 %}

## Fixes

*   Fixed issues related to conversion from Mendix 4\. (Tickets 463586, 462850)

*   Fixed issues related to conversion of excluded Domain-to-XML and XML-to-Domain mappings. (Tickets 416284, 387305, 463573)

*   Fixed issue where an XSD reference in a WSDL section was not deployed correctly. (Ticket 463626)

*   Fixed device type in client for large session data responses (e.g. when there are a lot of entities in the domain model that are visible to the user). (Ticket 464004, 463916)

*   Fixed incorrect value of '$currentDevicetype' in the homepage microflow. (Tickets 463112, 463916)

*   Fixed storage of non-localized date attributes as localized values. (Ticket 463941)

*   Fixed clicks on the date picker being ignored on Windows Phone. (Ticket 463945)

*   Fixed an issue where conditionally visible widgets could cause flickering of the page, a changing scroll position, or the scrollbar sometimes not appearing. (Ticket 463592)

*   Fixed memory leak in the data view which caused a noticeable slowdown and could even crash the browser. (Ticket 464612)

*   Fixed an issue in setting a custom configuration value for 'UploadedFilesPath'. Because of a race condition, the custom value was sometimes not picked up by the module which handles uploads to the local filesystem. (Tickets 463877, 464498)

*   Fixed nullpointer exception when 'ClientQueryTimeout' is set and a user has no rights to execute a query.

_NOTE : It is recommended to convert your existing Mendix projects directly into the 5.21.2 version of the modeler to incorporate above mentioned fixes._