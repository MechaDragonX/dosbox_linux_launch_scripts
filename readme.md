# Linux Launch Scripts for Games That Use DOSBox on Steam, GOG, etc.

## Purpose
Numerous DOS games (and many still that were simply ported to DOS, be they console games or games for competing computers) are distributed on Steam and other storefronts as simply
- The original retail game files
- A portable Windows version of the DOS emulator, DOSBox
- Custom config files that may or may not help the game look and sound as intended
- A Windows shortcut file that basically runs a specified command so all the settings are used with the provided portable DOSBox
- Other features that don't affect this (manual, soundtrack, digital versions of physical objects used for DRM checks, etc.)

As is, such releases require Wine to run on Linux, let alone macOS, where it seems such methods are inconsistent and may not always work. So I decided to start making script files to run these games as intended, without having to use Wine or set up virtual mount points in some other DOSBox installation. That's what these files are. I simply took the command found in the shortcut file and made them work with an existing global installation of DOSBox.

## Prerequisites
- DOSBox *Staging* specically requires certain prerequisites, but you might need them for any fork, including the normal version
    - SDL2
        - Debian-based: `libsdl2-2.0-0`
        - Arch: `sdl2`
        - Fedora: `SDL2`
    - SDL2_net
        - Debian-based: `libsdl2-net-2.0-0`
        - Arch: `sdl2_net`
        - Fedora: `SDL2_net`
    - opusfile
        - Debian-based: `libopusfile0`
        - Arch: `opusfile`
        - Fedora: `opusfile`
- A global installation of DOSBox. Forks such as DOSBox Staging and DOSBox-X, the fork that works with the [NEC PC-9800 series](https://en.wikipedia.org/wiki/PC-98), work as well, but you may have to modify the script
    - Normal DOSBox
        - Debian: `dosbox`
        - Ubuntu: Make sure [Universe repositories are enabled](https://help.ubuntu.com/community/AddingRepositoriesHowto) and install `dosbox`
        - Arch: `dosbox`
        - Fedora: `dosbox`
    - DOSBox Staging
        - Debian-based: Requires a custom repository
            ```bash
            sudo add-apt-repository ppa:feignint/dosbox-staging
            sudo apt-get update
            sudo apt install dosbox-staging
            ```
        - Arch AUR: `dosbox-staging`
        - Fedora: `dosbox-staging`
    - DOSBox-X (Requires modification to the script)
        - Debian-based: `dosbox-x`
        - Arch AUR:
            - SDL1: `dosbox-x`
            - SDL2: `dosbox-x-sdl2`
        - Fedora: Requires a Copr Repsository
            ```bash
            sudo dnf copr enable rob72/DOSBox-X
            sudo dnf update
            sudo dnf install DOSBox-X
            ```

## Currently Supported Games
- Alone in the Dark: [GOG](https://www.gog.com/en/game/alone_in_the_dark_the_trilogy_123) ･ [Steam](https://store.steampowered.com/app/548090/Alone_in_the_Dark_1/) ･ [Wikipedia](https://en.wikipedia.org/wiki/Alone_in_the_Dark_(1992_video_game))
- Alone in the Dark 2: [GOG](https://www.gog.com/en/game/alone_in_the_dark_the_trilogy_123) ･ [Steam](https://store.steampowered.com/app/548890/Alone_in_the_Dark_2/) ･ [Wikipedia](https://en.wikipedia.org/wiki/Alone_in_the_Dark_2_(video_game))
- Alone in the Dark 3: [GOG](https://www.gog.com/en/game/alone_in_the_dark_the_trilogy_123) ･ [Steam](https://store.steampowered.com/app/548900/Alone_in_the_Dark_3/) ･ [Wikipedia](https://en.wikipedia.org/wiki/Alone_in_the_Dark_3)
- The Elder Scrolls: Arena: [GOG](https://www.gog.com/en/game/the_elder_scrolls_arena) ･ [Steam](https://store.steampowered.com/app/1812290/The_Elder_Scrolls_Arena/) ･ [Wikipedia](https://en.wikipedia.org/wiki/The_Elder_Scrolls:_Arena)
    - While this one should work, it doesn't actually work. Despite basically the same script being used for II.
- The Elder Scrolls II: Daggerfall: [GOG](https://www.gog.com/en/game/the_elder_scrolls_chapter_ii_daggerfall) ･ [Steam](https://store.steampowered.com/app/1812390/The_Elder_Scrolls_II_Daggerfall/) ･ [Wikipedia](https://en.wikipedia.org/wiki/The_Elder_Scrolls_II:_Daggerfall)
- Tyrian 2000: [GOG](https://www.gog.com/en/game/tyrian_2000) ･ [Wikipedia](https://en.wikipedia.org/wiki/Ultima_IV:_Quest_of_the_Avatar)
- Ultima IV: Quest of the Avatar: [GOG](https://www.gog.com/en/game/ultima_4) ･ [Wikipedia](https://en.wikipedia.org/wiki/Tyrian_(video_game))

## Frequently Asked Questions
- Does the work on macOS?
    - I don't know and I can't test that at the moment. It probably could.
- When will more games added? Can you make a script that supports [some game]?
    - I don't buy or play this stuff often. I can't guarantee these scripts can work for other games if you just change a couple file names, but that's worth a try.
