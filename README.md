# Last Wave for iOS

A native iPhone music player for your YouTube Music library, built in the style of Apple Music. Your playlists, likes and history come from your YouTube Music account; Last Wave adds DJ‑style Automix, synced lyrics, lyric search, offline downloads, Last.fm scrobbling and playlist import from Spotify and Apple Music.

Last Wave is the iOS continuation of the open‑source [LastWave‑Native](https://github.com/Clash-Projects/LastWave-Native) project. It is independent and non‑commercial, and is not affiliated with Google, YouTube, Spotify, Apple or Last.fm.

## Download

Grab `LastWave.ipa` from the [latest release](../../releases/latest) and install it with [Sideloadly](https://sideloadly.io), [AltStore](https://altstore.io), [SideStore](https://sidestore.io) or [LiveContainer](https://github.com/LiveContainer/LiveContainer). The IPA is unsigned; your sideloader signs it for your device.

Requires an iPhone on iOS 18 or later. iOS 26 and 27 unlock the Liquid Glass interfaces.

### Add the source (automatic updates)

AltStore, SideStore and LiveContainer can follow Last Wave as a source, so new versions show up in their Updates tab. Add this URL under Sources › + :

```
https://raw.githubusercontent.com/DavidAdelG/LastWave-iOS/main/apps.json
```

The source is updated by the release pipeline the moment a new IPA is published.

## Features

**Playback**
- Streams from YouTube Music in Normal (128 kbps AAC) or High (160 kbps Opus) quality, with separate settings for Wi‑Fi and cellular and a per‑song fallback when a tier doesn't exist.
- Resumes exactly where you left off: last song, position and queue survive a restart.
- Autoplay keeps the music going with radio that follows what you were playing, and fetches ahead so the queue never runs dry.
- Lock screen and Control Center controls, AirPlay, and pauses for calls and other players the way Music does. Games and apps that mix their sound never stop it.
- Hour‑long recordings that YouTube won't stream are fetched and played from disk instead of being skipped.
- Cache Ahead: once a song plays, the songs after it in the queue are fetched up to a budget you choose (250 MB to 4 GB), so a tunnel or the subway doesn't stop the music. When the connection drops the player moves on to the songs already on the phone and resumes fetching when it's back.
- Offline mode: anything that needs the internet is dimmed and disabled; downloads, cached songs, local playlists and settings keep working.

**Automix**
- Analyzes rhythm, key, energy and loudness of each song and mixes like a DJ: long blend with bass swap, filter sweep, echo out, cut on the beat or reverb tail. Pick a style or leave it automatic.
- Tempo matching nudges the incoming song up to 6 % so beats line up, then eases back to its own speed inside the blend.
- Blend length from 1 to 8 seconds, trimming presets, and loudness normalization to −14 LUFS.

**Lyrics**
- Synced lyrics from LRCLIB with Apple‑style word‑by‑word animation, adjustable text size and sync offset.
- Search by lyrics: type a line you remember, in any language. Add "by Artist" to narrow it down.

**Library and playlists**
- Your YouTube Music playlists, Liked Music and history, plus local playlists when signed out.
- Grid or rows, pins, drag to reorder, and the playlist you used last moves to the top.
- Edit a playlist's name, description, visibility and cover after creating it.
- Import public Spotify and Apple Music playlists. Every song is accounted for: found, duplicate, not found, or explicit.
- "Don't Recommend" keeps songs out of suggestions, with a list in Settings to review and undo.

**Downloads**
- Download songs, albums or whole playlists with lyrics and artwork for offline listening; covers are saved with the download and shown offline. A queue shows progress and lets you retry or cancel.

**Discovery**
- Home and Discover follow what you actually play: the same languages, and Christian music stays Christian when that's what you listen to.
- Mixes: My Mix, For You, Song Radio, Similar Artists, By Genre, Mood Radio, Never Heard, Top and Recent. Genre DNA breakdown of your taste.

**Last.fm**
- Scrobbling with a configurable threshold, "love" on like, listening stats and top tracks, with your own API key.

**Looks**
- Three interfaces: Classic (iOS 18), Liquid Glass (iOS 26) and Liquid Glass+ (iOS 27 and later).
- Animated artwork background whose motion follows the song's BPM, with an intensity control.

## Setup

**YouTube Music**: Settings › YouTube Music › Sign in. Choose the default visibility for playlists Last Wave creates and whether plays are added to your YouTube Music history. Your session stays on the phone.

**Last.fm**: every app must bring its own API key. Create one at [last.fm/api/account/create](https://www.last.fm/api/account/create) (any application name, leave the callback empty), paste the key and shared secret into Settings › Last.fm, then tap Sign in with Last.fm.

## Tips

- Long‑press a song for Play Next, Add to a Playlist, Download, Start Mix, Don't Recommend and more. Inside a playlist the menu also offers Remove from Playlist.
- Explicit songs are marked **E**. With "Hide explicit songs" on they stay in your playlists but never play.
- Settings › Help › Activity Log records what the app does behind the scenes. It is off by default. Turn it on, reproduce a problem, and attach the log when opening an issue.

## Privacy

Last Wave talks to YouTube Music, LRCLIB, Genius (lyric search), Deezer and iTunes (artwork and artist genres), and Last.fm when you connect it. Nothing is sent to the author. Your YouTube session, API keys, library and downloads live on your phone.

## Known limitations

- YouTube Music playlist covers can't be uploaded; a cover you choose in Last Wave is shown only in the app.
- Passkey sign‑in is not possible inside the login web view; use a password with the AutoFill key icon.
- iOS does not let third‑party apps claim `music.youtube.com` links. Copy a link and Last Wave offers to open it when you return to the app.
- The app depends on YouTube's internal API and can break when YouTube changes it. Updates land on the Releases page.

## Credits

Based on [LastWave‑Native](https://github.com/Clash-Projects/LastWave-Native). Lyrics by [LRCLIB](https://lrclib.net).
