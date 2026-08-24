<!-- fork banner — keep at top; upstream content follows unchanged -->
# MPD Android APK fork (armeabi-v7a)

This is a fork of [Music Player Daemon](https://github.com/MusicPlayerDaemon/MPD)
whose sole purpose is to **build MPD as an Android APK for `armeabi-v7a`**
(32-bit ARM, e.g. the Samsung Galaxy S5). Upstream's Android build only produces
`arm64-v8a` and `x86_64`; the single patch this fork carries
([`.github/patches/android-armeabi-v7a.patch`](.github/patches/android-armeabi-v7a.patch))
adds the `armeabi-v7a` product flavor. `arm64-v8a` is built too.

CI keeps this fork in sync with upstream and publishes APKs to Releases:

- **Rolling build** ([`build-apk.yml`](.github/workflows/build-apk.yml)) — merges
  upstream `master` weekly and refreshes the rolling
  [`mpd-android-latest`](../../releases/tag/mpd-android-latest) release.
- **Versioned builds** ([`release-apk.yml`](.github/workflows/release-apk.yml)) —
  when upstream tags a new stable version (`vN.N[.N]`), builds that tag and
  publishes a matching versioned release here.

Both produce two APKs per build: `armeabi-v7a` (32-bit) and `arm64-v8a` (64-bit).
They share a stable debug signing key so new builds upgrade in place without an
uninstall (which would wipe `mpd.conf` / state).

---

# Music Player Daemon

http://www.musicpd.org

A daemon for playing music of various formats.  Music is played through the 
server's audio device.  The daemon stores info about all available music, 
and this info can be easily searched and retrieved.  Player control, info
retrieval, and playlist management can all be managed remotely.

For basic installation instructions
[read the manual](https://www.musicpd.org/doc/user/install.html).

# Users

- [Manual](https://mpd.readthedocs.io/en/stable/user.html), or see `/usr/share/doc/mpd/html` in your installation
- [Forum](https://github.com/MusicPlayerDaemon/MPD/discussions)
- [IRC](ircs://irc.libera.chat:6697/#mpd)
- [Bug tracker](https://github.com/MusicPlayerDaemon/MPD/issues/)

# Developers

- [Protocol specification](https://mpd.readthedocs.io/en/latest/protocol.html)
- [Developer manual](https://mpd.readthedocs.io/en/latest/developer.html)

# Legal

MPD is released under the
[GNU General Public License version 2](https://www.gnu.org/licenses/gpl-2.0.txt),
which is distributed in the COPYING file.
