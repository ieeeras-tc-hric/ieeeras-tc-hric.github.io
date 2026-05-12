# IEEE RAS TC HRI&C — Website

Source for the official site of the **IEEE RAS Technical Committee on Human-Robot Interaction and Collaboration**, built with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) and deployed to GitHub Pages.

Live site: **https://ieeeras-tc-hric.github.io/**

## Local development

Requires Python 3.10+.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

mkdocs serve            # preview at http://127.0.0.1:8000
mkdocs build --strict   # production build with broken-link check
```

## Editing content

All pages live in `docs/` as plain Markdown:

| File | Page |
|---|---|
| `docs/index.md` | Home |
| `docs/seminars.md` | Seminar Series |
| `docs/members.md` | Committee chairs and student reps |
| `docs/news.md` | Announcements |
| `docs/resources.md` | Journals, conferences, datasets |
| `docs/social.md` | Social media links |

Site-wide settings (title, nav, theme palette, footer social icons) live in `mkdocs.yml`. Brand tweaks live in `docs/stylesheets/extra.css`.

## Deployment

A push to `main` triggers `.github/workflows/deploy.yml`, which runs `mkdocs gh-deploy` and publishes to the `gh-pages` branch.

### One-time GitHub Pages setup

After the first successful workflow run:

1. Go to **Settings → Pages** in the GitHub repo.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Set **Branch** to `gh-pages` and folder to `/ (root)`.
4. Save. The site will be live at `https://ieeeras-tc-hric.github.io/` within a minute.

## Project structure

```
.
├── mkdocs.yml                  # site config (title, nav, theme)
├── requirements.txt            # mkdocs-material pin
├── .github/workflows/deploy.yml
├── docs/
│   ├── index.md  seminars.md  members.md  news.md  resources.md  social.md
│   ├── assets/                 # logo + favicon
│   └── stylesheets/extra.css
├── assets/imgs/logo/           # original logo source files
└── readme/members.txt          # source-of-truth member list
```

## License

Content © 2026 IEEE RAS Technical Committee on Human-Robot Interaction and Collaboration. The site framework is MIT-licensed via Material for MkDocs.
