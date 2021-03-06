---
title: "Modeler 6.10.1"
space: "Release Notes"
category: "Modeler"

---
***Date: December 5, 2016***

{% modelerdownloadlink 6.10.1 %}

See also the [Mendix 6.10.0 Release Notes](modeler-6.10.0).

## URLs for pages with context

URLs can now be defined for every page in your application! This allows for sharing and bookmarking the URL of any page, including pages with parameters. This means that you can directly access pages with an edit form or the details of an entity. The URL property for pages with parameters should be configured to contain the {Id} placeholder, which will be replaced with the actual entity ID at runtime.

These are the known issues for this change:

*   If you try to open a URL for a page with a parameter that you do not have access to, you will be asked to log in to an account with sufficient access and will be immediately logged out of the current account.
*   If you try to open a URL for a page with a parameter that does not exist, you will get the error message "The page you requested was not found" and a custom 404 page will be ignored.
*   Data grids with date search fields show 1/1/1970 when going back to the page. This results in empty grids, as there is usually not any data with that date.
*   If the user tries to access a page without having the correct permissions, the user is logged out.

## Other fixes

*   The Modeler no longer shows an empty pop-up window when an empty error message is provided in a microflow validation. (Ticket 46511)
*   We fixed the blank screen problem for specific use cases when the entity attribute name is the same as JavaScript keywords/methods like `toString`, `hasOwnProperty`, etc. (Ticket 43793)
*   Some custom widgets were loaded with a URL containing two slashes (for example, _[https://mendix.com/widgets//widgets.js](https://mendix.com/widgets//widgets.js*)_). Too many slashes can be a bad thing, so we have reduced it to one. (Tickets 47075, 45080)
*   We fixed the multiselect behavior when one of the possible options is an empty string. (Ticket 46254)
*   We fixed the bug that caused widgets shown or hidden via conditional visibility to show outdated data. (Ticket 47171)