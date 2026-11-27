# HopTool SRW A P (Super Robot Wars A Portable BGM replacer)

[日本語](README.md) | English

An Android app that replaces the BGM of Super Robot Wars A Portable with your own audio.
It rewrites the ISO / CSO you play in PPSSPP and similar emulators, right on your phone.

- Download: [SRWAP_BGMtool.apk](SRWAP_BGMtool.apk)
- **MX Portable version**: [SRWMXP_BGMtool.apk](SRWMXP_BGMtool.apk) (HopTool SRW MX P. Works the same way as the A version → [About the MX Portable version](#about-the-mx-portable-version))
- **α3 (PS2) version**: [SRWA3_BGMtool.apk](SRWA3_BGMtool.apk) (HopTool SRW α3 → [About the α3 version](#about-the-α3-version))
- **Windows version**: [HopTool_Windows.zip](HopTool_Windows.zip) (A P, MX P and α3 in one app → [About the Windows version](#about-the-windows-version))
- Requirements: Android 7.0 or later (arm64-v8a / armeabi-v7a / x86_64)
- The apps are shown in English when your device / PC language is not Japanese. Song titles stay as they are in the game (Japanese).

> **No game data is included.** Use it only for personal enjoyment, with an ISO / CSO you dumped from a game you own.

## Features

- **BGM replacement**: loads songs from mp3 / flac / wav / m4a or videos such as mp4 (audio only), converts them to the game's format (ATRAC3) and writes them
- **Editor** (InShot-style): line up and layer several sources, split, trim, per-clip volume and fades, undo
- **Loop points**: set with the L / R flags above the waveform. "Smooth the seam" makes the jump back to the loop start seamless
- **Listen to the original**: preview the songs in the ISO / CSO with the same loop as the game. You can also use the original song as a source in the editor
- **Rename songs**: tap a song → "Rename"
- **Match volume**: measures each original song's loudness and matches the replacement to it (you can boost it further)
- **CSO support**: keeps the original CSO and creates a new one
- **BPS patches**: creates a BPS patch for the ISO from the original and the modified file (ISO or CSO)
- The boot logo is replaced with the "hopmod" logo when writing

## Installation

1. Download [SRWAP_BGMtool.apk](SRWAP_BGMtool.apk) to your phone
2. Open it and install (allow "install unknown apps" if asked)

## How to use

1. **Choose an ISO / CSO**
   - An ISO is overwritten directly. **Always choose a copy**
   - For a CSO, the original is kept and a new CSO is created
2. In the song list, tap the song to replace → "Choose a song to replace it"
3. Adjust the length and loop in the editor, then "Done"
   - Songs longer than the red line don't fit (they are written into the original song's slot, at the original's quality)
4. "Write" → choose the volume settings and run
5. Start the game in PPSSPP and check

### Song numbers

- 01–45: same numbers and songs as the game's sound test
- 26: title screen song (same data as "極めて近く、限りなく遠い世界に")
- 00: backup with the same content as #26 (not used on the title screen)
- 25: unused placeholder

### Preset titles

The app comes with the author's own title changes preset.
If you don't want them, press "Undo all title changes" before writing.

## About the MX Portable version

A separate app for Super Robot Wars MX Portable. It can be installed alongside the A version.

- Download: [SRWMXP_BGMtool.apk](SRWMXP_BGMtool.apk)
- Screens and controls are the same as the A version
- 81: title screen song
- 85: alternate version of "魂のルフラン"

## About the α3 version

A separate app for Super Robot Wars α3 (PS2, SLPS_255.37). It can be installed alongside the A and MX versions.
It rewrites the ISO you play in PS2 emulators such as NetherSX2.

- Download: [SRWA3_BGMtool.apk](SRWA3_BGMtool.apk)
- Only ISO is supported (the ISO is overwritten directly, so **always choose a copy**)
- Choosing songs and the editor work the same as the A version
- Replaced songs are streamed from the disc while playing
- **Edit the written song**: reads a song you already wrote back into the editor
- **Restore the original song / Restore all**: puts replaced songs back. Restoring all gives you the unmodified ISO
- **Listen to the original**: plays it by imitating the console's sound chip (it sounds slightly different from the real game)
- **Quality**: Standard (32kHz) or Fewer dropouts (24kHz, slightly muffled highs). Standard is fine in most cases
- Pressing "Write to ISO" without choosing any song keeps the written songs and only updates the playback system and the boot logo. Do this once after updating the app
- If the ISO grows beyond a single-layer DVD (4.38 GB), emulators may fail to read the songs. Press "Write to ISO" again to pack away old unused song data and make it smaller

## About the Windows version

A Windows app that combines A P, MX P and α3. Open an ISO / CSO and it detects the game automatically.

- Download: [HopTool_Windows.zip](HopTool_Windows.zip)
- Requirements: Windows 10 / 11 (64-bit)
- No installation needed. **Extract the whole zip**, then double-click `HopTool.exe` in the extracted folder (Java is included)
- Screens and features are the same as the Android version. The editor is used with the mouse (drag an empty area: scroll, Ctrl + wheel: zoom, Space: play / stop)
- The boot logo is replaced with the "hopmod" logo every time you write

## Notes

- Don't distribute patches or ISO / CSO files containing replaced songs. Most of their content is the songs themselves, which belong to their songwriters and record labels
- In the A and MX versions the game loads each song into memory, so the length is limited (the red line in the editor)
- Always keep your original ISO / CSO before rewriting
- After writing with the α3 version, start the game fresh instead of loading a save state (a save state made before writing may have no sound)

## Licenses

These apps include the following open-source software. Full license texts, sources and changes are in `assets/licenses/` inside the APK (the `licenses` folder in the Windows version).

- [atracdenc](https://github.com/dcherednik/atracdenc) (ATRAC3 encoding): LGPL-2.1-or-later
- [FFmpeg](https://ffmpeg.org/) (playing the original songs, minimal build for ATRAC3 decoding only; the Windows version also uses it to read audio files): LGPL-2.1-or-later
- Windows version only: [Eclipse Temurin](https://adoptium.net/) (Java runtime): GPL-2.0 with Classpath Exception
