# BAR Map Studio — User guide

Beta 0.1 · [Italiano](GUIDA.md)

## Contents

1. [Install and first start](#1-install-and-first-start)
2. [Your first map in five minutes](#2-your-first-map-in-five-minutes)
3. [The MAPS tab](#3-the-maps-tab)
4. [The TEXTURES tab](#4-the-textures-tab)
5. [The OBJECTS & UNITS tab](#5-the-objects--units-tab)
6. [The MAP LIBRARY tab](#6-the-map-library-tab)
7. [Playing with friends](#7-playing-with-friends)
8. [Updates and feedback](#8-updates-and-feedback)
9. [Where your files are](#9-where-your-files-are)
10. [Problems and solutions](#10-problems-and-solutions)

---

## 1. Install and first start

1. Install **Beyond All Reason** and start it once, so it downloads the game and its engine.
2. Run `BARMapStudioSetup-…exe`. Windows asks for administrator permission and proposes `C:\Program Files\BARMapStudio`.
3. Start BAR Map Studio from the Start menu or the desktop shortcut.

The Studio looks for your BAR installation by itself. The round light next to **BAR** at the bottom right is green when it was found. If it is not, press **BAR** and pick the `data` folder of your installation (usually `…\Beyond-All-Reason\data`).

The language is chosen from the gear button at the bottom right: English, Italian, French, German. The change applies at the next start.

## 2. Your first map in five minutes

1. Open the **MAPS** tab. Size, terrain style, biome and seed are already filled in — style, biome and seed are picked at random at every start.
2. Press **GENERATE TERRAIN**. Do not like it? Press **Roll Seed** and generate again.
3. On the right press **+ Auto Base Mexes (Spawn)** and **+ Auto Contested Mexes (Center)** to place the metal.
4. Give the map a name in **Custom Map Name**.
5. Press **GENERATE AND PLAY VS AI**. The map is written into BAR and the match starts when you press Confirm.

## 3. The MAPS tab

![Map editor](img/maps.png)

### Left: the generator

| Control | What it does |
|---|---|
| **Map Size** | Size in BAR units (8x8, 12x12, 16x16…), square or rectangular. |
| **Terrain Style** | The shape of the land: valleys, mesas, islands, canyons, lanes, craters and more. |
| **Biome / Texture** | The look of the ground. The entries starting with `BAR:` use the biomes of the official maps. |
| **Symmetry** | How the map is mirrored so that every team gets the same ground. |
| **Players per team** | How many start points each team gets. |
| **Terrain Seed** | The number the terrain is built from: same seed and settings, same map. |

The **Relief** sub-tab reshapes the generated terrain live with sliders: relief profile (wider plains or plateaus), smoothing and terraces. Back to 0 restores the original.

### Top: the tools

`Sel` select and move · `Mex` metal spot (pick its value next to it) · `Geo` geo vent · `Spawn` start point · `Rocks`, `Trees`, `Wrecks` reclaim · `Eraser`.
**Symm** repeats every action on the mirrored side; **Axis** changes the mirror. **Undo / Redo** as usual.
The letter in square brackets is the keyboard shortcut.

Under the map: **Slope Map [L]** colours the ground by steepness (green: vehicles, yellow: slow vehicles, orange: bots only, red: impassable) and **3D View [V]** shows the map in three dimensions.

### Right: details and export

- **Map Details** — counters, metal value of the spots, quick placement buttons, reclaim density.
- **Spawn roles…** — the role suggested to each start point (front, air, tech…). All start as *front*.
- **Map options…** — wind, tidal strength, gravity, water and lava, extractor radius, fog of war, and how a match starts: **static** positions (each team exactly on its base) or **start zone** (players pick their spot inside the zone of their team).
- **GENERATE FINAL MAP** — writes the map into the BAR maps folder.
- **GENERATE AND PLAY VS AI** — the same, then starts a match.
- **HOST MATCH WITH FRIENDS** — see [chapter 7](#7-playing-with-friends).

Exporting again with the same name replaces the previous map.

## 4. The TEXTURES tab

The ground of a BAR map is painted with four materials, one per **zone**. Here you choose which material goes in each zone and where each zone lies.

- **Materials** — pick them from the BAR biomes or load your own image with **+ File**.
- **Automatic rules** — the zones are assigned by height and slope: for example sand on the low flat ground, rock on the cliffs.
- **Detail and relief** — how strong the fine detail of each material looks from close up.
- **Sync Map** — reloads the map currently open in the MAPS tab.

The colours you see are the same used by the MAPS tab and by the exported map.

## 5. The OBJECTS & UNITS tab

![Objects and units](img/objects.png)

### The library

On the left there are all the BAR units plus the objects shipped with the Studio. Filter by **category**, **faction** and **tech level**, or search by name. Clicking a unit loads its 3D model; the blue wireframe commander next to it shows the scale.

BAR units can only be viewed. To change one, select it and press **DUPLICATE AS CUSTOM UNIT**: the copy is yours and appears under the **CUSTOM** filter. **DELETE** removes a copy, never an original.

**+ IMPORT 3D MESH (.obj)** brings in your own model.

### The data of a custom unit

- **Entity data** — name, description, footprint, hit points, metal and energy cost, sight range.
- **In-game scale** — size of the model, with presets for commander, T1, building and prop.
- **Side & colour** — which side owns the unit on the map: a faction, one of the teams, *hostile to everyone* or *neutral*. Units of a faction use the team colour; with hostile and neutral you choose the colour.

### Behaviour and Definition

A custom unit has two Lua texts. The **?** button next to the two tabs explains them inside the program.

| | **BEHAVIOUR** | **DEFINITION** |
|---|---|---|
| What it is | What the unit **does** | What the unit **is** |
| When it is read | During the match, for every copy of the unit | Once, when the match loads |
| Use it for | Animations, moving pieces, effects, actions that repeat, reactions to damage | Health, cost, speed, sight, weapons, shields, movement |
| Example | Every 5 seconds the unit damages everything around it | Give the unit the plasma shield of another unit |

A copy starts with the script of the original BAR unit, ready to be changed.

In **Definition** you use short Studio commands — `Studio.set`, `Studio.addWeapon`, `Studio.addShield`, `Studio.moveLike`. The **Components…** button lists the BAR units with their weapons, shields and values and writes the lines for you.

**VALIDATE LUA CODE** checks the syntax. **SEND TO MAP** places the unit on the map open in the MAPS tab.

Rule of thumb: a number or a piece of equipment goes in Definition; something that happens while playing goes in Behaviour.

## 6. The MAP LIBRARY tab

![Map library](img/library.png)

All the maps installed in BAR. The ones made with the Studio carry the green **MINE** label.

- **Left** — search, show all / mine / BAR maps, sort by date, name or size.
- **Right** — preview with metal spots and geo vents, and the specifications: size, heights, start positions, metal, extractor radius, wind, tidal, gravity, hardness, water, author.
- **PLAY VS AI** — starts a match on the selected map.
- **OPEN IN THE EDITOR** (or double click) — loads terrain, texture, start points, metal and geo vents into the MAPS tab.
- **Delete** — only for your own maps. BAR maps can only be viewed.

## 7. Playing with friends

Your friends only need Beyond All Reason: they do not need the Studio.

### Once: your cloud storage

The map has to be somewhere your friends can download it from. The Studio uploads it to an S3-compatible storage of your own (Cloudflare R2, Backblaze B2, Amazon S3).

1. Create a **bucket** and an **access key** on the site of the provider, and make the bucket publicly readable.
2. In the Studio: **HOST MATCH WITH FRIENDS → Cloud storage…**, fill in endpoint, bucket, the two keys and the public address of the bucket.
3. Press **Test connection**.

The keys stay in the user settings of your PC. They are never written into the maps or into the files you send to your friends.

### Every match

1. Open or generate the map and press **HOST MATCH WITH FRIENDS**.
2. Type your player name, your friends' names (one per line), an optional password and the address they connect to (**Detect** finds your public address).
3. Press **HOST MATCH**. The Studio exports the map, uploads it, opens a folder with one `join_NAME.bat` per friend and starts BAR as host.
4. Send each friend their file. A double click downloads the map, checks it, installs it and joins your match.

The order of the names decides the teams: players are dealt to the teams in turn. Free places are taken by the AI.

### What must be true

- Your PC must be reachable on **UDP port 8452**: forward that port on your router, or use a private network such as Tailscale or ZeroTier and give the address of that network.
- Everybody needs the **same BAR version** as you. Opening BAR once updates it.
- Windows warns when a downloaded `.bat` is opened: **More info → Run anyway**.

The `.sh` files for Linux and macOS are written too, but they have not been tested.

## 8. Updates and feedback

- **UPDATE** (green, bottom right) appears when a newer version is published. It shows what is new and can download and start the installer. The Studio closes: save your work first.
- **FEEDBACK** (orange, bottom right) sends a bug report or an idea to the author. You see the technical details that are attached (version, system, last errors) and can untick them. Nothing is sent until you press Send.

## 9. Where your files are

| What | Where |
|---|---|
| The program | The folder you installed into, by default `C:\Program Files\BARMapStudio` |
| Settings, cache, logs, your textures, feedback copies | `%APPDATA%\BARMapStudio` (the program folder itself for the portable zip) |
| Exported maps | The `maps` folder of BAR |
| Files for your friends | `matches` inside your data folder |

Uninstalling removes the program and keeps your settings.

## 10. Problems and solutions

| Problem | What to do |
|---|---|
| The BAR light is red | Press **BAR** and pick the `data` folder of your installation. Start BAR once if you never did. |
| The unit list is empty | BAR has not downloaded the game yet: start it once. |
| "Play" does nothing | BAR has no engine yet: start it once and let it finish updating. |
| Windows asks for permission when exporting | The BAR maps folder is protected. Allow it: only the copy of the map uses that permission. |
| A unit of Legion, Scavengers or Raptors is missing in game | Those units need their game option. The Studio turns it on in the matches it starts. |
| A friend cannot join | Check the UDP port 8452 and that you both have the same BAR version. |
| The installer says it cannot create a folder | Start it from a normal folder such as Downloads or the Desktop. |

Something else? Press **FEEDBACK** and describe what you did, what you expected and what happened.
