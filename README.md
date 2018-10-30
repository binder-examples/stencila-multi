# stencila-r

Demo for Stencila &amp; Dar on binder with multiple documents in one repository.

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/nuest/stencila-multi/master)

Learn more about [Stencila](https://stenci.la/) and it's integration with [Binder](https://mybinder.org/) in this blog post: [TODO](TODO)

`repo2docker` automatically picks up all `manifest.xml` files and `*.jats.xml` files in a repository.
The repository demonstrates how to

- override the default MRAN date for R and install additional R packages, see files in the `binder/` directory
- select a specific Stencila document in the Stencila UI on Jupyter Hub

If you want to install a specific version of Stencila, e.g. the `stencila` R package or `stencila/py`, or the `stencila-host` npm package, then you must configure your own `Dockerfile`.

`repo2docker` goes through all directories and uses the last discovered `manifest.xml` as the default, in this case `brticle/manifest.xml`.
To open the document in the directory `article/doc/manifest.xml`, append the URL parameter `archive=<directory>`:

```
http(s)://<server:port>/stencila/?archive=article/doc
```
