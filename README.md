# Folio Community Tweaks

The jailbreak-inspired tweaks for [Folio](https://github.com/McCal-Codes/folio), published as a signed source.
Folio includes this source from the start, so nobody has to add it by hand.

| Tweak | Inspired by | What it does |
|---|---|---|
| **Cabinet** | Velox by Phillip Tennen | Swipe up on an app icon for a small panel with its shortcuts, latest notifications and music controls. |
| **Harborline** | Harbor by Evan Swick | Dock icons swell under your finger as you slide along the dock. |
| **Roll Call** | Axon by Nepeta | A row of app icons above Notification Center. Tap one to show only that app. |
| **Palette** | Velvet by NoisyFlake & HiMyNameisUbik | Notification cards take on a soft version of their app's color. |
| **Colored Albums** | ColorFlow by David Goldman | The music card and the island's sound bars take on the album art's color. |
| **Tilt** | Barrel by Aaron Ash | A page effect: Home pages lean a little as they pass, turning through their middle. |
| **Stack** | Barrel by Aaron Ash | A page effect: Home pages step back as they leave, without turning. |
| **Cylinder** | Barrel by Aaron Ash | A page effect: Home pages turn around their middle, like the sides of a drum. |

Each one is re-created from scratch for Folio, with no tweak code in it, and a package only switches on something
Folio can already do. Every tweak is also in Folio's own Settings, so nothing here is locked behind the source. The
page effects are the exception: each is four numbers (`effect.json`) that Folio's own page engine draws, and
installing one adds it to Settings › Gestures › Page Effects beside Cube and Carousel.

## How it's built

```
packages/<name>/    manifest.json, depiction.json and tweaks.json (effect.json for a page effect) for one tweak
assets/             the source's icon and each tweak's icon
source.json         the source's name, description and featured package
tools/build.py      packs the packages, builds the index and signs it
```

Every push to `main` builds the site, signs it with the key in the `FOLIO_SOURCE_KEY` secret and publishes it to
<https://mccal-codes.github.io/folio-tweaks/>. Without the key the workflow publishes nothing, because Folio
refuses an unsigned source.

Problems with a tweak: [open an issue](https://github.com/McCal-Codes/folio-tweaks/issues). Community themes and
other packages go to [folio-packages](https://github.com/McCal-Codes/folio-packages).
