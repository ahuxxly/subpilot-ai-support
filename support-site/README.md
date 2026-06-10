# SubPilot AI Support Site

This static site is published as the App Store Support URL and Privacy Policy URL.

Current public deployment:

- Support URL: https://ahuxxly.github.io/subpilot-ai-support/
- Privacy Policy URL: https://ahuxxly.github.io/subpilot-ai-support/privacy.html
- Support form: https://github.com/ahuxxly/subpilot-ai-support/issues/new?template=support.yml
- Public support repository: https://github.com/ahuxxly/subpilot-ai-support

The iOS source repository remains private. The support site is deployed from a separate public repository because the current GitHub plan does not support Pages for private repositories.

Before App Store submission:

1. Keep the support and privacy URLs stable.
2. Put the deployed support page URL in App Store Connect as Support URL.
3. Put the deployed privacy page URL in App Store Connect as Privacy Policy URL.
4. Add a real App Review contact email with `scripts/configure-release-contact.ps1` or `fastlane/metadata/review_information/email_address.txt`.

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
