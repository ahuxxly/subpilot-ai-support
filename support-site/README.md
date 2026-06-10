# SubPilot AI Support Site

This static site is a deployment-ready draft for the App Store Support URL and Privacy Policy URL.

Before publishing:

1. Configure the release contact values with `scripts/configure-release-contact.ps1`.
2. Deploy the folder to a stable HTTPS host.
3. Put the deployed support page URL in App Store Connect as Support URL.
4. Put the deployed privacy page URL in App Store Connect as Privacy Policy URL.

Configuration command from the repository root:

```powershell
powershell -ExecutionPolicy Bypass -File scripts\configure-release-contact.ps1 -SupportEmail "support@domain.tld" -SupportUrl "https://domain.tld" -PrivacyUrl "https://domain.tld/privacy"
```

Recommended first hosting options:

- GitHub Pages from this repository.
- Vercel static deployment.
- Any simple HTTPS static host controlled by the developer account holder.

## GitHub Pages

The repository includes `.github/workflows/support-site-pages.yml`. After the repository is pushed to GitHub, enable Pages for GitHub Actions deployments in the repository settings, then run the workflow. Use the resulting Pages URL as:

- App Store Support URL: `/`
- App Store Privacy Policy URL: `/privacy`

## Vercel

Deploy this folder as the Vercel project root. The included `vercel.json` enables clean URLs, so use:

- App Store Support URL: `/`
- App Store Privacy Policy URL: `/privacy`
