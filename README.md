# gameFileCopy

General-purpose PyCSMM mod template for replacing/adding game files to an ISO.

## How to use this template

- Rename `gameFileCopy.json` to `<modid>.json` and `gameFileCopy.py` to `<modid>.py` where `<modid>` is the desired name of your mod.
- Replace the line `+gameFileCopy` in `modlist.txt` with `+<modid>` where `<modid>` is the desired name of your mod.
- Drop any files/directories that you want to add to the ISO in this mod folder.
- In `<modid>.json`, specify how you want to add/replace files. For example, assuming that `chara` is a directory in the mod directory,
```json
[
{
	"from": "chara",
	"to": "files/chara"
},
{
	"from": "common langEN/common_curtain_EN.cmpres",
	"to": "files/common/langEN"
}
]
```
merges `chara` in the mod directory into the `files/chara` directory of the ISO (overwriting existing files in the ISO) and replaces `files/common/langEN/common_curtain_EN.cmpres` in the ISO with `common langEN/common_curtain_EN.cmpres` relative to the mod directory.
- Zip the mod directory for loading into CSMM/distributing to others, or optionally add other mods if creating a modpack by listing them (with `+<other modid>`) in `modlist.txt` as desired.
