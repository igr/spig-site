---
description: Collect attributes from path
---

# attributes

Each `FileRef` has attributes that are available during page templating and rendering (in page context). This operation collects attributes from various locations.

1. `_.json` or `.js` in the same folder where file is. It can be a JSON file or a JavaScript file that returns an object. Using JavaScript you can have dynamic values for your attributes.
2. Same files but in any upper folders. This way we can define some attributes for all subfolders or all subpages of the site.
3. `__.json` or `__.js` in the same folder where file is. Difference from single-underscored attribute files (explained above) is that they are only applied to the same folder, and not child folders. They are shared only by files in the same folder.
4. `<filename>_.js` or `<filename>_.json` the same as for double-underscored attributes; but they are not shared.

Using various attribute files you can set some attributes on 1) large collection of files and subfolders, 2) only files in the same folder and 3) only specific file.
