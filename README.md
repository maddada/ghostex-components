# Ghostex components

Runtime components that the [Ghostex](https://github.com/maddada/Ghostex) desktop app downloads on first launch: the Chromium Embedded Framework (`cef-<version>` releases) and the Code-tab editor payloads (`code-server-<identity>` releases). Each release is one immutable component version with one `.tar.gz` per platform, plus a `.sha256` sidecar for the editor archives.

Nothing here is meant to be downloaded by hand. Every Ghostex build embeds a sealed manifest naming the exact tag, asset name, size, and SHA-256 it fetches from this repository, and the app verifies each download against that manifest before installing it. Releases are never modified once published; a changed component gets a new tag.

Get Ghostex itself from the [Ghostex releases page](https://github.com/maddada/Ghostex/releases).

## Theme art

`theme-art/` holds the artwork Ghostex's themes paint behind the window (Settings > Themes: Art backgrounds and the Backgrounds gallery). Each file is `<id>-<first 8 of its SHA-256>.webp`, 2560x1440, and `theme-art/manifest.json` lists every artwork's id, name, file, size and SHA-256. Ghostex downloads an artwork from the `theme-art` release the first time it shows, keeps it only when its size and SHA-256 match the ones built into the app (`ARTWORKS` in `packages/settings-catalog/src/data/themes.rs` in the Ghostex repository), and caches it on disk.

The `theme-art` release is published from this folder by `tooling/theme-art/publish.sh` in the Ghostex repository. A changed artwork is a new file name, so the assets apps already know never change; new ones are added to the same release.
