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

## Build & deploy

Deployment is automatic: the [`.github/workflows/hugo.yml`](.github/workflows/hugo.yml) workflow builds the site
with [Hugo](https://gohugo.io/) and deploys it to [GitHub Pages](https://pages.github.com/) on every push to `main`.

It currently publishes to https://tuck1s.github.io/espops.com/. Once a custom domain is configured for this repo
under Settings > Pages, the workflow's `--baseURL` (taken from `actions/configure-pages`) will pick that up
automatically and start publishing to it instead — no workflow changes needed.

To build locally (e.g. to sanity-check the output):

```
cd source
hugo --minify --destination ../public
```
