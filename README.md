# OLC Planner launcher

The home screen page for the OLC Planner, served at **https://planner.ozarkleather.co** from GitHub Pages.

The planner is a Google Apps Script web app. Apps Script always serves Google's own outer page, so iPhone can't read an icon or full-screen setting from the app. This page sits in front of it and carries them.

| File | Purpose |
|---|---|
| `index.html` | Icon and full-screen tags, Add to Home Screen steps, forward to the planner |
| `manifest.webmanifest` | Web app manifest (`display: standalone`) |
| `apple-touch-icon.png` | iPhone home screen icon (the bear) |
| `icon-512.png` | Manifest icon |
| `favicon.png` | Browser tab icon, also used by the planner itself |
| `CNAME` | The custom domain for GitHub Pages |

## How it decides

- **Phone, normal Safari tab:** stays on screen with the Add to Home Screen steps, so the icon is added from this page and iPhone uses these tags.
- **Launched from the home screen icon:** runs full screen (`navigator.standalone`), forwards straight into the planner, and stays full screen.
- **Computer:** forwards straight away.

`APP_URL` in `index.html` must be the versioned `/exec` deployment, never `@HEAD`. Redeploying that deployment (`clasp create-deployment -i <id>`) keeps the URL, so app updates need no change here.

## DNS

`planner` is a CNAME record pointing to `tannerforsyth.github.io`, set where ozarkleather.co's DNS is managed.

The app's source lives in the private `olc-planner` repo; the icons come from its `assets/` folder.
