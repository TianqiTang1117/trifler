# Trifler

*A wanderer in the ocean of knowledge.*

Personal notes, reflections, and technical explorations, built with
[Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy).

- Website: https://tianqitang1117.github.io/trifler/
- Writing dashboard: https://app.pagescms.org/tianqitang1117/trifler/main/collection/posts
- Repository: https://github.com/TianqiTang1117/trifler

## Write online

Sign in to Pages CMS with GitHub and open `TianqiTang1117/trifler` on `main`.
The repository's `.pages.yml` defines posts, images, the About page, and site settings.
Write with the visual editor's formatting toolbar and image picker, or switch to
**Source** for advanced Markdown.
See [the writing guide](docs/cms-setup.md) for the publishing workflow.

Saving a published article triggers GitHub Actions. The website updates after
the **Build and Deploy** workflow succeeds.

## Local preview

Use Ruby 3.4 and Bundler:

```sh
bundle install
bundle exec jekyll serve --baseurl /trifler
```

Open http://127.0.0.1:4000/trifler/.

## Deployment

In GitHub **Settings → Pages**, set **Source** to **GitHub Actions**.
The workflow builds the site, checks internal links, and publishes its artifact.

`_config.yml` uses `url: https://tianqitang1117.github.io` and `baseurl: /trifler`.
Change both deliberately if the deployment address changes.

## Credits

Based on the official [Chirpy Starter](https://github.com/cotes2020/chirpy-starter),
with the Chirpy theme using the 7.x compatible release range in `Gemfile`.
The template's MIT license is retained in `LICENSE`.
