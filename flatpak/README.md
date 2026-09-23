# VaultSeal Flatpak Package

This directory contains the Flatpak metadata for VaultSeal. It packages only the
compiled desktop JAR published by this repository and a public Temurin Java 17
runtime. VaultSeal source code is not included.

## Local Build

Install Flatpak Builder and the Freedesktop SDK, then run:

```bash
flatpak-builder --force-clean --user --install build-flatpak app.kronware.VaultSeal.yml
flatpak run app.kronware.VaultSeal
```

The application uses Flatpak-managed data storage and retains it after a normal
`flatpak uninstall`. Do not add `--delete-data` when uninstalling if you need to
keep local VaultSeal data. Home-folder access is granted for direct import and
export workflows, and network access is granted for LAN sync.

## Flathub Submission

For each release, copy this directory into a Flathub submission branch and
replace the VaultSeal JAR URL with a Git commit-pinned URL from this repository.
Keep the matching SHA-256 value. The manifest, metadata, and binary download are
public; VaultSeal source code remains private.