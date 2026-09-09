# doomagon-wads

Game data for [Doomagon](https://github.com/syberphunk/doomagon), the Doom port
for the EMF Camp Tildagon badge.

Doomagon ships no game data of its own — the badge's internal filesystem is 3 MB
shared with everything else on it, and most of what people want to play is not
redistributable anyway. The files here are what the app downloads onto the SD
card when you ask it to.

Everything in this repository is freely redistributable. Nothing here is derived
from a commercial IWAD.

## Doomagon DM

Eleven deathmatch maps, `MAP01`–`MAP11`, from
[FreeDM](https://freedoom.github.io/) 0.13.0.

| | |
|---|---|
| file | [`doomagon-dm-1.0.zip`](https://github.com/syberphunk/doomagon-wads/releases/download/dm-1.0/doomagon-dm-1.0.zip) |
| download | 1,018,931 bytes |
| on the card | 2,692,233 bytes, as `doomagon-dm.wad` |
| maps | 11, seven to ten deathmatch starts each, four co-op starts each |
| **requires** | **`DOOM2.WAD`** |
| licence | BSD 3-clause — `COPYING.txt` |
| sha256 | `b152ca14d9c7f02a3f2d7681210d136df00b3ba8162cd194c73508a741953439` |

**It needs `DOOM2.WAD` under it.** This is a PWAD, not a game on its own: its
maps are named `MAPxx`, so the engine has to be in Doom II mode already, and it
carries no sprites, sounds, music or menu graphics — those come from the IWAD.
`DOOM2.WAD` is commercial and is not distributed here or anywhere else in the
project. It comes from a copy of Doom II you own.

**If you do not have Doom II,** download FreeDM instead. Doomagon offers it in
the same list. It is a complete IWAD and needs nothing under it, at 8.6 MB to
download and 21 MB on the card, against 1.0 MB and 2.7 MB for this.

## Getting it onto the badge

**From the badge, which is the way this is meant to be used.** On the WAD screen
choose `DOWNLOAD`, then `DOOMAGON DM`. It needs the badge to be on WiFi, and it
unpacks straight onto the SD card as `/sd/doom/doomagon-dm.wad`. Pick `BADGE`
instead of `SD CARD` as the destination only if you have no card — 2.7 MB is a
large part of the badge's internal space.

**By hand,** if the badge cannot get online:

```sh
unzip doomagon-dm-1.0.zip          # gives doomagon-dm.wad
```

Copy `doomagon-dm.wad` onto a FAT-formatted microSD card, in a `doom` folder at
the top of it. Doomagon also looks in `/sd/wads` and the root of the card, so
any of those will do.

To play: on the WAD screen pick `DOOM2.WAD` as the game, then tick
`doomagon-dm.wad` alongside it. For deathmatch, **every badge in the game needs
the same files** — Doomagon compares them when you join and will not start a
match that would desync.

To check the download arrived intact:

```sh
sha256sum -c doomagon-dm-1.0.zip.sha256
```

## Licence and attribution

Derived from FreeDM, part of the Freedoom project, and redistributed under the
same BSD 3-clause licence. `COPYING.txt` and `CREDITS.txt` are the Freedoom
project's own, copied from the 0.13.0 release, and the licence requires that
they travel with the data.

The Freedoom project does not endorse this pack and has nothing to do with it.
Maps have been selected and renumbered, and the texture, patch and flat sets
reduced; anything wrong with the result is wrong here, not upstream.
