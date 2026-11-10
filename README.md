# Personal Portfolio & Content Site

Source for [jasonwboyd.com](https://www.jasonwboyd.com), a personal website with articles hosted with GitHub Pages. The site introduces my work in software engineering, manufacturing, and data, and collects project write-ups and articles about personal interests.

## Technologies

- **[Hugo](https://gohugo.io/)** generates the site as static HTML, CSS, and other assets.
- **[Blowfish](https://blowfish.page/)** is the Hugo theme. It is included as a Git submodule at `themes/blowfish`.
- **Markdown** is used for pages and articles, with Hugo and Blowfish shortcodes for interactive or styled content such as the homepage introduction.
- **TOML** files in `config/_default/` configure Hugo, the theme, menus, language, and Markdown rendering.
- **CSS** in `assets/css/custom.css` provides small site-specific layout adjustments on top of the theme.

## Design and content

The site uses Blowfish's **Fire** color scheme with a dark default appearance and automatic light/dark switching. Its landing-page layout features an introduction and recent articles; article and list pages use image-led cards, breadcrumbs, dates, reading time, a table of contents, and reading progress. Search, code-copy buttons, and the appearance switcher are enabled.

Content focuses on software and data work, manufacturing systems, projects, and interests outside work. The navigation groups projects into main and mini projects, alongside articles. Hugo taxonomies are configured for tags, categories, authors, and series.

## Repository layout

| Path | Purpose |
| --- | --- |
| `config/_default/` | Hugo, Blowfish, language, menu, and markup configuration |
| `content/` | Homepage, article listings, and Markdown content |
| `assets/` | Processed site assets, including custom CSS and images |
| `static/` | Files copied directly to the generated site, such as favicons |
| `themes/blowfish/` | Blowfish theme submodule |
| `public/` | Generated site output; ignored by Git |

## Run locally

Install [Hugo](https://gohugo.io/installation/) first, then initialize the theme submodule and start the development server:

```sh
git submodule update --init --recursive
hugo server
```

Open the local URL printed by Hugo. To preview draft content as well, run `hugo server -D`.

Build the static site with:

```sh
hugo
```

Hugo writes the generated site to `public/`. That directory is build output and is intentionally excluded from version control.

## Writing content

Add pages and articles under `content/` as Markdown files. Hugo front matter supplies metadata such as the title, date, summary, tags, and draft status. Existing examples are in `content/`; the homepage is `content/_index.md`. Site-wide appearance and behavior can be adjusted in `config/_default/params.toml`, while the menu is defined in `config/_default/menus.en.toml`.

## Hosting

The production base URL is configured as `https://www.jasonwboyd.com` in `config/_default/hugo.toml`. The site is hosted with GitHub Pages; its publishing configuration is managed by the repository's GitHub Pages setup.
