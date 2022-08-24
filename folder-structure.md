---
description: Site source is well structured.
---

# 📚 Folder structure

**Spignite** expects a certain directory structure. The structure is part of the defaults and can be easily modified. The defaults exist only to speed up the initial project setup.

```
project/
├── out/
├── src/
│   ├── config/
│   ├── css/
│   ├── data/
│   ├── images/
│   ├── js/
│   ├── layouts/
│   ├── site/
│   └── static/
├── package.json
└── spig.mjs
```

These folders are used by default **Spignite** operations. If you wish, you can use whatever structure you like with your own operations.

Let's see what these folders are for.

### out

The resulting website will be created here. Note that **Spignite** does not clear this folder on the build! During the development, files can be accumulated while you are working on the website. Make sure you clean this folder before the deployment.

### src

The root folder for the whole website content, including a few global configuration files.

### src/config

Additional configuration of used 3rd party tools. For example, you can define here additional nunjucks filters, tweak parameters for minimization, etc.

### src/css

Process all `*.sass` files with the SASS compiler. Process all `*.css` files with precss-alike operator.

### src/data

Put any number of data `*.json` files here. **Spginite** will read them and make them available within the _site context._

Data files are usually used for the generation of data-driven sites. For example, data can be a list of books and their authors. Or a conference schedule, with talks and speakers information.

### src/images

Put all the images that you might want to process: either resize to fit certain width or height or just optimize.

Please note that image operations are lengthy and require more processor power. It is advisable to prepare all images before site processing.

### src/js

Home of all websites JavaSript files.

**Spignite** has a concept of javascript _bundles._ When a folder is named as `*.js` - all its JavaScripts will be merged into one output file named as a folder. JavaScript bundles are cool for splitting large javascript files into small ones for development.

### src/layouts

The root for page layouts.

### src/site

The site's content; usually written in Markdown. **Spignite** supports any renderer engine so that you can write content in e.g., Nunjucks, too - helpful on complex pages.

You can mix various content types.

This folder may contain additional resources, like images.

### src/static

Files that will be blindly copied to the output.

### spig.mjs

The **Spignite** website definition. While defaults are not mandatory, it is advisable to have them enabled.&#x20;

```javascript
const { Spig } = require('spignite');

Spig.hello();

// user operations

Spig.run();
```
