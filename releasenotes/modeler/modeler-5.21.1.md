---
title: "Modeler 5.21.1"
space: "Release Notes"
category: "Modeler"

---


***Date: December 10, 2015***

See also the release notes for Mendix [5.21.0](modeler-5.21.0).

{% modelerdownloadlink 5.21.1 %}

## Improvements

*   Added menu item Tools > Batch Update Layouts to quickly change the layouts of many pages. This is especially useful for pages that are still pointing to a layout that has the property 'Use main placeholder for pop-ups' set to 'Yes'. You can limit the pages to update based on the way they are opened, e.g. only update pages that are always opened in content. See also [https://www.mendix.com/blog/batch-updating-page-layouts/](https://www.mendix.com/blog/batch-updating-page-layouts/)
*   Notify the user if the cache bust is not configured in index file of the theme. (Ticket 370276)

## Fixes

*   Fix data views doing a full refresh while only the rendering should be updated. (Ticket 463051)
*   Fix the flickering of the sidebar transition during navigation to another page. (Ticket 304502)
*   Disallow multiple home pages for the same user role.
*   Fixed exceptions and incorrectly constructed queries around entities where the depth level of the specializations is more than two. (Ticket 463510)