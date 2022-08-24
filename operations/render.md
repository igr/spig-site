---
description: Renders a page
---

# render

Renders a file: converts the content to HTML. Rendering engine is chosen from file's extension.

**Spignite** currently supports following renderers:

* nunjucks
* pug
* markdown

Rendering is optional, because some engines may not need one. You can specify the paths (usually just extensions) that will be rendered in `ops.js`.

For example, you can use `nunjucks` files as sources in two ways: with rendering and without. When rendering is enabled than nunjucks file is just a simple template, unaware of `layout` (as layouts are used during templating). When used without rendering, than this step is skipped and only templating is applied to the file.
