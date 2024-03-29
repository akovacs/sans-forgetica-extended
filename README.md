# Sans Forgetica Extended for Chinese Hànyǔ Pīnyīn Characters

Fork of the [Sans Forgetica font](https://en.wikipedia.org/wiki/Sans_forgetica) designed using principles of cognitive psychology to help better remember study notes. This version adds glyphs for the following Chinese hànyǔ pīnyīn characters:

| Character | Unicode | Description                                      |
| ----------| ------- | ------------------------------------------------ |
| Ǎ         | 0x1CD   | latin capital letter a with caron                |
| ǎ         | 0x1CE   | latin small letter a with caron                  |
| Ě         | 0x11A   | latin capital letter e with caron                |
| ě         | 0x11B   | latin small letter e with caron                  |
| Ǐ         | 0x1CF   | latin capital letter i with caron                |
| ǐ         | 0x1D0   | latin small letter i with caron                  |
| Ǒ         | 0x1D1   | latin capital letter o with caron                |
| ǒ         | 0x1D2   | latin small letter o with caron                  |
| Ǔ         | 0x1D3   | latin capital letter u with caron                |
| ǔ         | 0x1D4   | latin small letter u with caron                  |
| Ǖ         | 0x1D5   | latin capital letter u with diaeresis and macron |
| ǖ         | 0x1D6   | latin small letter u with diaeresis and macron   |
| Ǘ         | 0x1D7   | latin capital letter u with diaeresis and acute  |
| ǘ         | 0x1D8   | latin small letter u with diaeresis and acute    |
| Ǚ         | 0x1D9   | latin capital letter u with diaeresis and caron  |
| ǚ         | 0x1DA   | latin small letter u with diaeresis and caron    |
| Ǜ         | 0x1DB   | latin capital letter u with diaeresis and grave  |
| ǜ         | 0x1DC   | latin small letter u with diaeresis and grave    |


## System-wide Installation on Ubuntu Linux

1. Download the latest `SansForgetica-Regular.otf` font from the releases page.

2. Open the `SansForgetica-Regular.otf` file with `gnome-font-viewer` or the font viewer of your choice.

3. Click the Install button.


## Removing / Reinstalling Newer Versions of the Font

    # List font path
    fc-list "Sans Forgetica"

    # remove font
    sudo rm ~/.local/share/fonts/SansForgetica-Regular.otf

    # clear font cache
    fc-cache -fv


## Usage in Anki Linux

Based on instructions from [Anki Web Styling: Installing Fonts](https://docs.ankiweb.net/templates/styling.html#installing-fonts) and [Anki Web File Locations](https://docs.ankiweb.net/files.html#file-locations).

1. Go to your Anki folder: `cd ~/.local/share/Anki2`

2. Go into the folder called "User 1" (or your profile name if you’ve renamed/added profiles or use a different language).

3. Copy `SansForgetica-Regular.ttf` into the `collection.media` folder within the "User 1" folder:
   `cp ~/Downloads/SansForgetica-Regular.otf ~/.local/share/Anki2/User\ 1/collection.media/`


## Usage in Anki Windows

1. Go to your Anki folder: navigate to `%APPDATA%\Anki2` using Windows Explorer.

2. Go into the folder called "User 1" (or your profile name if you’ve renamed/added profiles or use a different language).

3. Copy `SansForgetica-Regular.ttf` into the `collection.media` folder.


## Usage in AnkiDroid

Based on instructions from [Anki Web Styling: Installing Fonts](https://docs.ankiweb.net/templates/styling.html#installing-fonts).

1. Determine the root AnkiDroid directory specified under Settings > Advanced > AnkiDroid directory. For me, this was `/storage/emulated/0/AnkiDroid`

2. Rename your font so that you remove all whitespace (eg: replace spaces " " with dashes "-") and add an underscore ("\_") at the front of the font name. For example, `SansForgetica Regular.ttf` should become `_SansForgetica-Regular.ttf`. The underscore ("\_") prefix avoids annoying check media messages. Note that `collection.media` only supports `.ttf` fonts, `.otf` fonts are no longer supported.

3. Copy `_SansForgetica-Regular.ttf` to the `collection.media` folder under the root AnkiDroid directory (for me, this was `/storage/emulated/0/AnkiDroid/collection.media`). If you have adb installed on your computer, you can use the following command: `adb push SansForgetica-Regular.ttf /storage/emulated/0/AnkiDroid/collection.media/_SansForgetica-Regular.ttf`, otherwise you can use a something like Amaze Filemanager on your Android device to copy the font to the `collection.media` folder.


## Usage in Anki Decks

If you have existing Anki decks, you also need to update their templates:

1. Click Add at the top of the main screen, and then select the note type you want to change with the top left button.
2. Click Cards.
3. In the styling section, add the following text to the bottom (after the last "}" character):

    @font-face {
      font-family: myfont;
      src: url("_SansForgetica-Regular.ttf");
    }

Applying the style to every card is very time-consuming, but there are ways to generate decks programmatically with [GenAnki](https://github.com/kerrickstaley/genanki) and similar libraries which avoid this problem. Basically, you can define your deck as a tab-separated file, and then [generate the deck using some Python code](https://charly-lersteau.com/blog/2019-11-17-create-anki-deck-csv/).


## License

Sans Forgetica is licensed under the [Creative Commons Attribution-NonCommercial License (CC BY-NC)](https://creativecommons.org/licenses/by-nc/3.0/).


## Credits

The Sans Forgetica font was created by Melbourne’s [RMIT University](https://www.rmit.edu.au/): [news release](https://www.rmit.edu.au/news/all-news/2018/oct/sans-forgetica-news-story).

Since the original [sansforgetica.rmit](https://sansforgetica.rmit/) website is no longer available, I downloaded the font files from [1001 Fonts](https://www.1001fonts.com/sans-forgetica-font.html).

The fonts were edited using [FontForge, an Open Source Font Editor](https://fontforge.org/).