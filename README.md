# Hannah Yao Personal Website

Jekyll/al-folio personal academic website for research, projects, blog posts, and fun notes.

Public URL after GitHub Pages is enabled:

```text
https://hannahyao-hy.github.io/Personal-website/
```

## Local Development

```bash
bundle install
npm install
bundle exec jekyll serve --baseurl "" --host 127.0.0.1 --port 4000
```

Open `http://127.0.0.1:4000/`.

## Main Content Files

- `_pages/about.md`: homepage bio and profile section
- `_pages/publications.md`: research page at `/research/`
- `_projects/`: project cards and detail pages
- `_posts/`: blog posts
- `_news/`: homepage news items
- `_bibliography/papers.bib`: publications
- `_data/socials.yml`: social/contact links
- `_data/cv.yml`: structured CV data
- `assets/img/`: headshot and project images

## Deployment

The workflow in `.github/workflows/deploy.yml` builds and deploys the site through GitHub Pages Actions. In the GitHub repository settings, set Pages to use **GitHub Actions** as the source.

This site is based on the MIT-licensed [al-folio](https://github.com/alshedivat/al-folio) theme.
