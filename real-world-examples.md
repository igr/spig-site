---
description: See Spignite in action.
---

# 🌍 Real-world examples

Here are some real-world **Spignite** examples. Even though we didn't talk about existing operations, these examples will be understandable.

### Simple website

```javascript
import { Spig } from "spignite";

Spig.hello();

Spig
  .on('/**/*.{md,njk}')

  ._("INIT")
  .pageMeta()
  .pageLinks()
  .tags()

  ._("RENDER")
  .render()
  .applyTemplate()
  .htmlMinify()
;

Spig
  .on('/**/*.{png,jpg,gif}')

  ._("INIT")
  .assetLinks()

  ._("IMG")
  .imageMinify()
;

Spig.run();
```

This is how one simple website is built. Let's dig the code.

* `Spig.hello()` defines the `HELLO` phase with all the default operations that work with the default folder structure: dealing with CSS, javascript, images, static files, etc. Content and layers are not covered in this phase.
* `INIT` phase for markdown files collects some meta-data (attributes) and defines the output links. A similar thing happens on the second set (images), where only output links are defined.
* `INIT` phase on the first set also collects tags and pages that define them.
* `RENDER` phase is one that processes markdown files to HTML (`render()` operation), then applies the template, and finally, performs the HTML minification of the code.
* Images set does not have the `RENDER` phase, but the `IMG` phase, where images get minified.

The order of phases is as defined in the file: `HELLO`, `INIT`, `RENDER`, `IMG`.

{% hint style="info" %}
Don't forget the alternative syntax if this one looks awkward 😊
{% endhint %}

### Advanced example

{% code lineNumbers="true" %}
```javascript
import { Spig } from "spignite";

Spig.hello();

function postsToRoot(path) {
  if (path.dirname.startsWith('/posts/')) {
    path.dirname = path.dirname.substr(6);
  }
}

Spig
  .on('/**/*.{md,njk}')
  .watchSite()

  ._('META')
  .pageMeta()
  .readingTime()
  .tags()
  .summary()

  ._('INIT')
  .do('slug-from-title', fileRef => {...})
  .pageLinks()
  .rename(postsToRoot)

  ._('RENDER')
  .render()
  .applyTemplate()
  .htmlMinify()
;

Spig
  .on('/**/*.{png,jpg,gif}')

  ._('IMAGES')
  .assetLinks()
  .rename(postsToRoot);

Spig
  .on('/index.json')

  ._('RENDER^BEFORE')
  .pageMeta()
  .applyTemplate()
;

Spig.run();
```
{% endcode %}

This example has two custom javascript codes: one is a function `postsToRoot` and the second is a lambda in line #22 (removed for simplicity).

* We are also collecting reading time and extracting the summary, all in the `META` phase. In other words, we just collect more meta-data about the content.
* `INIT` phase is all about links. It defines page slugs from the page title and removes the `/post/` prefix from the URL.
* `RENDER` phase is the same as in the previous example.
* `IMAGES` process the images from the content folder. Note that images from the `/src/images` are processed in `HELLO` phase, defined in defaults by `Spig.hello()`.
* `index.json` is some kind of meta-data file that needs to exist on the website. It is executed before `RENDER` phase. This is the only time in the pipeline when we have both the target links defined and the content is still in Markdown.
