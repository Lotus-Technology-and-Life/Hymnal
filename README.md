# Hymnal downloads

Hymnal is a lyrical hymnal for Windows by Lotus: every song you love, with its
words, following the music as it plays.

This repository publishes signed Hymnal Windows releases. The application
source, signing keys, private symbols and build system are not stored here;
GitHub's generated source archives contain only this small distribution shell.

## Install

Download `Hymnal-Windows-vX.Y.Z-Setup.exe` from the latest release and run it.
It installs for your user only (no administrator prompt) under
`%LOCALAPPDATA%\Programs\Lotus\Hymnal`.

Windows SmartScreen may say the publisher is unknown: Hymnal is not signed with
a paid Windows publisher certificate. Choose **More info → Run anyway** if you
trust this release, and verify it first if you like (below).

## Verify

Each release carries `SHA256SUMS.txt` and its detached Ed25519 signature
`SHA256SUMS.txt.sig`, made with the Lotus Hymnal release key whose public half
is `hymnal-release-ed25519-public.pem` in this repository.

```
openssl pkeyutl -verify -pubin -inkey hymnal-release-ed25519-public.pem -rawin -in SHA256SUMS.txt -sigfile SHA256SUMS.txt.sig
certutil -hashfile Hymnal-Windows-vX.Y.Z-Setup.exe SHA256
```

The hash must match the line in `SHA256SUMS.txt`. See
`LOTUS_RELEASE_IDENTITY.md` for the permanent fingerprint of the key.

## License

Hymnal is free to use, including at work. Selling, redistributing, modifying,
repackaging, or monetizing Hymnal itself is not permitted. See `LICENSE`.
