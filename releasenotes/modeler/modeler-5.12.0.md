---
title: "Modeler 5.12.0"
space: "Release Notes"
category: "Modeler"

---


***Date: December 29, 2014***

{% modelerdownloadlink 5.12.0 %}

## Features

*   Added support for MySQL 5.5 and later.

## Improvements

*   When running an application locally from the Modeler, the startup sequence of the runtime is now performed in the background, so the user can continue working in the Modeler right after the deployment of the project finishes. (Tickets 5424, 7527)

*   File documents are now stored based on a UUID instead of an autonumber. On disk a file is stored in a two-level deep folder structure: the first folder name is the first two characters of the UUID, the second folder name the second two characters. In the second folder the file name of the actual file is the UUID. This will give a better distribution of files in folders, so that browsing files using a GUI is still performant for a large number of files. Only new files will be stored and fetched using this new method. Old files will stay in their old location and will be fetched using the old method.

*   File documents marked with "DeleteAfterDownload" are no longer stored in the temp folder, but between the other files as temporary documents are a different concern. Temporary documents can be stored into the temp folder directly.

*   When parsing invalid XML, coming from either another server or when importing XML from a file, the error message to clarify the problem with the XML is improved. (Ticket 203721)

*   Schema validation option can now be set via the "Export XML" action and the "Import XML" action in microflow.

*   Wsdl validation option can now be set via the "Call web service" action in microflow.

*   'Draft' app service versions can now be consumed during development. When running in production, still only 'consumable' app service versions are available.

*   Assign active class to clicked items in Navigation list. This feature allows developers to add an indication of the current page to the navigation list. (Tickets 203898, 19068)

## Fixes

*   Fixed the problem that document packages containing only one image collection document could not be imported.

*   Ensure the context classloader of a request handler is the classloader of the request handler class. I.e. when processing a request in a custom request handler in a Mendix project the project bundle classloader should be the context classloader. (Tickets 204676, 204613)

*   Fixed that the thumbnail migration would not terminate when more than 500 images did not have a physical thumbnail file associated. (Ticket 204840)
*   'All' element in XML schema definition is now supported in the modeler. (Ticket 7873)

*   The enumeration caption is now rendered in the correct language when rendering a document template. (Ticket 204391)

*   Fixed issue in Consumed web service document where OK button did not respond when file path has changed.

*   Fixed issue where unjustified error messages were shown about widgets not being destroyed correctly.
*   The precision of the display of float and currency is increased to 15 significant digits to properly display large numbers. (Ticket 204366)

## Known issue

*   Applications which have been built before Mendix 2.5.1 and for which FileDocuments have been uploaded in production are advised not to upgrade to this version. Before Mendix 2.5.1 files were stored directly in deployment/data/files (e.g. deployment/data/files/12). In 5.12.0 a new structure is used for file storage for which the first folder name is the first two characters of a UUID. This new folder name can collide with the file name of a file uploaded before Mendix 2.5.1, which will ultimately result in a FileNotFoundException during upload. This issue will be fixed in 5.14.0, from this version on it's safe to upgrade again for these applications.
