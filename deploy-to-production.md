---
description: Happy site is a live site
---

# 🚢 Deploy to production

By default, **Spignite** works in `DEVELOPMENT` mode. When deploying to production, enable the `PRODUCTION` mode by enabling the environment variable `SPIG_PRODUCTION`

```shell
rm -rf out
SPIG_PRODUCTION=true npm run build
```
