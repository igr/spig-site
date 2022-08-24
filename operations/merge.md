---
description: Merges files
---

# merge

Merges several files into one. Provided `bundleAggregatorFn` must return result bundle name from given file reference. Each bundle name will be added as bundle file to `Spig` instance with merged content of all bundled files.

`Merge` is used, for example, in default **Spignite** operations, to collect all underscore prefixed JavaScript files and to create a single bundle file from it.
