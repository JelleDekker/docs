---
title: "Modeler 5.21.5"
space: "Release Notes"
category: "Modeler"

---


***Date: July 22, 2016***

See also the release notes for Mendix [5.21.0](modeler-5.21.0), [5.21.1](modeler-5.21.1), [5.21.2](modeler-5.21.2), [5.21.3](modeler-5.21.3) and [5.21.4](modeler-5.21.4).

{% modelerdownloadlink 5.21.5 %}

## New feature

Make it possible to use widgets that are marked as offline capable. Note that actually building offline applications is a Mendix 6 feature.

## Improvements

*   Administration 'about' action now includes Java version.
*   Amazon aws-sdk-java is updated to 1.10.69 version. This version includes the fix for incorrect formatting of date headers in case of Java 1.8u60 and later, causing the server rejecting the requests. See [the AWS Github issue page](https://github.com/aws/aws-sdk-java/issues/444) for more information.
*   Due to a number of reasons orphan files can exist in the local filesystem of an app. Orphan files are files in the uploaded file directory which do not have a corresponding database entry. As not all causes of files becoming orphan files can be resolved a scheduled clean-up is introduced in this release to do clean orphan files automatically. In this release this scheduled task is turned off by default, so that this will for now only run for applications which explicitly turn this on. To do this set the custom setting 'com.mendix.core.localfilesystem.cleaning.isEnabled' to 'true'. See for more details https://world.mendix.com/display/refguide6/Custom+Settings. When clean-up goes well for all apps which test this procedure, the scheduled task will be turned on by default in a next release. (Tickets 263923, 419169, 463045, 463881, 464147, 464233, 464504)

## Fixes

*   When "Send binary data as attachments (MTOM)" is disabled in the consumed web service document, the "xml:" namespace is no longer added to the SOAP body message because it is not allowed to be present by Microsoft web services. (Ticket 466164)
*   Fix confirmation dialogues so that they are blocking again. (Ticket 464792, 463453)
*   Memory usage reporting in monitoring ('runtime_statistics') for Java 8\. Java 7 fields "survivor", "tenured", "code", "permanent" and "eden" elements are deprecated and instead use "memorypools". Old memory fields have a value of 0 for backwards compatibility reasons. For more information see the "memory" section in [the Monitoring documentation](https://world.mendix.com/display/refguide6/Monitoring+-+Mendix+Business+Server). (Ticket 465551)
*   Fixed 'Remove' list operation for the case where the object to be removed was retrieved in a different manner (e.g. 'by association' instead of 'from database') than the object in the list, which lead to in-equal objects. (Ticket 464178 and 466689)
*   Updated BouncyCastle libraries to the newest signed versions. This makes sure a signed provider is used and fixes the 'JCE cannot authenticate the provider BC' error. (Ticket 466314)
*   Fixed an issue when Edm.Decimal representation in XML for OData had a scientific notation. (Ticket 466590)
*   Fix memory leak when generating documents. (Ticket 465251)

## Known issue

*   Opening the AppStore in the Mendix Modeler fails for Windows 10 in some cases. This is due to the `%USERPROFILE%\AppData\Local\Microsoft\Windows\INetCache` directory being read-only.
    A workaround is to follow these steps:
    1\. Open the `%USERPROFILE%\AppData\Local\Microsoft\Windows\INetCache `directory
    2\. Right-click -> Properties
    3\. Uncheck the 'Read only' attribute