# stencila-multi

Demo for Stencila &amp; Dar on binder with multiple documents in one repository.

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/binder-examples/stencila-multi/master?urlpath=stencila)

Learn more about [Stencila](https://stenci.la/) and it's integration with [Binder](https://mybinder.org/) in this blog post: [TODO](TODO)

`repo2docker` automatically picks up all `manifest.xml` files and `*.jats.xml` files in a repository.
The repository demonstrates how to

- override the default MRAN date for R and install additional R packages, see files in the `binder/` directory
- select a specific Stencila document in the Stencila UI on Jupyter Hub

If you want to install a specific version of Stencila, e.g. the `stencila` R package or `stencila/py`, or the `stencila-host` npm package, then you must configure your own `Dockerfile`.

`repo2docker` goes through all directories and uses the first discovered `manifest.xml` as the default, in this case `article/manifest.xml` (with R code).
To open the document in the directory `brticle`, append the URL parameter `archive=<directory>`:

```
http(s)://<server:port>/stencila/?archive=article
```

**Important notes**

- nested directories do not work, only documents at the same levels as the last discovered one can be opened.
- only the source code languages of the first Dar are supported (in our example the Python Jupyter code cell one still works, because Jupyter is always installed, but other cells not)
