# Conspiral Compliance Site Deployment

This folder is a standalone static website for `conspiral.co.uk`. It does not import or modify the Conspiral app.

## Pages

- Home: `https://conspiral.co.uk/`
- Privacy Policy: `https://conspiral.co.uk/privacy/`
- Account deletion: `https://conspiral.co.uk/delete-account/`
- Support: `https://conspiral.co.uk/support/`

## GitHub Pages

1. Push the `web-page` branch to GitHub.
2. In GitHub, open `alexAcRohafza/Conspiracy-game`.
3. Go to `Settings > Pages`.
4. Under `Build and deployment`, set `Source` to `GitHub Actions`.
5. Open the `Actions` tab and run or wait for `Deploy Conspiral compliance site`.
6. After the first successful deploy, return to `Settings > Pages`.
7. Set `Custom domain` to `conspiral.co.uk`.
8. Wait for DNS/certificate checks to pass, then enable `Enforce HTTPS`.

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

## Google Play URLs

After HTTPS works:

- Privacy Policy URL: `https://conspiral.co.uk/privacy/`
- Account deletion URL: `https://conspiral.co.uk/delete-account/`
