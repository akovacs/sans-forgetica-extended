# Sans Forgetica Extended for Chinese Hànyǔ Pīnyīn Characters

Fork of the [Sans Forgetica font](https://en.wikipedia.org/wiki/Sans_forgetica) designed using principles of cognitive psychology to help better remember study notes. Download the latest stable version from the [releases page](https://github.com/akovacs/sans-forgetica-extended/releases).

## Font Preview

[<img src="screenshots/20240328_SansForgetica-v1.002-Firefox-TextRenderingPreview.png">](https://raw.githubusercontent.com/akovacs/sans-forgetica-extended/main/screenshots/20240328_SansForgetica-v1.002-Firefox-TextRenderingPreview.png)

## Main Features Added

- v1.002: Support for Chinese hànyǔ pīnyīn characters such as: ǎěǐǒǔǖǘǚǜǍĚǏǑǓǕǗǙǛ

Please see the [CHANGELOG.md](/CHANGELOG.md) for additional details

## System-wide Installation on Ubuntu Linux

1. Download the latest `SansForgetica-Regular.otf` font from the [releases page](https://github.com/akovacs/sans-forgetica-extended/releases).

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

3. Download `SansForgetica-Regular.ttf` from the [releases page](https://github.com/akovacs/sans-forgetica-extended/releases) and copy it into the `collection.media` folder within the "User 1" folder:
   `cp ~/Downloads/SansForgetica-Regular.otf ~/.local/share/Anki2/User\ 1/collection.media/`


## Usage in Anki Windows

1. Go to your Anki folder: navigate to `%APPDATA%\Anki2` using Windows Explorer.

2. Go into the folder called "User 1" (or your profile name if you’ve renamed/added profiles or use a different language).

3. Download `SansForgetica-Regular.ttf` from the [releases page](https://github.com/akovacs/sans-forgetica-extended/releases) and copy it into the `collection.media` folder.


## Usage in AnkiDroid

Based on instructions from [Anki Web Styling: Installing Fonts](https://docs.ankiweb.net/templates/styling.html#installing-fonts).

1. Determine the root AnkiDroid directory specified under Settings > Advanced > AnkiDroid directory. For me, this was `/storage/emulated/0/AnkiDroid`

2. Rename your font so that you remove all whitespace (eg: replace spaces " " with dashes "-") and add an underscore ("\_") at the front of the font name. For example, `SansForgetica Regular.ttf` should become `_SansForgetica-Regular.ttf`. The underscore ("\_") prefix avoids annoying check media messages. Note that `collection.media` only supports `.ttf` fonts, `.otf` fonts are no longer supported.

3. Download `SansForgetica-Regular.ttf` from the [releases page](https://github.com/akovacs/sans-forgetica-extended/releases) and copy it into the `collection.media` folder under the root AnkiDroid directory (for me, this was `/storage/emulated/0/AnkiDroid/collection.media`). If you have adb installed on your computer, you can use the following command: `adb push SansForgetica-Regular.ttf /storage/emulated/0/AnkiDroid/collection.media/_SansForgetica-Regular.ttf`, otherwise you can use a something like Amaze Filemanager on your Android device to copy the font to the `collection.media` folder.


## Usage in Anki Decks

If you have existing Anki decks, you also need to update their templates:

1. Click Add at the top of the main screen, and then select the note type you want to change with the top left button.
2. Click Cards.
3. In the styling section, add the following text to the bottom (after the last "}" character):

    @font-face {
      font-family: myfont;
      src: url("_SansForgetica-Regular.ttf");
    }

Applying the style to every card is very time-consuming, but there are ways to generate decks programmatically with [GenAnki](https://github.com/kerrickstaley/genanki) and similar libraries which avoid this problem. Basically, you can define your deck as a tab-separated file, and then [generate the deck using some Python code](https://charly-lersteau.com/blog/2019-11-17-create-anki-deck-csv/), applying the font via a CSS style rule.


## License

Sans Forgetica is licensed under the [Creative Commons Attribution-NonCommercial License (CC BY-NC)](https://creativecommons.org/licenses/by-nc/3.0/). This was the license provided by RMIT University, therefore I do not have the freedom to change it.


## Contributors

If you would like to add new glyphs or modify existing ones, please send a pull request with the modified FontForge `.sfd` (preferred), `.otf`, or `.ttf` file and a screenshot of the FontForge glyphs with your changes, as well as a screenshot of `sans-forgetica-font-preview.html` with your new/modified characters rendered in the browser of your choice. Thank you!


## Credits

The Sans Forgetica font was created by Melbourne’s [RMIT University](https://www.rmit.edu.au/): [news release](https://www.rmit.edu.au/news/all-news/2018/oct/sans-forgetica-news-story).

Since the original [sansforgetica.rmit](https://sansforgetica.rmit/) website is no longer available, I downloaded the font files from [1001 Fonts](https://www.1001fonts.com/sans-forgetica-font.html).

The fonts were edited using [FontForge, an Open Source Font Editor](https://fontforge.org/).