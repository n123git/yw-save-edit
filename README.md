# yw-save-edit

![Node.js](https://img.shields.io/badge/Node.js-CLI-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-Web%20UI-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-Native-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Save Editor](https://img.shields.io/badge/Tool-Save%20Editor-blueviolet?style=for-the-badge)

A tool for encrypting, decrypting, editing, diffing, exporting, and scanning Yo-kai Watch save files (`.yw` / `.ywd`).

Supports all variants, including ports, versions, and regions of Yo-kai Watch 1 (3DS, Switch, Smartphone), Yo-kai Watch: Gerapo Rhythm and Yo-kai Watch 2.
> Yo-kai Watch Blasters, Yo-kai Watch 3, Yo-kai Watch Busters 2, and Yo-kai Sangokushi are all planned, but do not have complete support. 

## Versions
![Nintendo 3DS](https://img.shields.io/badge/Nintendo_3DS-Native-CC0000?style=for-the-badge&logo=nintendo3ds&logoColor=white)
![Browser](https://img.shields.io/badge/Browser-Web%20UI-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)
![Terminal](https://img.shields.io/badge/Terminal-CLI-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
### Node.js CLI
This constitutes the core of the save editor, requires Node.js for obvious reasons. See [`save/README.md`](save/README.md) before use.
* Mainly intended for debugging, and use in other tools. For instance, if you want to make a tool to randomise a save, you would use the CLI for all the parsing, decrypting, mapping etc.
> **This is NOT for most people. Use the HTML5 UI or the C++ 3DS Build**.
### HTML5 UI
Built from the CLI source files in `save/` too. Open the output in any modern browser, including mobile. See [`save/README.md`](save/README.md) for build instructions.
* This runs on all platforms with support for a modern browser, this includes:
  * Windows
  * Linux
  * macOS
  * iOS
  * Android
> TODO: Create a usage tutorial in `wiki`.
 
### C++ (3DS Native)
Runs directly on hardware.
> This is unfinished, and will likely be released as a part of v1.1.

## Save File Basics
> **Please** follow proper proceedure; **make a backup** before you save edit. If any corruption is caused, you may DM @n123original on discord for help, but I cannot guarantee that corruption is restorable. *Use this tool at your own risk*.

The main save files in 3DS Yo-kai Watch games are:

- `game0.yw` - Backup save slot, exclusively used in *Yo-kai Watch 1 for Smartphone*.
- `game1.yw` - Main save data for slot 1.
- `game2.yw` - Main save data for slot 2.
- `game3.yw` - Main save data for slot 3 *(not present in YW3 or YWB2)*.
- `head.yw` -  Preview data, metadata, and encryption keys for all save slots.

Other files such as `sys.yw` are present from Yo-kai Watch Blasters onwards but not covered here, as the save editor does not currently support their games, and hence their new files.

> **Note:** Yo-kai Sangokushi does not follow this save structure. Despite being a 3DS title, it is a spinoff developed by Koei Tecmo rather than Level-5 and does not use Level-5's engine. This game will be supported either last, or second-to-last.

## Schema Files

Schema files (`.json5`) map and document the fields and structs within each save section, enabling human-readable editing and JSON import/export. See [`save/README.md`](save/README.md) for details. The following are built in:

| File            | Covers                                                            |
| --------------- | ----------------------------------------------------------------- |
| `yw1_eur.json5` | Yo-kai Watch 1 (3DS): EUR / NA / AUS / KOR                        |
| `yw2.json5`     | Yo-kai Watch 2. All regions, versions and variants are supported. |

## Progress
- [X] YW1 Crypto
- [X] Section Parsing
- [X] YW2 Crypto
- [X] YW2 Integrity Checks
- [X] JSON Export
- [X] Roundtrip completeness
- [X] Create JSON5 schema system
- [X] Complete feature parity with Togenyan's editor for YW2
- [X] Map out 25% of YW2 save files
- [X] Map out 50% of YW2 save files
- [X] Nearly completely map out YW2 save files
- [X] Map out key regions of YW2 header files
- [X] Complete feature parity with Togenyan's editor for YW1
- [X] Improve schema system with version handling, `id` handling, and raw `bitarray` and `bytearray` types
- [X] Switch to JSON5 exports by default
- [X] Fix header support, with version and game detection for YW1, YW2, YWB, YW3, and YWB2 header files
- [X] RE `GENERIC_HANDLE` (togenyan did not do this properly) and create handle parsing and generation code.
- [X] RE V1 SramIO containers for 1m
- [X] RE V2 SramIO containers for 1m
- [X] Write SramIO container code
- [X] RE YGR .s files
- [X] Confirm all integrity checks found
- [X] Confirm write works
- [X] Create YGR schema
- [X] Write YGR documentation
- [X] Finish YGR support
- [X] Work on UI
- [ ] Release YGR documentation
- [ ] Test a vulnerability in DWE's implementation of SramIO, and find any potential use for it
- [ ] Map out 30% of YW1 save files
- [ ] Map out key regions of YW1 header files
- [ ] Add support for YWB
- [ ] Work on mod support
- [ ] Pretend to release it
- [ ] Actually release it
- [ ] Create C++ Build
- [ ] Debate implementing mod support for the C++ Build
- [ ] Implement it, if the above, suggests I should.
