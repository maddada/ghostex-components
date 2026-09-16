# Ghostex components

Runtime components that the [Ghostex](https://github.com/maddada/Ghostex) desktop app downloads on first launch: the Chromium Embedded Framework (`cef-<version>` releases) and the Code-tab editor payloads (`code-server-<identity>` releases). Each release is one immutable component version with one `.tar.gz` per platform, plus a `.sha256` sidecar for the editor archives.

Nothing here is meant to be downloaded by hand. Every Ghostex build embeds a sealed manifest naming the exact tag, asset name, size, and SHA-256 it fetches from this repository, and the app verifies each download against that manifest before installing it. Releases are never modified once published; a changed component gets a new tag.

Get Ghostex itself from the [Ghostex releases page](https://github.com/maddada/Ghostex/releases).
