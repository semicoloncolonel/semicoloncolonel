# semicoloncolonel

I maintain two sources of Morphe patches that remove ads and block tracking in streaming, news, shopping, and other apps. Each source is its own repository, with its own releases and issues.

| Source | Devices | Latest release | Install |
|--------|---------|----------------|---------|
| [Mobile Morphe Patches](https://github.com/semicoloncolonel/mobile-morphe-patches) | Phones | [![Latest release](https://img.shields.io/github/v/release/semicoloncolonel/mobile-morphe-patches?label=release&color=4f46e5)](https://github.com/semicoloncolonel/mobile-morphe-patches/releases/latest) | [Add to Morphe Manager](https://morphe.software/add-source?github=semicoloncolonel/mobile-morphe-patches) |
| [TV Morphe Patches](https://github.com/semicoloncolonel/tv-morphe-patches) | Android TV | [![Latest release](https://img.shields.io/github/v/release/semicoloncolonel/tv-morphe-patches?label=release&color=14b8a6)](https://github.com/semicoloncolonel/tv-morphe-patches/releases/latest) | [Add to Morphe Manager](https://morphe.software/add-source?github=semicoloncolonel/tv-morphe-patches) |

Open the install link on the device that has Morphe Manager. To patch phone and Android TV apps in one copy of Morphe Manager, add both sources.

## Before you patch

Patch only the apps you need. A patched app is re-signed, so it no longer updates from Google Play, and some apps refuse to play or sign in on a re-signed copy. I do not patch banking, payment, email, or cloud storage apps, and I do not recommend patching them.

## Verify a source

Morphe Manager shows the signer of each source on its "Signed by" line. Both sources are signed with the same key:

<p align="center">
  <a href="https://github.com/semicoloncolonel/mobile-morphe-patches/blob/dev/docs/signing-key.md"><img alt="Signed by fingerprint" src="https://raw.githubusercontent.com/semicoloncolonel/mobile-morphe-patches/dev/docs/assets/signed-by.svg"></a>
</p>

If Morphe Manager shows a different signer, check the signing key history of the [phone source](https://github.com/semicoloncolonel/mobile-morphe-patches/blob/dev/docs/signing-key.md) or the [Android TV source](https://github.com/semicoloncolonel/tv-morphe-patches/blob/dev/docs/signing-key.md) before you apply the patches.

GitHub Actions also attaches a signed attestation to every release file, which names the commit the file was built from. To check a downloaded `.mpp` file, install the [GitHub CLI](https://cli.github.com) and run the command for its source.

Phone patches:

```bash
gh attestation verify patches-VERSION.mpp -R semicoloncolonel/mobile-morphe-patches
```

Android TV patches:

```bash
gh attestation verify patches-VERSION.mpp -R semicoloncolonel/tv-morphe-patches
```

## Report a problem

Open an issue in the repository for the device the app runs on, and use one of its issue forms. For a security problem, follow the security policy of the [phone source](https://github.com/semicoloncolonel/mobile-morphe-patches/security/policy) or the [Android TV source](https://github.com/semicoloncolonel/tv-morphe-patches/security/policy) instead of opening a public issue.
