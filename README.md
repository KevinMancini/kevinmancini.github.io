# Kevin Mancini website

This repository is a GitHub Pages / Jekyll website with four main goals:

1. a clean landing page,
2. a structured academic profile,
3. a blog-style sport journal,
4. a blog-style art journal.

## Structure

- `index.md` - homepage
- `academy.md` - academic profile
- `sport.md` - sport archive page
- `art.md` - art archive page
- `_data/` - academic content and links
- `_sport/` - sport posts
- `_art/` - art posts
- `_layouts/` - shared page templates
- `assets/css/style.css` - styling
- `templates/` - example post templates

## How to update the academic section

Edit the YAML files in `_data/`:

- `profile.yml`
- `education.yml`
- `research.yml`
- `experience.yml`
- `publications.yml`
- `talks.yml`
- `awards.yml`

The academy page renders automatically from these files.

## How to add a sport story

1. Copy `templates/sport-post-template.md` into `_sport/`.
2. Rename it, for example: `_sport/2026-02-10-dolomites-winter-route.md`
3. Update the title, date, excerpt, location, tags, and cover image.
4. Add your photos to `assets/images/sport/`.
5. Commit and push to GitHub.

## How to add an art post

1. Copy `templates/art-post-template.md` into `_art/`.
2. Rename it, for example: `_art/2026-02-18-bach-practice-notes.md`
3. Update the front matter and body.
4. Add images to `assets/images/art/` if needed.
5. Commit and push to GitHub.

## Hosting on GitHub Pages

If the repository is named `kevinmancini.github.io`, GitHub Pages will serve it from the root automatically.

If you host it in a project repository instead, set the repository name in `baseurl` inside `_config.yml`.
