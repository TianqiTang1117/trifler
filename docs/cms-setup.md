# Writing on Trifler

The public website runs on GitHub Pages. [Pages CMS](https://app.pagescms.org/) is the hosted editing interface. Articles and images stay in the GitHub repository; no separate server is required.

## First connection

1. Open [Pages CMS](https://app.pagescms.org/) and sign in with GitHub.
2. If GitHub asks to install the Pages CMS app, choose **Only select repositories** and select `TianqiTang1117/trifler`.
3. Open that repository and its `main` branch in Pages CMS.
4. The repository's `.pages.yml` creates **Notes & articles**, **About**, **Site identity**, and **Images** entries.

Installation is a one-time account authorization. Until it is completed and the repository has been opened successfully, the CMS configuration is prepared but the hosted editing connection has not been verified.

## Write and publish

1. In **Notes & articles**, create a new entry.
2. Enter a title and a short English **URL slug**, such as `lidar-time-sync`.
3. Choose the **Publication date** in Shanghai time. Filenames use that field, for example `_posts/2026-10-20-lidar-time-sync.md`, including when adding an older note.
4. Add up to two categories, any tags, and an optional summary or cover image.
5. Write the article in Markdown.
6. Leave **Publish on the website** off while drafting. Turn it on and save when ready.
7. Check the repository's **Actions** tab. Once the deployment succeeds, refresh [Trifler](https://tianqitang1117.github.io/trifler/).

Saving sends a Git commit to the selected branch. The website updates after the configured GitHub Actions build and deployment finish. Drafts are excluded from the website, but this is a public repository: their Markdown and uploaded images remain publicly accessible on GitHub.

New files use the selected date and slug. Keep the generated `YYYY-MM-DD-slug.md` filename. Changing the date later does not automatically rename an existing file. Keep a published slug stable, since changing it changes the article URL.

The CMS date picker saves a calendar date (`yyyy-MM-dd`). Jekyll interprets it at midnight using the site's `timezone: Asia/Shanghai`. The picker's initial value follows the browser's local calendar, so check the date if writing while abroad. For timestamps down to the second, edit the Markdown front matter directly on GitHub with an explicit value such as `2026-10-20 14:30:00 +0800`; this simplified CMS date picker is intended for date-only entries. Future-dated posts require a deployment on or after their publication date.

## Markdown examples

The body uses a Markdown source editor so technical notation remains intact. There is no rich-text conversion step.

````markdown
## What I learned

A short paragraph with **emphasis** and a [link](https://example.com).

```python
def hello():
    print("Hello, Trifler")
```

![A descriptive image caption](/assets/img/posts/example.webp)

$$
E = mc^2
$$

```mermaid
flowchart LR
  Idea --> Experiment --> Note
```
````

Enable **Math formulas** or **Mermaid diagrams** on articles that need them. For code containing literal Liquid delimiters, consult [Chirpy's writing guide](https://chirpy.cotes.page/posts/write-a-new-post/#code-block).

## Images and site details

Upload inline images through **Images**, then use `/assets/img/posts/your-file.webp` in Markdown. The **Cover image** field can also upload and select an image. Files are committed under `assets/img/posts/`. Chirpy adds the site's `/trifler` base path to both inline and cover images during rendering, so the final public URL is `/trifler/assets/img/posts/your-file.webp`. Do not add `/trifler` manually to image fields or Markdown image paths.

Use **About** to edit the introduction and **Site identity** to change the site name, signature, and short description. The CMS uses merge mode to retain Jekyll and Chirpy configuration keys not shown in these forms. YAML comments and formatting may still be normalized when the CMS saves a file.

The initial identity is:

> **Trifler**
>
> A wanderer in the ocean of knowledge.

## Configuration references

Verified against the official documentation on 2026-10-20:

- [Pages CMS filename tokens](https://pagescms.org/docs/configuration/content/filename/)
- [Date field](https://pagescms.org/docs/configuration/fields/date/)
- [Markdown code field](https://pagescms.org/docs/configuration/fields/code/)
- [Media paths](https://pagescms.org/docs/configuration/media/)
- [Merge mode](https://pagescms.org/docs/configuration/settings/#content)
- [Chirpy article front matter](https://chirpy.cotes.page/posts/write-a-new-post/)
- [Chirpy media URL handling](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/_includes/media-url.html)
- [Jekyll timezone configuration](https://jekyllrb.com/docs/configuration/options/)
