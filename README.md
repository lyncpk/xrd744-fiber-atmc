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
 This project is developed with *CRI Atom Craft Ver.2.35.19* ( ATMC ) and will build correctly for versions that support:
 - ACF Format Ver.1.20.01
 - ACB Format Ver.1.30.00

![|500](./.assets/version.png)

ATMC Ver.3, while more easily accessible, is **not** supported. Expect a non-matching .ACF binary and many in-game bugs related to Selector Labels and Automation AISAC Graphs. 
## Install
.atmcproject files are portable, but locally create user and work unit settings files. Modified installs can be more safely moved around by deleting *.atmcuser and *.user_settings files. 

ATMC projects by default are created in  `~/Documents/CriAtomCraft/`, which functions well for most purposes.

**Expect large files on build!** The .WAV files present are already large to avoid build artifacts from double compression. Reserve at least 3 Gigabytes for ATMC and this repo. 

> [!WARNING]  
> BGM, for the time being, does not contain the actual .WAV files. While this is a Git LFS repo, BGM adds 4 Gigabytes to the size alone. Given the other tools available for BGM modding in fiber, the BGM CueSheet should mostly be used for bugfixing or experimentation. 

Almost all tools in the Criware SDK are single-threaded with no GPU acceleration, so a mid-range CPU will help with navigating the larger .ACB files. Ignore the warning saying the estimated build time is in the hours range, the estimation function is *wildly* inaccurate, and all .ACB files will build in around 2 to 4 minutes, even on lower end hardware. 

## Compatibility
This project is intended for fiber, but can theoretically be retrofitted for PS3, PS4, Switch, and Xbox. 
For versions of Persona 5 Royal released prior to fiber, some Cue IDs will be misaligned and the Project Encryption Key will need to be changed. 
For base Persona 5, most .ACB files contained are completely different and will not function at all. While unlikely to cause fatal crashes, this repo should only serve as reference material for non-Royal versions.

## Testing
To verify Cue ID and Player / Voice configuration in-game, download [Ryo Framework](https://gamebanana.com/mods/549032) and toggle on "Developer Mode" in the Mod Settings to see Cue Triggers being printed to conhost.

To verify the integrity of the project with any other version of ATMC, select Build from the Global Settings window and select Build Only ACF, the .ACF exported to /xrd744 should match byte for byte with the vanilla fiber .ACF file. 

Audio files can be read via [CriAtomViewer](https://game.criware.jp/manual/native/adx2_en/latest/criatom_tools_criatomviewer_about.html), but note that most features like Local AISAC, Subsequences, Track Events, etc. are not displayed. For more accurate analysis, this project was made alongside a lightly modified build of [AtomicAudio](https://github.com/DarkPsydeOfTheMoon/AtomicAudio).   

## Stream Indexing
ATMC assigns a Wave Index to files queued for conversion partially via *filename length*, so recreations of vanilla .ACB files should use tools like [AtomicAudio](https://github.com/DarkPsydeOfTheMoon/AtomicAudio) or [SonicAudioTools](https://github.com/blueskythlikesclouds/SonicAudioTools) to extract streams with their Wave Index as a filename and **MAKE SURE** to pad their ID's to a uniform character count, i.e: 

| Extracted     | Padded          |
| ------------- | --------------- |
| memory-1.ADX  | memory-0001.ADX |
| memory-2.ADX  | memory-0002.ADX |
| memory-15.ADX | memory-0015.ADX |
| stream-1.ADX  | stream-0001.ADX |
| stream-2.ADX  | stream-0002.ADX |
| stream-15.ADX | stream-0015.ADX |

> [!WARNING]  
> Since AWB Emulator relies on Wave Index to replace audio, mod compatibility without Ryo Framework is essentially 0% unless the *full* .ACB is recreated or a "filler" Cue referencing every Wave forces ATMC to build with a matching queue.

Obviously when using ATMC to make entirely new .ACB files, this can be safely ignored and Waves can be named whatever you see fit for organization. 

## Localization
Output can be in either English or Japanese. Japanese is the default and should be where all .WAV files are stored. Unfortunately, it seems like ATLUS chose to duplicate every single .WAV if a .ACB required localization. To maintain Stream Indexing order, this behavior has to be duplicated for the time being, but better solutions will come soon.
