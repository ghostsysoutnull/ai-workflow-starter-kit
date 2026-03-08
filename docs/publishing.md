# Publishing

This repository is set up to publish documentation to GitHub Pages with Jekyll using the Hacker theme.

## Files used for publishing

- `_config.yml`
- `Gemfile`
- `.github/workflows/pages.yml`

## One-time GitHub setup

1. Push this repository to GitHub.
2. Open the repository settings.
3. Go to **Pages**.
4. Set the source to **GitHub Actions**.
5. Confirm the `url` and `baseurl` values in `_config.yml` match the repository URL.

For a project site, the URL usually looks like:

```text
https://<org-or-user>.github.io/<repo>/
```

## Local preview

Install the site dependencies:

```bash
bundle install
```

Start a local preview server:

```bash
bundle exec jekyll serve
```

Build the static site locally:

```bash
bundle exec jekyll build
```

## Automatic deployment

The GitHub Actions workflow publishes the site when changes are pushed to the `main` branch.

It will:

1. install Ruby and bundle dependencies
2. build the site with Jekyll
3. apply the Hacker theme
4. upload the built site
5. deploy it to GitHub Pages

## Updating the published site

Any change to content in `docs/`, configuration in `_config.yml`, or the publishing workflow will be reflected the next time the workflow runs.

## Troubleshooting

### The site builds locally but not in GitHub Actions

Run this locally first:

```bash
bundle exec jekyll build
```

Then check for:

- broken links
- invalid configuration values
- missing gems
- Markdown syntax issues

### The Pages URL is wrong

Update `url` and `baseurl` in `_config.yml` to the final GitHub Pages address for the repository.

### The workflow runs but nothing changes

Confirm that:

- the repository default branch is `main`
- GitHub Pages is configured to use **GitHub Actions**
- the workflow file is present at `.github/workflows/pages.yml`
