# Auction Analyst — releases

Built installers for the Auction Analyst desktop client, and the update
manifest its auto-updater reads. **Binaries only** — the source lives in a
private repository.

This repository is public for one specific reason: Tauri's updater fetches
`latest.json` and the installer over plain HTTPS with no credentials, and
private release assets cannot be downloaded that way.

## Installing

Take the `.exe` from the [latest release](../../releases/latest). It is not
code-signed, so Windows SmartScreen will warn on first run — *More info* →
*Run anyway*. After that the app updates itself and you should not need this
page again.

## For the updater

`latest.json` on the newest release points at that release's installer and
carries its signature. Every build is signed, and the client verifies it
against a public key compiled into the application: an installer that has been
tampered with, or built with a different key, is refused rather than run.

Published by CI from the private source repository. Nothing here is edited by
hand.
