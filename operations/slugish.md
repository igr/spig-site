# slugish

Change slug name based on attribute `slug`. If attribute is missing, the slug will be set from the files output name.

Slug attribute value can be also a Mustache template that is parsed on `FileRef` context.

For example, you can specify the slug from title like this:

```
slug: {{title}}
```
