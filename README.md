<div style="display:flex;flex-direction:row;">
	<img src="./.assets/logo.png" width="85"/>
	<h1>xrd744-fiber-atmc</h1>
</div>

This is a version control repository for specific **Atom Configuration Files** ( .ACF ) and **Atom CueSheet Binaries** ( .ACB ) found in multiplatform releases of "fiber", a.k.a *Persona 5 Royal Remaster Edition*.

Future release builds of this repository will contain:
- /sound/xrd744.acf
- /sound/dungeon/dungeon_se.acb
- /sound/bgm.acb
- /sound/system.acb
- /sound/mementos.acb
- /sound/my_palace.acb

> [!WARNING]  
> This project is nowhere near completion! Don't expect builds anytime soon.

## Software
 This project is developed with *CRI Atom Craft Ver.2.35.19* ( atmc ) and will build correctly for versions that support:
 - ACF Format Ver.1.20.01
 - ACB Format Ver.1.30.00

![|500](./.assets/version.png)

atmc Ver.3, while more easily accessible, is **not** supported. Expect a non-matching .ACF binary and many in-game bugs related to Selector Labels and Automation AISAC Graphs. 
## Install
.atmcproject files are portable, but locally create user and work unit settings files. Modified installs can be more safely moved around by deleting *.atmcuser and *.user_settings. 

atmc projects by default are created in  `~/Documents/CriAtomCraft/`, which is a good default.

**Expect large files on build!** The .WAV files present are already large to avoid build artifacts from double compression. Reserve at least 3 Gigabytes for atmc and this repo. 
## Compatibility
This project is intended for fiber, but can theoretically be retrofitted for PS3, PS4, Switch, and Xbox. For versions of Persona 5 Royal released prior to fiber, some Cue IDs will be misaligned and the Project Encryption Key will need to be changed. 
For base Persona 5, most .ACB files contained are completely different and will not function at all. While unlikely to cause fatal crashes, this repo should only serve as reference material for non-Royal versions.

## Testing
To verify Cue ID and Player / Voice configuration in-game, download [Ryo Framework](https://gamebanana.com/mods/549032) and toggle on "Developer Mode" in the Mod Settings to see Cue Triggers being printed to conhost.
To verify the integrity of the project with any other version of atmc, select Build from the Global Settings window and select Build Only ACF, the .ACF exported to /xrd744 should match byte for byte with the vanilla fiber .ACF file. 