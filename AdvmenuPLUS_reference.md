# About #

AdvmenuPLUS is a modification of Andrea Mazzoleni's AdvanceMENU 2.6.0 front-end source base made by **Daesdae**. [Link to project's site](http://arcadeforever.forumfree.it/?t=64108705)


# Previous notes #

This reference is complementary to the main AdvanceMENU's 2.5.0 documentation which can be found [here](http://advancemame.sourceforge.net/doc-advmenu.html).

Documentation compiled by **Rockman**.



## File paths and directories ##

It is recommended to use full paths inside **advmenu.rc**. For instance:

```
emulator_file_custom "ARCADE" "home/userX/.advance/layouts/arcade/arcade.amp" (Linux case)
```

or

```
emulator_file_custom "ARCADE" "c:/advmenuplus/layouts/arcade/arcade.amp"(Windows/DOS case)
```

On the other hand, inside **.amp** files (layouts), it's better to use relative paths ("./" or "../", right before the directory/file) which refer to the file where they are defined (advmenu.rc or an ".amp" file). The "/" slash is preferred instead of "\" to allow compatibility between different systems.

```
background_image "background.png"
```

## Units ##

All units are in pixels, unless otherwise stated, and are relative either to the resolution described in the **"display\_size xxx"** option, in the case of **advmenu.rc** general options, or to the background picture's resolution **"background\_path xxx"**, in the case of **.amp** layout files.

## Colors ##

Colors are in hexadecimal format _RRGGBB_. Example:

```
list_font_color "589c9f 373c3f"
```

# Modifications over official AdvanceMENU #

## Option-less modifications ##

  * Fixed filtering of games by orientation for versions of M.A.M.E. higher than 0.106 (Added by **VeS**).

# General Options #

**Defined in advmenu.rc**

**event\_assign EVENT KEY**

  * EVENT: in addition to the AdvanceMENU's existing events we can use these ones:
    * **emulator\_pre:** Shows the previous emulator
    * **emulator\_next:** Shows the next emulator

  * KEY: The available key names are: a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 0\_pad, 1\_pad, 2\_pad, 3\_pad, 4\_pad, 5\_pad, 6\_pad, 7\_pad, 8\_pad, 9\_pad, f1, f2, f3, f4, f5, f6, f7, f8, f9, f10, f11, f12, esc, backquote, minus, equals, backspace, tab, openbrace, closebrace, enter, semicolon, quote, backslash, less, comma, period, slash, space, insert, del, home, end, pgup, pgdn, left, right, up, down, slash\_pad, asterisk\_pad, minus\_pad, plus\_pad, period\_pad, enter\_pad, prtscr, pause, lshift, rshift, lcontrol, rcontrol, lalt, ralt, lwin, rwin, menu, scrlock, numlock, capslock.

Example:

```
event_assign emulator_pre f6
event_assign emulator_next f7 (replaces previous AdvanceMENU "event_assign emulator f6")
```

**rem\_selected yes | no**

Remembers the selected game for each emulator.

  * yes: remembers the last game launched by each emulator, both when starting AdvmenuPLUS as when switching between emulators.
  * no: (default value) only remembers last game launched before closing the front-end. It's just like the normal AdvanceMENU behaviour.

Example:

```
rem_selected yes
```

# Emulator options #

These are specific to each emulator in any mode, but the "custom mode" (no layouts). They are declared in **advmenu.rc**

**emulator\_background" "EMULATOR" "IMAGE"**

Loads a background image.

  * EMULATOR: name of the emulator referred by the option
  * IMAGE: path to the background image in PNG format.

Example:
```
emulator_background "ARCADE" "Arcade/ArcadeBackground.png"
```

**emulator\_font "EMULATOR" "FONT"**

Loads a font.

  * EMULATOR: name of the emulator referred by the option
  * IMAGE: path to the font inf TTF, GRX, PSF or RAW format.

Example:
```
emulator_font "ARCADE" "Arcade/ArcadeFont.ttf"
```

**emulator\_font\_size "EMULATOR" "auto | SIZE\_Y [SIZE\_X](SIZE_X.md)"**

Specifies the font size.

  * EMULATOR: name of the emulator referred by the option.
  * SIZE\_Y: vertical size of the font, in pixels.
  * SIZE\_X: horizontal size, in pixels. Optional, if not specified SIZE\_X is calculated based on SIZE\_Y.

Example:
```
emulator_font_size "ARCADE" "24 22"
```

**emulator\_font\_color "EMULATOR" "FORE BACK"**

Speficies the font color (for lists, menu, etc.)

  * EMULATOR: name of the emulator referred by the option.
  * FORE: color of the font, in hexadecimal
  * BACK: color of the font's background, in hexadecimal

Example:
```
emulator_font_color "ff0000 41bf28"
```

**emulator\_help "EMULATOR" "none | IMAGE/VIDEO"**

Defines a help image or video to be shown when F1 is pressed.

  * EMULATOR: name of the emulator referred by the option.
  * none: shows the default help.
  * IMAGE/VIDEO: path to the image or video in .PNG or .MNG format.

Example:
```
emulator_help "ARCADE" "Arcade/help.png"
```

**emulator\_start "EMULATOR" "none | VIDEO"**

Defines a video to be shown before loading an emulator.

  * EMULATOR: name of the emulator referred by the option.
  * none: shows no video.
  * VIDEO: path to the video in .MNG format.

Example:
```
emulator_start "ARCADE" "Arcade/intro.mng"
```

**emulator\_file\_custom "EMULATOR" "LAYOUT"**

Loads a layout in custom mode.

  * EMULATOR: name of the emulator referred by the option.
  * LAYOUT: path ot the layout file, in .AMP format.

Example:
```
emulator_file_custom "ARCADE" "Layouts/Arcade/ArcadeLayout.amp"
```

# MAME Info/History from AdvmenuPLUS #

By pressing **F11** from the list or layout we have access to a window that allows as to select the contents of **Mameinfo.dat** or **History.dat** that we want to show for the selected game.

# Filters for M.A.M.E. game list #

Adds filters for the M.A.M.E. emulator game list:

  * Mechanical (M.A.M.E. >= 0.142)
  * Mahjongs (M.A.M.E. >= 0.144)
  * Beatmania
  * Bets & Poker & Casino & Card & Jocker
  * Quiz & Trivial
  * Golf & Darts & Fish

Fixes data extraction from XML for M.A.M.E. >= 0.106:

  * Screen type (raster, vector)
  * Resolution

# Favorite lists #

Available for general list and layouts.

Changed names of **advmenu.rc** options:
  * group -> favorites
  * group\_include -> favorites\_include
  * event\_assign group f2 -> event\_assign favorites\_next f2
  * event\_assign setgroup f9 -> event\_assign setfavorites f9

Some features of favorite lists:

  * Declaration of lists, example: `favorites "list 1"`
  * Each game's lists are saved in **advmenu.rc**, in the property `game "emulator/rom" "list 1/.../list n" "..." "..." "..."`
  * The list "All Games" always exists, even if not declared in **advmenu.rc**. It shows all the games of the emulator.

  * Filters and types only apply to the "All Games" list.
  * The favorite list loaded is shown on the upper bar when in non-custom mode.
  * If there are no games in the list, a message is prompted informing of the favorite list loaded and emulator.
  * F2: shows the next list.
  * F9 or Menu->Settings...->Game Lists...: shows a window/menu to choose which list to include the current game in.

Keys used:

  * ARROWS -> move through lists
  * SPACE -> include/exclude game in selected list
  * ENTER -> save changes
  * ESC -> exit menu without saving changes

![http://img194.imageshack.us/img194/4130/65648129.png](http://img194.imageshack.us/img194/4130/65648129.png)

Access from AdvmenuPLUS menu:

  * Menu->Listing...->Game Lists...: shows a menu to choose the list.

![http://img10.imageshack.us/img10/968/menulistinggamelists.png](http://img10.imageshack.us/img10/968/menulistinggamelists.png)

The information in the upper bar shows the lists the current game belongs to.

![http://img209.imageshack.us/img209/7467/infotx.png](http://img209.imageshack.us/img209/7467/infotx.png)

# Layouts #

Layout files allows the creation of customized visualization modes for AdvmenuPLUS. In order to access to the layouts a new "custom" visualization mode has been added to the existing ones in AdvanceMENU.

Declaration of layouts in mame.rc:

**emulator\_file\_custom "EMULATOR" "LAYOUT"**

Loads a layout in custom mode

  * EMULATOR: name of the emulator referred by the option.
  * LAYOUT: path to the layout file, in .AMP format.

Example:
```
emulator_file_custom "ARCADE" "Layouts/Arcade/ArcadeLayout.amp"
```

# Layout file options #

Affect the emulators in custom mode. They are declared inside .AMP extension files.

## Orientation ##

**orientation "flip\_xy | mirror\_x | mirror\_y"**

Layout orientation.

  * flip\_xy: swaps x and y axis.
  * mirror\_x: mirror horizontally
  * mirror\_y: mirror vertically

## Help ##

**help\_image\_path "none | IMAGE/VIDEO"**

Image of video help shown when F1 is pressed.

## Loading video ##

**start\_image\_path "none | VIDEO"**

Video in .MNG format to be shown before the emulator is loaded.

## Background ##

**background\_image\_path "none | IMAGE"**

Background image.

**background\_color "COLOR"**

Background color in case no image is specified in "background\_image\_path" option.

## Game list ##

**list\_pos\_size "X Y dX dY"**

Position and size of list, in pixels.

**list\_font\_path "FONT"**

Font to use by game list.

**list\_font\_size "SIZE\_X SIZE\_Y"**

Size of game list font, in pixels.

**list\_font\_color "FontColor BackgroundColor Transparency"**

Color for unselected games and background color transparency.

**list\_font\_select\_color "FontColor BackgroundColor Transparency"**

Color for selected game and its background, and background color transparency.

**list\_rows "Rows RowSpace"**

Number of rows and space between them. If no value is specified for RowSpace, this will be adjusted so that rows occupy the whole height of the list.

**list\_cols "Cols ColSpace"**

Number of columns and space between them. If no value is specified for ColsSpace, this will be adjusted so that the columns occupy the whole width of the list.

**list\_align left | center | right**

Align for game list, by default is `left`.

**list\_diagonal d**

Shows the list leaning by "d" pixels.

## Game image windows ##

**win\_snaps none | "X Y dX dY"**

**win\_flyers none | "X Y dX dY"**

**win\_cabinets none | "X Y dX dY"**

**win\_icons none | "X Y dX dY"**

**win\_marquees none | "X Y dX dY"**

**win\_titles none | "X Y dX dY"**

**win\_color "BorderColor BackgroundColor Transparency"**

Window's border and background colors and level of transparency for the background color.

## Vertical scroll bar ##

**scroll\_pos\_size "X Y dX dY"**

Scroll bar position and size.

**scroll\_color "FORE BACK TRANSPARENCY"**

Scroll bar foreground and background colors, and background transparency.

## Information/text bars ##

**bar\_info\_N "X Y dX dY"**

**bar\_info\_N\_font "FONT"**

**bar\_info\_N\_color "FontColor BackgroundColor Transparency"**

**bar\_info\_N\_text "TEXT %TAGS%"**

Text/information that will be shown in the information bar.

  * N = 1...5 : Up to 5 information bars can be declared.
  * TEXT: Any text which is not between % signs.
  * %TAGS%: labels to show specific information of the game. The following values are allowed:
    * %description% : game name
    * %­name% : emulator name / rom name
    * %emulator%: emulator name
    * %rom%: rom name
    * %manufacturer%: manufacturer
    * %year%: year of manufacture
    * %clone% : shows the number of clones (N clones) if the game is a parent, or (clone of EMULATOR/PARENT) if the game is a clone.
    * %­proportion% : game proportion (not implemented for M.A.M.E. >= 0.106)
    * %­resolution% : game resolution (not implemented for M.A.M.E. >= 0.106)
    * %­size% : rom size
    * %­sessions% : number of sessions played
    * %­time% : total time played (hours:mins)
    * %­selected% : game number
    * %­games% : total number of games in the list
    * %­type% : game type/category
    * %­group% : game group
    * %­refresh% : game refresh frequency
    * %favorites% : favorite list loaded
    * %­game\_favorites% : favorite lists the games belongs to

Example:
```
bar_info_1_text "Game %­selected% of %­games%"
```

## Options Menu ##

**menu\_font\_path "FONT"**
Menu font.

**menu\_font\_size "size\_Y size\_X"**
Font size.

**menu\_title\_color "FORE BACK"**

Font's foreground and background colors (and menu window's color)

  * FORE: Color of title's font and the first letter of non-selected options.
  * BACK: Color of title's background and the window.

**menu\_font\_color "FORE BACK"**

Non-selected options font and background color.

  * FORE: Color of non-selected options font and external border
  * BACK: Color of non-selected options background and internal border

**menu\_font\_select\_color "FORE BACK"**

Selected option font and background color.

  * FORE: Color of selected option font
  * BACK: Color of selected option background

Example:
```
menu_font_path neuropol.ttf
menu_font_size 22

menu_title_color 9ecfce 202020
menu_font_color fefefe 202020
menu_font_select_color 9ecfce 303030
```

![http://i39.tinypic.com/258qtzp.jpg](http://i39.tinypic.com/258qtzp.jpg)