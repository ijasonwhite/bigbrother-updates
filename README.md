# bigbrother-updates

Public update feed for **Big Brother**, the Android phone client for the
server monitor dashboard.

This repo holds only the Sparkle-format `appcast.xml` and the release APKs it
points at, so installed copies can find and verify updates. The newest build
is always at
[releases/latest/download/BigBrother.apk](https://github.com/ijasonwhite/bigbrother-updates/releases/latest/download/BigBrother.apk).

**No application source, and no key of any kind, is ever published here.** The
source lives in a separate private repository. Releases are published by
`scripts/release.sh` in the app source tree, which builds, checks the APK for
anything that shouldn't be public, signs and uploads in one step.

Every APK is signed twice: with the app's Android release key, which Android
requires to match before it will upgrade an installed copy, and with an EdDSA
key whose public half is compiled into the app, which the app checks before it
installs anything. Being public makes the feed readable, not writable: it
cannot be used to push a build we did not sign.
