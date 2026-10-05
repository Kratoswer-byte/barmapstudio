# BAR Map Studio

**Map and unit editor for [Beyond All Reason](https://www.beyondallreason.info).**
Generate a terrain, paint it, place metal and start points, build custom units, and play the result a minute later.

> Beta 0.1 — unofficial tool, not affiliated with the Beyond All Reason team.

![Map editor](docs/img/maps.png)

## Download

Get the latest version from the **[Releases](../../releases/latest)** page.

| File | For |
|---|---|
| `BARMapStudioSetup-…exe` | Windows installer (recommended) |
| `BARMapStudio-…-win.zip` | Windows, no installation: unzip and start `bar-map-launcher.bat` |
| `BARMapStudio-…-unix.tar.gz` | Linux and macOS — **not tested**, needs Java 25 |

Windows may warn about an unknown publisher the first time: choose **More info → Run anyway**.

## What you need

- Windows 10 or 11 (64 bit).
- Beyond All Reason installed and started at least once, so it has downloaded the game.

BAR Map Studio finds your BAR installation by itself. If it does not, press the **BAR** button at the bottom and pick its `data` folder.

## What it does

- **Maps** — procedural generator with 29 terrain styles and the BAR biomes, live terrain shaping, symmetry tools, metal spots, geo vents, start points, rocks, trees and wrecks, slope map and 3D view. One click exports the map into BAR and starts a match against the AI.
- **Textures** — materials for the four terrain zones, automatic rules by height and slope, detail and relief.
- **Objects & Units** — browse every BAR unit in 3D, duplicate one as your own custom unit, change its name, stats, size, side and colour, and script it in Lua. Import your own `.obj` models.
- **Map Library** — all the maps installed in BAR with preview, size, heights, wind, tidal, metal and start positions. Open any of them in the editor or play it against the AI.
- **Play with friends** — your friends only need BAR. The Studio uploads the map to your own cloud storage and writes a small file for each friend: a double click downloads the map and joins your match.
- English, Italian, French and German.

![Map library](docs/img/library.png)

![Objects and units](docs/img/objects.png)

## Guide

- [User guide (English)](docs/GUIDE.md)
- [Guida per l'utente (italiano)](docs/GUIDA.md)

## Updates

When a newer version is published here, a green **UPDATE** button appears at the bottom right of the Studio. It shows what is new and can download and start the installer for you.

## Feedback

This is a beta: bug reports and ideas are welcome. Use the orange **FEEDBACK** button at the bottom right of the Studio. Nothing is sent until you press Send, and you see exactly what is attached.

## Licence

BAR Map Studio is © 2026 Kr4Tosw3R, free to use for personal and non-commercial purposes. It is built on the [Neroxis Map Generator](https://github.com/FAForever/Neroxis-Map-Generator) (MIT License, © 2020 Peter Ziegler). The full text and the list of the libraries used are in `LICENSE.txt`, shipped with the program.

Beyond All Reason and its game content belong to their respective authors. BAR Map Studio reads the game files from your own installation and does not include them.
