# Looply Website

Small static marketing and support website for Looply, an iPhone app for recurring things.

Looply's core promise:

> Log what happened. Looply learns what repeats and predicts what comes next.

The site is intentionally simple: plain HTML, one shared CSS file, no JavaScript, no frameworks, and no build step. It is ready to host on GitHub Pages.

## Pages

- `index.html` - landing page with hero, app preview, use cases, privacy note, and TestFlight CTA.
- `privacy.html` - clean privacy policy for the current local-first app model.
- `support.html` - support contact page with a short FAQ.
- `styles.css` - shared responsive styling for all pages.
- `assets/looply-app-icon.png` - web-sized copy of the original Looply app icon.

## Local Preview

From the repository root:

```bash
python3 -m http.server 8765 --directory website
```

Then open:

```text
http://localhost:8765
```

You can also open `website/index.html` directly in a browser, but the local server is closer to how GitHub Pages serves the site.

## GitHub Pages Deployment

Recommended setup:

1. Commit the `website/` folder.
2. Push it to GitHub.
3. In the repository settings, open `Pages`.
4. Set the publishing source to the branch you use for the website.
5. Set the folder to `/website` if GitHub Pages offers that option for the repository.

If GitHub Pages only offers root or `/docs`, either move these files to `/docs` or configure a separate deployment branch.

The site uses relative links such as `privacy.html` and `support.html`, so it works on both a custom domain and a GitHub Pages project URL.

## Common Edits

### TestFlight Link

Replace the placeholder `#` in `index.html`:

```html
<a class="button button-primary" href="#">Join TestFlight</a>
```

Use the real public TestFlight link when it is ready.

### Contact Email

Replace `hello@example.com` in:

- `index.html`
- `privacy.html`
- `support.html`

Keep the visible email and `mailto:` link in sync.

### Privacy Date

Update the effective date in `privacy.html` when the policy changes:

```html
Effective date: July 2026
```

Only update privacy claims when the app behavior really matches them.

### App Icon

The website icon is a resized copy of:

```text
../assets/branding/looply-app-icon-master.png
```

If the app icon changes, regenerate or replace:

```text
assets/looply-app-icon.png
```

Keep the website copy small enough for fast loading.

## Design Notes

- Calm Apple-like visual direction.
- Soft green brand palette.
- Mobile-first layout.
- No stock photos.
- CSS phone mockup instead of screenshots for now.
- Privacy-first positioning: local data, no account, no ads, no tracking.

## Maintenance Checklist

Before publishing:

- Check all navigation links.
- Replace the TestFlight placeholder.
- Replace the contact email placeholder.
- Confirm privacy policy text matches the current app behavior.
- Preview on mobile and desktop.
- Keep the site dependency-free unless there is a strong reason to change that.
