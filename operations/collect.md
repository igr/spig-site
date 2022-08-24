---
description: Collect files by attribute name
---

# collect

`collect(attributeName)` collect files with an attribute. It process each file in a set and if a file contains an attribute, it will be collected into a collection.

The following methods are added to the `site`:

* `attributeName()` (in plural) - returns all files with the attribute defined
* `<attributeName>Of(<url>)`&#x20;
* `<attributeName>OfSrc`

This operation is cool when you need to collect the pages of same kind. For example, you can collect all blog posts, or all project-related pages.
