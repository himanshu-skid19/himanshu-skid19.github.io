# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based academic website using the **al-folio** theme. It's designed for academics to showcase their publications, projects, CV, and blog posts. The site is configured to be deployed to GitHub Pages at `himanshu-skid19.github.io`.

## Development Commands

### Local Development (Recommended - Docker)
```bash
# Pull and start the development server
docker compose pull
docker compose up

# For slimmed docker image (< 100MB)
docker compose -f docker-compose-slim.yml up

# Build custom docker image
docker compose up --build

# Debug docker issues
docker compose up -d
docker compose logs
docker compose exec -it jekyll /bin/bash
```
The site will be available at `http://localhost:8080`.

**Note for Windows users:** Docker is recommended. If using native Ruby, use WSL (Windows Subsystem for Linux) to avoid compatibility issues.

### Local Development (Legacy - Ruby/Bundler)
```bash
# Install dependencies
bundle install
pip install jupyter

# Start development server
bundle exec jekyll serve
```
The site will be available at `http://localhost:4000`.

### Build and Deployment
```bash
# Build static site
bundle exec jekyll build

# Build with custom destination
bundle exec jekyll build --destination /path/to/destination

# Purge unused CSS (optimization)
purgecss -c purgecss.config.js

# Code formatting
npx prettier --write .
```

## Project Structure

- **Content Collections:**
  - `_posts/` - Blog posts with dates (YYYY-MM-DD format)
  - `_projects/` - Project portfolio items
  - `_news/` - News/announcement items (displayed on homepage)
  - `_books/` - Book reviews/recommendations
  - `_pages/` - Static pages (about, CV, publications, etc.)

- **Data Files:**
  - `_data/cv.yml` - CV/Resume data (fallback if JSON not found)
  - `_data/repositories.yml` - GitHub repository showcase configuration
  - `_data/coauthors.yml`, `_data/venues.yml` - Academic publication metadata
  - `assets/json/resume.json` - JSON Resume format (preferred for CV)

- **Configuration:**
  - `_config.yml` - Main Jekyll configuration
  - `_bibliography/papers.bib` - Academic publications in BibTeX format
  - `Gemfile` - Ruby dependencies
  - `package.json` - Node.js dependencies (Prettier for formatting)

## Key Features and Customization Points

### Site Metadata
- Set `title`, `first_name`, `last_name` in `_config.yml`
- Configure `url` and `baseurl` for deployment
- Update `description` and `keywords` for SEO

### Academic Features
- Publications auto-generated from `_bibliography/papers.bib`
- CV can be JSON Resume format (`assets/json/resume.json`) or YAML (`_data/cv.yml`)
- Support for math typesetting (MathJax), code highlighting, and academic citation formats

### Content Management
- Blog posts support categories, tags, and related posts
- Projects support categorization and portfolio display
- News items automatically display on homepage
- All content uses Jekyll front matter for metadata

### Styling and Theming
- Theme colors configured in `_sass/_themes.scss` via `--global-theme-color`
- Dark/light mode toggle available
- Responsive design with Bootstrap grid system
- Social media preview support (Open Graph)

## Deployment

The site is configured for automatic GitHub Pages deployment:
1. Push changes to `main` branch
2. GitHub Actions automatically builds and deploys to `gh-pages` branch
3. Site becomes available at `https://himanshu-skid19.github.io`

Manual deployment requires setting GitHub Actions permissions to "Read and write" in repository settings.

## Common Development Tasks

### Adding New Content
- **Blog post:** Create file in `_posts/` with format `YYYY-MM-DD-title.md`
- **Project:** Add file in `_projects/` with appropriate front matter
- **Page:** Add file in `_pages/` or root directory

### Managing Publications
- Add entries to `_bibliography/papers.bib` in standard BibTeX format
- Supported fields: `pdf`, `code`, `website`, `slides`, `poster`, `abstract`, etc.
- Publications auto-sort by year (descending) unless configured otherwise

### Updating CV
- Preferred: Update `assets/json/resume.json` using JSON Resume schema
- Fallback: Update `_data/cv.yml` in YAML format
- JSON format takes precedence if both exist

### Theme Customization
- Colors: Edit `_sass/_themes.scss`
- Layout: Modify files in `_layouts/` and `_includes/`
- Fonts and styles: Update `_sass/` directory files

## Important Notes

### File Modification Workflow
- All changes should be made to the `main` branch
- The `gh-pages` branch is auto-generated - **DO NOT** modify it directly
- Changes to `_config.yml` require a rebuild to take effect
- Other content changes are visible immediately (may need browser refresh)

### BibTeX Publications
- Publications in `_bibliography/papers.bib` are auto-sorted by year (descending)
- Author annotation uses `scholar:last_name` and `scholar:first_name` from `_config.yml`
- Co-author links are managed in `_data/coauthors.yml`
- Supported custom fields: `pdf`, `code`, `website`, `slides`, `poster`, `abstract`, `arxiv`, `bibtex_show`, `blog`, etc.

### Jekyll Plugins and Dependencies
- Core Jekyll plugins are defined in `Gemfile` under `:jekyll_plugins` group
- Node.js dependencies (Prettier for formatting) in `package.json`
- Jekyll Scholar handles bibliography generation
- Jekyll Archives handles post/project categorization