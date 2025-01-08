# eleventy-files-minifier

This plugin was forked from https://github.com/benjaminrancourt/eleventy-plugin-files-minifier. Currently it includes modification to the code to address vulnerabilities introduced by html-minifier, which have been addressed by switiching out the dependency.

This plugin allows you to automatically **minify** files when builting with **[Eleventy](https://www.11ty.dev/)**.
It currently supports `css`, `html`, `json`, `xml`, `xsl` and `webmanifest` files.

Why should you minify your files? Simply to reduce the data transfered between your hosting servers and your visitors,
even if some of them maybe some bots.

Under the hood, this plugin use the following plugins to minify code:

- [pretty-data](https://www.npmjs.com/package/pretty-data): `css`, `json`, `xml` and `webmanifest`
- [html-minifier](https://www.npmjs.com/package/html-minifier): `html` and `xsl`

## Usage

The plugin will automatically minify supported files, you don't need to do anything except the installation!

Make sure that the files you want to minify are currently written by Eleventy. If not, you can easily rename it and add
Front matter options. For example, for the `manifest.webmanifest` file, I could rename it as `manifest.webmanifest.njk`
and add the following code at his top:

```yaml
---
eleventyExcludeFromCollections: true
permalink: /manifest.webmanifest
---
```

## Publish

Increment the `version` defined in the `package.json` file and run the command below to publish the module in the
registry:

```bash
# Dry run
npm publish --dry-run

# For real (are you really sure?)
npm publish --access public
```

## License

The [MIT License][1] (MIT)

[1]: https://opensource.org/licenses/MIT
