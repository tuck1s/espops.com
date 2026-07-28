# espops.com static site

## Setup

The theme (`source/themes/ananke-mod`) is a git submodule. Clone with submodules included:

```
git clone --recurse-submodules https://github.com/tuck1s/espops.com.git
```

or, if already cloned:

```
git submodule update --init --recursive
```

Without this step, `source/themes/ananke-mod` is an empty directory, Hugo has no layout templates, and `hugo server` will fail to render pages (a `404` on every route).

## Preview

The markdown files are in folder `source`.

```
cd source
hugo server
```

## Build

The html is generated using [Hugo](https://gohugo.io/) back into the `/docs` directory, for serving via [Github Pages](https://pages.github.com/).

```
cd source
hugo -D --destination ../docs
```
