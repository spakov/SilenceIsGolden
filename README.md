# Silence is Golden
Disables seasonal and other common music, allowing ambient sounds to play
immediately.

I love the music in Stardew Valley, but I also love the ambient sounds,
especially when playing for a long time. If you set the Music Volume slider to
zero in the Options menu, you may have noticed that you just get silence while
the music is still playing at zero volume, then you get ambient sounds once
it's done. This mod replaces configured music with a 100-millisecond silent
.wav file, allowing the game to play ambient sounds almost immediately.

[Translations](https://stardewvalleywiki.com/Modding:Translations) are welcome!

## Installation
1. Install the latest version of [SMAPI](https://smapi.io/).
2. Install the latest version of [Content
   Patcher](https://www.nexusmods.com/stardewvalley/mods/1915).
3. Install the latest version of [Generic Mod Config
   Menu](https://www.nexusmods.com/stardewvalley/mods/5098). (Optional, but
   makes configuration easier.)
4. Install the latest version of [Sound
   Tweaker](https://www.nexusmods.com/stardewvalley/mods/14767).
5. Unzip the mod folder into `Stardew Valley/Mods`.
6. Run the game using SMAPI.

## Configuration
You can edit settings from the title screen ([via the cog
button](https://github.com/spacechase0/StardewValleyMods/blob/develop/GenericModConfigMenu/docs/screenshot-title.png))
or in game ([at the bottom of the in-game Options
menu](https://github.com/spacechase0/StardewValleyMods/blob/develop/GenericModConfigMenu/docs/screenshot-in-game-options.png)).

Changes take effect when entering a new area once music has stopped playing.

### Options
All options are true-false, representing whether or not you want music to play.

* Stardew Valley
  * Seasonal music
  * Secret Woods music
  * Town music
* Desert
  * Desert music
* Island
  * Island music
* Mines
  * Mines music (also affects Skull Cavern)
  * Volcano Dungeon music

### Manual configuration
If you're not using Generic Mod Config Menu, create a `config.json` file in the
mod directory and tweak as desired.

Here's the default `config.json`:

```
{
  "SeasonalMusic": "false",
  "SecretWoodsMusic": "true",
  "TownMusic": "true",
  "DesertMusic": "false",
  "IslandMusic": "false",
  "MinesMusic": "false",
  "VolcanoDungeonMusic": "false"
}
```

## Side effects
* When transitioning between screens that music normally plays through, there
  is a brief pause while the silence is briefly played before ambient sounds
  are played again. This is difficult to work around since the conditions that
  determine which [ambient
  sound](https://stardewvalleywiki.com/Modding:Audio#Music_.28ambient.29) is
  triggered are complex.
* Sounds are patched when the day begins and when the player changes locations
  (i.e., moves between screens). Changing the configuration will not
  immediately stop any music that is already playing.
* Pelican Town is eerily silent with no music playing—there are no ambient
  sounds there.

## Mod details
* **Nexus Mods**: [Link](https://www.nexusmods.com/stardewvalley/mods/31677)
* **GitHub**: [Link](https://github.com/spakov/SilenceIsGolden)
* **`UniqueID`**: `spakov.SilenceIsGolden`

Music playback triggering is
[complicated](https://stardewvalleywiki.com/Soundtrack#Triggering_Conditions)
in Stardew Valley, on top of an already-complex
[wavebank](https://stardewvalleywiki.com/Modding:Audio#Music)-based audio
system using audio cues.

Table 1 lists affected music:

**Table 1**: Music affected by this mod

| Cue ID         | Soundtrack Title                        | Mod Option            |
| -------------- | --------------------------------------- | --------------------- |
| `spring1`      | Spring (It's A Big World Outside)       | Seasonal music        |
| `spring2`      | Spring (The Valley Comes Alive)         | Seasonal music        |
| `spring3`      | Spring (The Wild Horseradish Jam)       | Seasonal music        |
| `summer1`      | Summer (Nature's Crescendo)             | Seasonal music        |
| `summer2`      | Summer (The Sun Can Bend An Orange Sky) | Seasonal music        |
| `summer3`      | Summer (Tropicala)                      | Seasonal music        |
| `fall1`        | Fall (The Smell Of Mushroom)            | Seasonal music        |
| `fall2`        | Fall (Ghost Synth)                      | Seasonal music        |
| `fall3`        | Fall (Raven's Descent)                  | Seasonal music        |
| `winter1`      | Winter (Nocturne of Ice)                | Seasonal music        |
| `winter2`      | Winter (The Wind Can Be Still)          | Seasonal music        |
| `winter3`      | Winter (Ancient)                        | Seasonal music        |
| `woodsTheme`   | In The Deep Woods                       | Secret Woods music    |
| `springtown`   | Pelican Town                            | Town music            |
| `wavy`         | Calico Desert                           | Desert music          |
| `IslandMusic`  | Ginger Island                           | Island music          |
| `EarthMine`    | *See Table 2*                           | Mines music           |
| `FrostMine`    | *See Table 3*                           | Mines music           |
| `LavaMine`     | *See Table 4*                           | Mines music           |
| `VolcanoMines` | *See Table 5*                           | Volcano Dungeon music |

`EarthMine`, `FrostMine`, `LavaMine`, and `VolcanoMines` work slightly
differently than the other cues. These each select one of many cues, as
described in Tables 2 through 5:

**Table 2**: Cues associated with `EarthMine`.

| Cue Alias       | Soundtrack Title              |
| --------------- | ----------------------------- |
| `Crystal Bells` | Mines (Crystal Bells)         |
| `Cavern`        | Mines (A Flicker In The Deep) |
| `Secret Gnomes` | Mines (Star Lumpy)            |

**Table 3**: Cues associated with `FrostMine`.

| Cue Alias | Soundtrack Title                |
| --------- | ------------------------------- |
| `Cloth`   | Mines (Cloth)                   |
| `Icicles` | Mines (Icicles)                 |
| `XOR`     | Mines (Marimba Of Frozen Bones) |

**Table 4**: Cues associated with `LavaMine`.

| Cue Alias              | Soundtrack Title               |
| ---------------------- | ------------------------------ |
| `Near The Planet Core` | Mines (Visitor To The Unknown) |
| `Of Dwarves`           | Mines (The Lava Dwellers)      |
| `tribal`               | Mines (Danger!)                |
| `Overcast`             | Mines (Magical Shoes)          |

**Table 5**: Cues associated with `VolcanoMines`.

| Cue Alias       | Soundtrack Title                |
| --------------- | ------------------------------- |
| `VolcanoMines1` | Volcano Mines (Molten Jelly)    |
| `VolcanoMines2` | Volcano Mines (Forgotten World) |

## Acknowledgments
* Big thanks to [Now
Playing](https://www.nexusmods.com/stardewvalley/mods/19441), which made
creating this mod relatively painless.

## See also
* [Release notes](https://github.com/spakov/SilenceIsGolden/blob/main/release-notes.md)
* [Source code](https://github.com/spakov/SilenceIsGolden)
