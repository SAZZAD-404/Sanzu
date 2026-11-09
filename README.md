# Sanzu — Take back your browser

Sanzu is a privacy-focused web browser for Android, based on
[Cromite](https://github.com/uazo/cromite) (a Bromite fork of Chromium),
with built-in ad blocking and an eye for privacy — rebranded and
customised as Sanzu.

## Why Sanzu

- **Built-in ad blocking** — eyeo / Adblock Plus based blocker, plus the
  legacy Bromite subresource blocker as a fallback. Filter lists update
  daily; add your own lists in Settings.
- **Anti-fingerprinting** — battery, fonts, WebGL, WebRTC, canvas, audio,
  client hints, and much more are disabled or mitigated so websites
  cannot recognise your device.
- **De-Googled** — no Google Sync, browser sign-in, metrics, crash
  reports, Translate, or Feed. No usage data leaves the browser.
- **Privacy by default** — Do-Not-Track and Global Privacy Control on,
  encrypted DNS (DoH), partitioned cookies and storage (per-site boxes),
  referrer and window-name cleared on cross-site navigation.
- **Fast** — PGO-optimised release builds and the Android Dynamic
  Performance Framework.
- **Extras** — per-site settings (adblock, JavaScript, images, JIT,
  WebGL, WebRTC), always-incognito mode, bottom toolbar, extensions on
  Android, bookmark import/export, exit button, proxy settings page
  (`chrome://proxy`), user-agent customisation.

## Build

Sanzu builds in GitHub Actions (GitHub-hosted runner, Android arm64):

1. Open the **Actions** tab → **Build Sanzu** → **Run workflow**.
2. Choose branch `master`, debug `false` for a release-style build.
3. The APK appears under the run's **Artifacts** as
   `sanzu-android-arm64`.

The workflow (`.github/workflows/build_sanzu.yaml`) fetches Chromium at
`build/RELEASE`, applies all patches in `build/cromite_patches_list.txt`,
and builds `chrome_public_apk`. A full Chromium build needs ~30 GB of
source and several hours. Every CI build uses a fresh throwaway signing
key, so uninstall an older Sanzu build before installing a new one (or
set up one stable keystore for signed releases).

## License

Sanzu is published under **GNU GPL v3**; Cromite-specific patches are
under GPL-2+. See [LICENSE](./LICENSE). Each patch carries its own
licence header.

## Credits

- [Chromium](https://www.chromium.org/Home) and its developers
- [Bromite](https://github.com/bromite/bromite)
- [Cromite](https://github.com/uazo/cromite) by uazo — Sanzu is a fork
  of Cromite, rebranded with its own icon, name, and package
  (`com.sanzu.browser`)
