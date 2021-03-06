---
title: "Model SDK 2.5.0"
space: "Release Notes"
category: "SDK"
---
| Impact | Description |
| --- | --- |
| Low |  `getFilePaths` has been deprecated and renamed to `getFiles`. |
| Low | Improved the typings of some (internal) APIs. |
| None | Added support for Mendix 6.6.0. |
| None | `getFilePaths` accepts an option objects which can define `format` (either `zip` or `json`), `filter` (glob pattern) and `path` (output filename if format is `zip`). |
| None | Output filename is no longer mandatory for `getFile` / `getFiles` / `exportMpk`. If not provided, raw response is provided in the callback instead. |
| None | Support for forcing full deployment. Deploying a working copy is functionality that's not accessible to regular Model SDK users (i.e. non-trusted backends), so no impact. |
| None | Fixed a bug with delete deltas not being sent while they should - this e.g. caused 2 translations to be created for the title text of a new page, with the translations having the same language code. |
| None | More (complete) support for running model checks from the SDK: corrected implementation of check level groups, renamed `hasPrefix` standard library method for expressions (checks and queries) to `startsWith`. |