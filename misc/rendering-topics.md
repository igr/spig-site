---
description: Rendering templates caveats.
---

# Rendering Topics

### Nunjucks

* Use the `safe` filter to pass already rendered content, e.g.:  `{{ value | safe }}`. [Documentation](https://mozilla.github.io/nunjucks/templating.html#safe).
* To render a JSON value in scripts: `{{ value | json | safe }}`.
