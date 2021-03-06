---
title: "Modeler 5.21.4"
space: "Release Notes"
category: "Modeler"

---


***Date: April 20th, 2016***

See also the release notes for Mendix [5.21.0](modeler-5.21.0), [5.21.1](modeler-5.21.1), [5.21.2](modeler-5.21.2) and [5.21.3](modeler-5.21.3).

{% modelerdownloadlink 5.21.4 %}

## Fixes

*   Fixed issue when MTOM attachment reference in XML had xmime:contentType attribute even if it was not provided by export mapping (Ticket 374374, 463341, 464052, 465254)
*   Attribute namespaces in XML messages did not apply prefixes correctly (Ticket 447172, 463535)
*   Fix flickering of the page when navigating to a page in content.
*   Fix login issue when named user limit is reached, causing all users to be locked out of the application. Users with the System.Administrator role can now always log in, even when the number of users has exceeded the number specified in the license. Previously only the user with the Administrator name, MxAdmin by default, could log in. This user is not available on sandboxes however. (Ticket 465382)