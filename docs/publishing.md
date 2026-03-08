# Publishing

This repository is set up to publish documentation to GitHub Pages with MkDocs Material.

## Files used for publishing

- `mkdocs.yml`
- `requirements-docs.txt`
- `.github/workflows/pages.yml`

## One-time GitHub setup

1. Push this repository to GitHub.
2. Open the repository settings.
3. Go to **Pages**.
4. Set the source to **GitHub Actions**.
5. Update the `site_url` value in `mkdocs.yml` to match your real Pages URL.

For a project site, the URL usually looks like:

```text
https://<org-or-user>.github.io/<repo>/
```

## Local preview

Install the docs dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements-docs.txt
```

Start a local preview server:

```bash
mkdocs serve
```

Build the static site locally:

```bash
mkdocs build --strict
```

## Automatic deployment

The GitHub Actions workflow publishes the site when changes are pushed to the `main` branch.

It will:

1. install Python
2. install the docs dependencies
3. build the site with MkDocs
4. upload the built site
5. deploy it to GitHub Pages

## Updating the published site

Any change to content in `docs/`, navigation in `mkdocs.yml`, or the publishing workflow will be reflected the next time the workflow runs.

## Troubleshooting

### The site builds locally but not in GitHub Actions

Run this locally first:

```bash
mkdocs build --strict
```

Then check for:

- broken links
- invalid navigation paths
- missing dependencies
- Markdown syntax issues

### The Pages URL is wrong

Update `site_url` in `mkdocs.yml` to the final GitHub Pages address for the repository.

### The workflow runs but nothing changes

Confirm that:

- the repository default branch is `main`
- GitHub Pages is configured to use **GitHub Actions**
- the workflow file is present at `.github/workflows/pages.yml`
