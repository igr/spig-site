---
description: How to migrate Spig website to version 3?
---

# Migrate to v3

* Update node to `16` in `.nvmrc`
* Rename `spig.js` to `spig.mjs` to use **Spignite**'s ESM module.
*   Change `spig.mjs` to import **Spignite** module (instead of `require`):

    ```javascript
    import { Spig } from "spignite";
    ```
* Update `package.json` srcripts to use the new file name `spig.mjs`.

That should be it.
