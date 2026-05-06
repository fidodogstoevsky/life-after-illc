# Life After ILLC — Website

Live site: https://events.illc.uva.nl/LifeAfterILLC/

## Setup on a new device

### Prerequisites

Install the following:

- [Hugo (extended)](https://gohugo.io/installation/) — the static site generator
- [Node.js](https://nodejs.org/) — required for Tailwind CSS
- [Git](https://git-scm.com/)

### Clone the repo

```
git clone --recurse-submodules git@github.com:fidodogstoevsky/life-after-illc.git
cd life-after-illc
```

The `--recurse-submodules` flag is required to also download the `themes/tella` theme.

### Install dependencies

```
npm install
```

### Run locally

```
hugo server
```

Then open http://localhost:1313 in your browser. Changes to files are reflected live.

---

## Making changes

All content is in the `content/` directory as Markdown files. Edit them directly.

| File | What it controls |
|------|-----------------|
| `content/home.md` | Text shown on the main page below the slideshow |
| `content/event.md` | The 2026 Event page |
| `content/about.md` | The About page |
| `content/archives/` | Past panel posts (one `.md` file per event) |
| `data/slide.json` | Slideshow images and titles |
| `hugo.toml` | Site title, nav menu, favicon, logo |
| `static/css/custom.css` | Custom styles |

### Adding a new archive post

Create a new `.md` file in `content/archives/`:

```markdown
---
title: "Life After ILLC Panel: 2024"
date: 2024-05-01
image: img/your-image.jpg
---

Content goes here.
```

The `date` field controls the order posts appear in. Place any images in `static/img/`.

---

## Deploying to the server

Build and upload in one command:

```
hugo && rsync -avz --progress --chmod=Dg+ws,Fg+w /path/to/life-after-illc/public/ [YOUR UVA ID]@goedel.fnwi.uva.nl:/var/www/illc/events/LifeAfterILLC/
```

Replace `/path/to/life-after-illc` with the actual path on your machine.

You will need SSH access to `goedel.fnwi.uva.nl`. Contact Marco if you do not have access.

---

## Saving changes to GitHub

```
git add -A
git commit -m "describe your changes"
git push
```
