# Chulapa on Netlify

This repository demonstrates the [Chulapa Jekyll theme](https://github.com/dieghernan/chulapa) on [Netlify](https://chulapatest.netlify.app/) using a remote theme.

[![Netlify Status](https://api.netlify.com/api/v1/badges/9cdb24a4-d2ff-44b3-99a8-4530849ff5e1/deploy-status)](https://app.netlify.com/sites/chulapatest/deploys)

## Getting started

1. Clone or fork this repository and connect it to a Netlify site.
2. Edit `_config.yml`: set your title, description, author and repository.
3. Set `url` to your Netlify or custom domain and `baseurl` to `""` for a site hosted at the domain root.
4. Replace the sample posts, pages, images and navigation links.
5. In Netlify, set the build command to `bundle exec jekyll build`, the publish directory to `_site` and the build environment variable `JEKYLL_ENV` to `production`. Ruby 3.4 is declared in `.ruby-version`. See the [Netlify build configuration reference](https://docs.netlify.com/build/configure-builds/file-based-configuration/).

## Run locally

Install Ruby and Bundler, then run these commands from the repository directory:

```sh
bundle install
bundle exec jekyll serve --host localhost --baseurl ""
```

Open <http://localhost:4000>. Restart Jekyll after editing `_config.yml`.
This repository uses Ruby 3.4 and Jekyll 4.4. Its optional GitHub Pages workflow also uses Ruby 3.4.

## Configuration

[`_config.yml`](_config.yml) follows the current Chulapa configuration
structure:

- Site settings, social locales, author and optional JSON-LD publisher.
- Font Awesome, analytics, search and comment providers.
- Navigation, footer, fonts, skins and syntax highlighting.
- Pagination, collections, front matter defaults and Jekyll settings.

Blank settings use theme defaults where available. Replace the sample content
and identity settings before publishing. Image metadata must describe the actual
image.

The template uses Fuse.js search, four posts per blog page and a Markdown
cheatsheet collection. Autotheming is enabled with `lightskyblue` as the primary
color.

## Page options and examples

[`_pages/theme-options.md`](_pages/theme-options.md) demonstrates options
available in Chulapa 2.1.0: independent `seo_title` and `og_title`, a shared
`description`, social image metadata, page language, Open Graph locales,
`og_type: article`, `schema_image` and video metadata.

Use `canonical_url` only when a page should identify a different canonical URL;
ordinary pages use their generated URL. Set `robots: "noindex, follow"` for
pages such as search results, as shown in
[`_pages/search.md`](_pages/search.md). Robots metadata does not remove a page
from the sitemap; use `sitemap: false` when needed.

[`_pages/minimal-header.md`](_pages/minimal-header.md) demonstrates `layout:
minimal` with `show_header: true`.

See the complete [page and snippet reference](https://dieghernan.github.io/chulapa/docs/04-layouts), [site configuration](https://dieghernan.github.io/chulapa/docs/02-config) and [theming guide](https://dieghernan.github.io/chulapa/docs/03-theming).

## Included content

- Sample posts, a paginated blog and year, category and tag archives.
- Markdown and kramdown cheatsheets.
- A Bootstrap component demo and a 404 page.
- Fuse.js search, an Atom feed, an RSS feed and a generated sitemap.
- An optional GitHub Actions workflow for GitHub Pages. Its build sets the project base path automatically.
- Custom include hooks in [`_includes/custom/`](_includes/custom/) and CSS in [`assets/css/`](assets/css/).
- Optional Algolia indexing workflow in [`.github/workflows/algolia-search.yml`](.github/workflows/algolia-search.yml).

## Theme updates

```yaml
remote_theme: dieghernan/chulapa
```

The remote theme follows Chulapa's default branch without pinning a release. A
fresh build downloads the theme from that branch, so rebuilding can pick up
upstream changes even without editing this repository. The examples have been
updated for Chulapa 2.1.0.

Theme updates do not replace this repository's configuration, content or local overrides. Review the [Chulapa changelog](https://github.com/dieghernan/chulapa/blob/main/CHANGELOG.md) when updating. `bundle update` updates Ruby dependencies, not the remote theme version.
