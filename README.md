# doomagon-wads

Game data for [Doomagon](https://github.com/syberphunk/doomagon), the Doom port
for the EMF Camp Tildagon badge.

Doomagon ships no game data of its own — the badge's internal filesystem is 3 MB
shared with everything else on it, and most of what people want to play is not
redistributable anyway. The files here are what the app downloads onto the SD
card when you ask it to.

Everything in this repository is freely redistributable. Nothing here is derived
from a commercial IWAD.

| | maps | needs | download | on the card |
|---|---|---|---|---|
| [Doomagon DM Full](#doomagon-dm-full) | 11 | nothing | 2.8 MB | 6.4 MB |
| [Doomagon DM](#doomagon-dm) | 11 | `DOOM2.WAD` | 1.0 MB | 2.7 MB |

## Doomagon DM Full

Eleven deathmatch maps and a complete game around them. Built from
[FreeDM](https://freedoom.github.io/) 0.13.0, which is a deathmatch game in its
own right; this is the same thing at a size the badge is comfortable with.

| | |
|---|---|
| file | [`doomagon-dm-full-1.0.zip`](https://github.com/syberphunk/doomagon-wads/releases/download/dmfull-1.0/doomagon-dm-full-1.0.zip) |
| download | 2,824,617 bytes |
| on the card | 6,377,349 bytes, as `doomagon-dm-full.wad` |
| maps | 11, `MAP01`–`MAP11`, seven to ten deathmatch starts each, four co-op starts each |
| **requires** | **nothing** |
| licence | BSD 3-clause — `COPYING.txt` |
| sha256 | `07495edd47d56c43822b0739f193fcb0930121a6d4f97d4aa913e63999cd8ed5` |

This is a whole game, not a patch: it carries its own sprites, sounds, menu
graphics and title demos, and it loads on a badge with no other WAD on it. There
are no monsters, because FreeDM puts none in any of its maps — everything you
meet is another player.

Do not rename it. The engine works out what a WAD is partly from its filename,
and `doomagon-dm-full.wad` is a name it has no expectations about, which is what
makes it read the file instead.

## Doomagon DM

The same eleven maps as a patch for Doom II, for people who own it. Also from
FreeDM 0.13.0.

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

If you have Doom II, this is the cheaper of the two: it borrows that IWAD's
sprites, sounds and music instead of carrying them, which is how eleven maps fit
in 1.0 MB. If you do not, take **Doomagon DM Full** above, which is the same
maps with everything they need.

## Getting it onto the badge

**From the badge, which is the way this is meant to be used.** On the WAD screen
choose `DOWNLOAD`, then `DM FULL` or `DOOMAGON DM`. It needs the badge to be on
WiFi, and it unpacks straight onto the SD card as `/sd/doom/`. Pick `BADGE`
instead of `SD CARD` as the destination only if you have no card — neither of
these fits comfortably in the badge's internal space, and `DM FULL` does not fit
at all.

**By hand,** if the badge cannot get online:

```sh
unzip doomagon-dm-full-1.0.zip     # gives doomagon-dm-full.wad
unzip doomagon-dm-1.0.zip          # gives doomagon-dm.wad
```

Copy the WAD onto a FAT-formatted microSD card, in a `doom` folder at the top of
it. Doomagon also looks in `/sd/wads` and the root of the card, so any of those
will do.

To play `doomagon-dm-full.wad`: pick it as the game on the WAD screen. To play
`doomagon-dm.wad`: pick `DOOM2.WAD` as the game, then tick `doomagon-dm.wad`
alongside it. For deathmatch, **every badge in the game needs the same files** —
Doomagon compares them when you join and will not start a match that would
desync.

To check a download arrived intact:

```sh
sha256sum -c doomagon-dm-full-1.0.zip.sha256
sha256sum -c doomagon-dm-1.0.zip.sha256
```

## Licence and attribution

Derived from FreeDM, part of the Freedoom project, and redistributed under the
same BSD 3-clause licence. `COPYING.txt` and `CREDITS.txt` are the Freedoom
project's own, copied from the 0.13.0 release, and the licence requires that
they travel with the data.

The Freedoom project does not endorse these packs and has nothing to do with
them. Maps have been selected and renumbered, and the texture, patch, flat,
sprite and sound sets reduced; anything wrong with the result is wrong here, not
upstream.
