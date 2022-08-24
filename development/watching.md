---
description: Watch to speed up local development
---

# Watching

When started in development mode, **Spignite** will watch for changes in files and redeploy them.

Changes are watched on all `Spig` patterns defined in `spig.js`. Some additional files are watched too, like templates or data files.

{% hint style="info" %}
Sometimes **Spignite** will miss a change (it is not perfect yet:). Just please restart! The build is fast enough.
{% endhint %}

Alternatively, you can use the [server-x](https://github.com/svrxjs/svrx) that reloads on change.
