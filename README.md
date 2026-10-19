# homebrew-orynivo

Homebrew tap for [Orynivo](https://orynivo.app/) — a free, open-source Hi-Fi
music library, player and self-hosted server for Windows, Linux and macOS
(Apache-2.0).

```sh
brew tap bschlaack/orynivo
brew install --cask orynivo
```

## Status: preview

- The cask checksums were verified on 2026-10-19 against Orynivo's signed
  update manifest (ECDSA P-256, `update-manifest.json` + `update-manifest.sig`
  on each GitHub release) and against the actual downloaded release artifacts.
- `brew style` / `brew audit --cask --online` and install/uninstall tests on
  real Apple Silicon and Intel hardware have **not** been run yet.
- Orynivo is not signed with an Apple Developer ID and not notarized. macOS
  Gatekeeper will require explicit approval in Privacy & Security on first
  launch; the cask does not bypass Gatekeeper or strip quarantine.

## Release update procedure

1. Verify the new release's `update-manifest.sig` against the release public
   key, then take the portable-zip SHA-256 values from the manifest.
2. Update `version` and both `sha256` values in `Casks/orynivo.rb`.
3. Re-run `brew style` and `brew audit --cask --online`, plus an install
   smoke test on each architecture.

Source: <https://github.com/bschlaack/Orynivo>
