# SEORCE tag for Google Tag Manager

<img src="assets/seorce-logo-48.png" alt="SEORCE logo" width="48" height="48">

The official [SEORCE](https://seorce.com) Google Tag Manager template. It loads the SEORCE script on your website without code changes. The script powers:

- **SEORCE Web Analytics**: privacy-friendly visitor and event tracking (no cookies, no localStorage).
- **SEORCE AutoFix**: one-click technical SEO fixes such as structured data (JSON-LD), meta tags and internal links, applied live on your pages.

## Setup

1. **Copy your Project ID from SEORCE.**
   In [app.seorce.com](https://app.seorce.com), open your project, click **Install Script** and copy the **Project Identifier** (a 24-character ID such as `6ae196592b4146f493a796af`). Each project has its own ID.
2. **Add the tag in Google Tag Manager.**
   Go to **Tags → New → Tag Configuration → Discover more tag types in the Community Template Gallery**, search for **SEORCE**, and click **Add to workspace**.
3. **Paste your Project ID** into the **Project ID** field.
4. **Set the trigger** to **All Pages** (or **Initialization – All Pages** to load it as early as possible).
5. **Submit and publish** the container.
6. Go back to SEORCE and click **Recheck installation**.

## What the tag does

When it fires, the tag loads one script:

```
https://scripts.seorce.com/api?projectId=<YOUR_PROJECT_ID>&ref=gtm
```

This is the same script as the `<script>` snippet in the SEORCE installation guide. The tag loads it at most once per page, even if it fires more than once (for example on single-page-app history changes).

### Permissions

| Permission | Why |
| --- | --- |
| Injects scripts: `https://scripts.seorce.com/*` | Loads the SEORCE script. |
| Logs to console (debug only) | Shows setup errors in GTM Preview mode. |

## Consent

The SEORCE script does not set cookies or use localStorage. If your consent policy still requires consent before loading it, use the tag's **Advanced Settings → Consent Settings** to require `analytics_storage` (or another consent type) before it fires.

## Troubleshooting

- **"Unverified" in SEORCE:** make sure the GTM container version with the SEORCE tag is **published** (not just saved), then click **Recheck installation**.
- **Don't install it twice:** if you use this tag, remove the `<script>` snippet from your site's `<head>` and any Custom HTML tag with the SEORCE snippet.
- **Debug:** use GTM **Preview** mode. The SEORCE tag should show as *Fired* and `scripts.seorce.com/api` should appear in your browser's Network tab.

## Support

- Website: https://seorce.com
- Report an issue with this template: open an issue in this repository.

## License

Apache 2.0. See [LICENSE](LICENSE).
