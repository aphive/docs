## Installation

### MkDocs

[MkDocs](https://www.mkdocs.org/) is a fast, simple and downright gorgeous static site generator that's geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file.

```
pip3 install mkdocs
```

### MkDocs Material Theme

[Material](https://squidfunk.github.io/mkdocs-material/) is a theme for MkDocs, an excellent static site generator geared towards project documentation. It is built using Google's Material Design guidelines.

```
pip3 install mkdocs-material
```

### PyMarkdown Extensions

PyMdown Extensions is a collection of Markdown extensions that add some great features to the standard Markdown library.

```
pip3 install pymdown-extensions
```

### Font Awesome Extensions
```
pip3 install https://github.com/bmcorser/fontawesome-markdown/archive/master.zip
```

### Markdown Include
```
pip3 install markdown-include
```

## Upgrading

To upgrade things you can run the following commands:

#### MkDocs

```
pip3 install mkdocs --upgrade
```

#### MkDocs Material Theme
```
pip3 install --upgrade mkdocs-material
```

## Demo and Launch
### Starting your local site

To start up a local site while you develop run the following command:

```
mkdocs serve
```

If you have no issues, you will see output like this:

```
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 191203 11:07:02 server:296] Serving on http://127.0.0.1:8000
```

Load up that URL in your browser to check out your site as you build. Each time you save a file, the site gets updated automatically after a few seconds.

### Uploading your site

Once you are done with your edits, run the following command to upload your site to Git:

```
mkdocs gh-deploy
```

This will convert your markdown files to html, create a gh-pages branch and set the repo to use that for the site then upload the site files.

To save the actual repository, you would proceed just as you would with a regular repo. Ensure that you are using a `.gitignore` so you don't upload the entire site folder to your repo.
