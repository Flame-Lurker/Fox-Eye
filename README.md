# Fox Eye — First Person Cockpit View for All-Range Mode

**Author:** Flame-Lurker  
**Version:** 1.0  
**Compatible with:** Starship 2.0.0 (Star Fox 64 PC Port)

---

## What This Mod Does

In the original Star Fox 64 and in Starship, pressing **C-Up** switches to a first-person cockpit view during linear (on-rails) stages. Fox Eye extends this to **all-range mode** — the free-roaming sections like Corneria, Fichina, and the Venom boss fight.

Press **C-Up** in any all-range mode stage to toggle the cockpit view. The camera locks to the cockpit and rotates fully with the ship, including during aerobatic maneuvers like somersaults and U-turns. Press **C-Up** again to return to the normal third-person camera.

### Features
- First-person cockpit view in all-range mode via C-Up, matching the feel of the existing on-rails cockpit view
- Camera correctly follows all ship rotations — banking, pitching, somersaults, U-turns
- Cockpit interior renders during all-range mode just as it does on linear stages

### Known Issues
- Minor skybox flicker for one or two frames when completing a U-turn maneuver. This is cosmetic and does not affect gameplay.

---

## Installation

1. Navigate to your Starship installation folder (where `Starship.exe` lives)
2. **Back up your original `Starship.exe`** — rename it to `Starship_original.exe` or copy it somewhere safe
3. Download `Starship.exe` from the [Releases](../../releases) page and place it in your Starship folder, replacing the original

That's it. Launch the game normally.

To uninstall, delete the modded `Starship.exe` and restore your backup.

---

## Notes

- This mod replaces the game executable. It does not modify any game data files or your save data.
- Built and tested on Starship 2.0.0 (Windows). Compatibility with other versions is not guaranteed.
- This is an unofficial mod and is not affiliated with the Starship development team.

*Developed with assistance from Claude (Anthropic). This is my first mod and I'm not a coder*

---

## Source & Changes

This mod modifies the Starship source code (https://github.com/HarbourMasters/Starship). The following files were changed:

**New files:**
- `src/mods/firstperson360.c` — the cockpit camera logic for all-range mode
- `src/port/resource/type/audio/AudioSequence.h/.cpp` — audio resource type required for the game to boot with the mod active
- `src/port/resource/importers/audio/SequenceFactory.h/.cpp` — audio resource loader required for the game to boot with the mod active

**Modified files:**
- `src/engine/fox_play.c` — routes the camera to the new cockpit view when C-Up is pressed in all-range mode
- `src/engine/fox_display.c` — renders the cockpit interior during all-range mode and correctly orients the camera during aerobatic maneuvers
- `src/port/Engine.cpp` — registers the audio resource loader

No game data files, save files, or assets are modified. The only change to the player experience is the new camera behavior when pressing C-Up in all-range mode.
## Changelog

**1.0** — Initial release. First-person cockpit view in all-range mode.
