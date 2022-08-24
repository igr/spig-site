---
description: File in Spignite is just a collection of meta-data.
---

# FileRef

A file reference is an object that contains file information. It is passed to every **Spignite** operation.

It contains the following properties:

```javascript
_change = false;
_active: boolean;
_synthetic: boolean;
readonly _root: string;
readonly _id: string;
readonly _src?: string;
readonly _dir: string;
readonly _name: string;
readonly _ext: string;
_out: string;
readonly _basename: string;
readonly _path: string;
readonly _uuid;
readonly _spig: Spig;
readonly _cfg: SpigConfig;
```

### Attributes

Attributes are associated data of a `FileRef`. Attributes are (or should be:) only accessible using the methods:

```javascript
attr(name);           // reads attribute
setAttr(name, val);   // sets attribute
setAttrsFrom(object); // copies attributes from the object (Objects.assign)
addAttrsFrom(object); // adds non-existing attributes from given object
hasAttr(name);        // detects if attribute exist
```

### Content

Current content can be reached as `Buffer` or a simple string, using methods: `buffer()` or `string()`.

### Context

While `FileRef` is available for all **Spignite** operations and file manipulation, it is NOT available inside any content! In other words, `FileRef` is not available for rendering/templating.

{% hint style="success" %}
`FileRef` is available for **Spignite** ops; the _context_ for the rendering/templating.
{% endhint %}

For that purpose, each `FileRef` has a `context()` method that returns actual context that IS available on the page! It consists of:

* all the attributes
* `site`- global metadata
* `link` - full link to the file
* `url` - permalink
* `src` - dir + name of the source file
* `content` - string content of a file
