# Rosetta Gaming

**A native Android library manager, downloader, and multi-engine runner for adult games and visual novels.**

> ### 🔞 18+ Content Warning
> Rosetta Gaming is a tool for browsing, downloading, and playing **adult (NSFW) games and visual novels** from public community sources. It does not host or distribute any content itself — it's a client that talks to existing sites and file hosts. **You must be 18 or older (or the age of majority in your jurisdiction) to use this app.** By downloading or running it, you confirm that you meet that requirement and that this kind of content is legal for you to access where you live.

This repository hosts **pre-built APKs and release notes** for public testing. The application's source code lives in a separate private repository during this alpha phase.

---

## What it is

Rosetta Gaming is a single app that replaces the usual "browse a forum on a phone browser → click through an ad-laden shortener → download a `.zip` → find a file manager → extract it → figure out which engine it needs → sideload an emulator/runtime" routine with one native flow: browse, download, and play, all from a single library screen.

## Who it's for

Anyone who plays adult games/VNs on Android and is tired of juggling browser tabs, file-host popups, and separate runner apps for RPGMaker, Ren'Py, and Windows/PC titles. If you already bookmark F95Zone, LewdCorner, or similar sites on your phone, this is built for you.

## Features

- **Native browsing for free sources** — Multiple sources are integrated into a real, scrollable app UI (catalogs, search, user-managed tag filters, detail pages and galleries) instead of an embedded mobile web browser.
- **Encrypted credentials, stored on-device only** — optional login for sites that unlock more content when signed in, and for premium file-host accounts so downloads skip free-tier wait timers and captchas. Nothing leaves your device except the login requests themselves.
- **One download manager, many hosts** — automatic link resolution across MediaFire, GoFile, PixelDrain, Google Drive, Rapidgator, and more, with resumable (Range-request) transfers and a real progress/speed display. Hosts that require solving a real captcha or clicking through an ad page fall back to an in-app browser view — with built-in ad-blocking and popup/click-hijack protection — instead of dumping you into your phone's default browser.
- **Automatic archive handling** — ZIP/RAR/7z extraction, including password-protected and RAR5 archives, with correct handling of non-UTF-8 (Shift-JIS) filenames common in Japanese-authored releases.
- **Multi-engine game runner** — RPG Maker MV/MZ and TyranoScript run through an in-app WebView-based host; Ren'Py games use embedded native runtimes; compatible Godot games use a unified companion; and an experimental PC/Windows runner handles selected WOLF RPG and other Windows titles.
- **A real library** — cover art, categories, source and engine filters, play statistics, version metadata, developer collections and patch/mod management instead of a flat folder of `.zip` files.
- **Torrent/magnet awareness** — if a source's only distribution method is a `.torrent` or magnet link, Rosetta hands it off to your own BitTorrent app rather than pretending to support it.

## What's new in 0.82.0-alpha

- Added on more source with catalogs, search, pagination, tag browsing, details and galleries.
- Made tag filtering transparent and user-controlled for every compatible source, with independent per-source settings and no hidden default filters.
- Added compact source search/tag dialogs, reload-current-page and visited-page navigation.
- Added game versions, Source filtering, total play time, most-played game, most-visited source and last-visited source to the library experience.
- Added cover-card carousels for “More from…”, in-app folder creation and a choice between Rosetta's internal browser and the Android system picker.
- Added transactional Ren'Py/RPG Maker patch and mod management for eligible forum-source games.
- Added Ren'Py 7.8.7 support with a live state editor, encrypted Godot PCK compatibility, portable Electron/NSIS extraction and non-destructive WOLF RPG/GuruGuru compatibility.
- Improved Cloudflare recovery, F95Zone/LewdZone developer metadata, developer social actions and automatic game-version extraction from downloads.
- Fixed dark-mode colors and updated the About screen with the official [Stars Translations](https://www.stars-translations.com/) and [Telegram](https://t.me/nsfwhgames) links.

See the [0.82.0-alpha release notes](../../releases/tag/v0.82.0-alpha) for the complete change list, validation results and downloads. This release includes source changes from [`8901284`](https://github.com/StarsFord/StarsRemote/commit/8901284ad8f6bd7cb7755242907506b40aeaf254) and [`7a754ea`](https://github.com/StarsFord/StarsRemote/commit/7a754ea83922dabf31de0bd1751242e1dce2c8cc).

## Installation

1. Download the APK matching your device's architecture from the [latest release](../../releases/latest).
2. Enable "Install unknown apps" for your browser/file manager if prompted (this is a normal Android requirement for anything installed outside the Play Store).
3. Install and open.

| File | Use if... |
|---|---|
| `rosetta-gaming-<version>-arm64-v8a.apk` | **Most devices from ~2017 onward.** Full feature set, including Ren'Py and the experimental PC/Windows runner. If you're not sure which one you need, start here. |
| `rosetta-gaming-<version>-armeabi-v7a.apk` | Older 32-bit-ARM-only devices. RPGMaker/TyranoScript games and all browsing/download/library features work; **Ren'Py games and the PC/Windows runner are not available on this build** (their native runtimes are 64-bit only). |

Not sure which your phone is? If the `arm64-v8a` build installs, use it — it's the fuller build.

## Status

This is an **alpha** (`0.82.0-alpha`). Expect bugs, rough edges, and experimental engine compatibility paths. Debug-signed builds for now; a proper release-signed pipeline comes later.

## Planned implementations

- Planned release of an immersive desktop launcher with integrated remote gaming, bringing Rosetta's library-first experience to Windows through the StarsRemote host and client stack.

## Reporting a problem

Please use this repository's **[Issues](../../issues)** tab. When reporting a bug, it helps a lot to include:
- Which APK you installed (`arm64-v8a` or `armeabi-v7a`) and your device model.
- What you were doing when it happened (which source, which game, which step of a download).
- Whether it's reproducible.

Feature requests and source-site suggestions are welcome there too.

## License / third-party notices

Rosetta Gaming aggregates content from third-party community sites and file hosts; it does not claim ownership of any game, image, or file it helps you access. See the main project for third-party component licenses (adrenotools, Ren'Py, zip4j, junrar, and others).
