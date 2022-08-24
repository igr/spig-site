# template

Applies a template to a file.

**Spignite** supports the following templating engines:

* Nunjucks.

### Resolving layouts

Layout resolving is part of the **Spignite**. Templates are resolved using the following order:

1. the value of `layout` attribute (from frontmatter or attributes files)
2. using files base name
3. using files full name
4. using `base` as default layout name.

For each above step, layouts are searched for in corresponding folder and parent folders.
