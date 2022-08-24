---
description: Group files by attribute
---

# group

`group(attributeName)` groups files by an attribute. It process each file of a set and if a file contains an attribute, it will be collected into the group by attribute value.

The following methods are added to the `site`:

* `attributeName()` (in plural) - returns all attributes
* `<attributeName>Group(<groupName>)` - returns all files of a group with given name.

### Example

```javascript
Spig
  .on('...')
  ._('PHASE')
  .group('type')
;
```

This example will scan all the files (file references). If file has attribute `type`:

```
---
title: Some cool title
type: A
---
```

it will be collected and grouped in the `A` group (the name of the `type`).

Later on, you can get all the types using `site.types()` and all the files of a group using `site.typeGroup('A')`.
