# Conspiral Website Deployment

This repository is the public static website for `conspiral.co.uk`. It is separate from the private Conspiral game app repository.

## Required Public Pages

- Home: `https://conspiral.co.uk/`
- Privacy Policy: `https://conspiral.co.uk/privacy/`
- Account deletion: `https://conspiral.co.uk/delete-account/`
- Support: `https://conspiral.co.uk/support/`

## Repository Layout

The repo root should contain:

```text
index.html
privacy/index.html
delete-account/index.html
support/index.html
assets/styles.css
assets/conspiral-logo.png
assets/conspiracy_board_bg.png
.nojekyll
DEPLOY.md
```

## GitHub Pages Setup

Use GitHub Pages in the simplest available mode.

1. Push this repo to GitHub.
2. In GitHub, open `alexacrohafza/conspiral-web-page`.
3. Go to `Settings > Pages`.
4. If the `Source` dropdown allows it, choose `Deploy from a branch`.
5. Select:
   - Branch: `main`
   - Folder: `/ (root)`
6. Click `Save`.
7. Wait for GitHub Pages to publish.

If the screen keeps `Source` set to `GitHub Actions` and shows a `Static HTML` card, click `Static HTML > Configure`, then commit the generated workflow. This is GitHub's built-in static site workflow. Do not add a custom workflow unless you decide to use this GitHub-provided option.

## Temporary GitHub Pages URL

Before adding the custom domain, test:

- `https://alexacrohafza.github.io/conspiral-web-page/`
- `https://alexacrohafza.github.io/conspiral-web-page/privacy/`
- `https://alexacrohafza.github.io/conspiral-web-page/delete-account/`
- `https://alexacrohafza.github.io/conspiral-web-page/support/`

If images or styling fail to load, check the relative paths in the HTML and CSS.

## Custom Domain

After the temporary GitHub Pages URL works:

1. Go to `Settings > Pages > Custom domain`.
2. Enter `conspiral.co.uk`.
3. Click `Save`.
4. GitHub may create a `CNAME` file automatically. If it does not, create `CNAME` in the repo root containing exactly:

```text
conspiral.co.uk
```

## Namecheap DNS

In Namecheap, open `Domain List > conspiral.co.uk > Manage > Advanced DNS`.

Remove conflicting parking, redirect, or old records for `@` and `www`, then add:

| Type | Host | Value | TTL |
| --- | --- | --- | --- |
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |
| CNAME Record | www | alexacrohafza.github.io | Automatic |

DNS changes can take minutes to several hours. GitHub may take additional time to issue the HTTPS certificate.

When DNS checks pass in GitHub Pages settings, enable `Enforce HTTPS`.

## Google Play URLs

- Privacy Policy URL: `https://conspiral.co.uk/privacy/`
- Account deletion URL: `https://conspiral.co.uk/delete-account/`
