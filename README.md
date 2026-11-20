# UniversalRichPresence

A Vencord userplugin for Windows 10/11 that shows the media reported by Windows media controls as Discord Rich Presence.

## Features

- Windows media controls as the only playback source.
- Automatic Watching activity and 🎬 for video, or Listening activity and 🎵 for audio.
- Listening is the fallback when the player does not report a media type.
- Playback title, artist, timeline and pause handling, depending on what the player reports.
- Optional Wikipedia movie artwork lookup by title and year, with cached successful matches.
- Configurable activity text, timestamps, filters and optional custom status.

This plugin uses the session Windows considers current. A movie title must be supplied by the player. It does not identify movies from video frames or audio.

## Installation

1. Use a Vencord source checkout with its dependencies installed.
2. Copy this repository's contents into a single folder named src/userplugins/UniversalRichPresence.
3. Run pnpm build --dev --disable-updater and install that custom build using Vencord's documented installation procedure.
4. Restart Discord and enable UniversalRichPresence in Settings → Vencord → Plugins.
5. Enable Update Activity in the plugin settings. Enable Discord activity sharing if other people should see it.

[Official custom plugin instructions](https://docs.vencord.dev/installing/custom-plugins/)

## Artwork

Enable “Find missing movie artwork on Wikipedia by title and year” to search for movie posters. The plugin sends the title and available year to English Wikipedia. It requires a unique matching article with an image and caches successful results locally. A Wikipedia button links to the source article.

The Windows reader currently does not extract the player's own thumbnail. Wikipedia artwork is a fallback for video activities. Titles absent from English Wikipedia or differently named there may have no artwork.

## Privacy

Playback metadata is read locally through Windows SMTC and published to Discord when the corresponding output is enabled. Custom status publishing is separate from activity publishing. Wikipedia receives movie title searches when artwork lookup is enabled. Custom image URLs are resolved through Discord.

## Attribution and license

UniversalRichPresence is a modified fork of **SpotifyStatus by 3xyy**, from [3xy-userplugins-vencord](https://github.com/3xyy/3xy-userplugins-vencord/tree/main/spotifyStatus), based on upstream commit 51ee47d12f1901e77fb149b50a00127ce83870ad.

Changes include Windows-only playback sourcing, automatic activity type and emoji, Wikipedia movie artwork lookup, and the UniversalRichPresence name. Original author and copyright notices are retained.

Licensed under **GPL-3.0-or-later**. See [LICENSE](LICENSE).
