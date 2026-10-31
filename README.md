# fk-site

A website made of a folder of Markdown: a page of each file, with every page listed beside it and
its own headings on the other side, and every other file, as images, copied as it is.

```sh
fk-site --title "My project" --out site docs
fk-site --title "My project" --out site --serve 8000 docs   # then serves it on localhost:8000
```

Each page's title is its front matter's, `title:` between `---` lines at its start, or its first
heading's, or its file's name. The pages are listed with an index first, `index.md` or `README.md`,
then in the order their front matter's `order:` gives, then by title. A link goes where it means on
the site: to a page by its Markdown, `guide/start.md`, or by its path without `.md`, from the
site's root, `/guide/start`, or from the page, as VitePress writes them; to `#a-heading` on it, as
each heading has an id as GitHub gives one; and to a file from the site's root, there or in
`public`. fckt's code, in a block marked `fckt` or `kotlin`, is coloured: its keywords, types,
strings, numbers, comments and annotations. Links are written from where each page is, so the site works wherever it's put, served
or opened from its folder.

`--serve` serves the site once it's made, with fk-http: each file at its path, read each time it's
asked for, so the site can be made again while it's served.

It's fk-markdown, fk-html, fk-cli and fk-http together: `Pages` reads a page, `Layout` writes it, with the
site's navigation and a stylesheet of its own, light or dark as the reader's system is, and `Sites`
does it for a folder.

## Building

```sh
kiln build                 # compiles and tests it
build/bin/fk-site --help
```
