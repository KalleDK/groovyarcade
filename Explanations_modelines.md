# The 224p case #

Creating 224p modes (or lower) for groovymame doesn't make sense and is a waste of space (as long as the y-axis is kept with integer scaling).

Groovymame will pick 240p but will use 224 lines, leaving black borders up and down as required, so although you see 240p being reported in the UI it's actually rendering the native resolution, as it becomes obvious when you see the picture.

However, some emulators are not wise enough and require 224p modes, otherwise they'll stretch things to the full height (say 240p) ruining the picture. For those cases you can enable a lower value for yresmin in vmmaker.ini.

With the most recent vmmaker, you have two sources for resolutions, xml and custom list.
So you can configure each one with different settings, e.g. A magic table for GM (xml resolutions) and static table for the custom list (other emulators).




# The Dual monitor CRT/LCD case #

You just need to setup each screen as a separate desktop from Windows's display properties dialog, then assign the right video mode for each of them: a 15 kHz mode for the arcade monitor (e.g. 640x480@60i), and a whatever kHz mode for the LCD (e.g. 1920x1080@60).





# Arcade OSD, VMMaker and raw-modeline explanation #

First, you only need to install the driver once. Reinstalling it doesn't make sense, you won't get better modelines.

The fact that modes are stored in the registry only means that groovymame, arcadeosd and vmmaker have to access the registry regularly to edit/update the modes, etc.

The generateinis option was created before groovymame existed, it is totally wrong to use it with groovymame.

Probably the best way to visualize this is with a simile: imagine this is like a palette, but instead of colors, it's a palette of video modes. You can only have 120 different modes (or colors) available at the same time, but you can pick them from a nearly infinite list. The purpose or vmmaker is to create the required "palette" entries, to a maximum of 120. Then groovymame fills each entry with the required modeline, at run time, from an infinite amount of possibilities.

If you use arcadeosd to modify the registry modelines, you're just modifying those "entries" created by vmmaker, which are actually dummy modelines which destiny is to be overwritten by groovymame on run time.

You only need to run vmmaker once, with the correct monitor settings. Once the modes are created, any further adjustment can be done simply by configuring groovymame (mame.ini, crt\_range lines).

Now, those settings (crt\_range lines) ONLY apply to groovymame (mame.ini)... NOT to vmmaker.

Finally, although this is not the recommended way, since groovymame 0.151 it is possible to specify a raw modeline inside an specific game ini, so you force groovymame to pick that exact modeline. You can write down the modeline in the standard format (e.g. Modeline "320x240\_60 15.73khz 60.04Hz" 6.670 320 352 384 424 240 245 246 262 -hsync -vsync) by copying the values in arcadeosd (modeline menu) once you adjust a certain modeline, then paste this line in an ini file (e.g. Goldnaxe.ini).






# Magic Resolutions & Super Resolution #

Super Resolutions is the only way to go if you want to use Windows 7.

You can use super resolutions as well as Magic Resolutions in XP.


With magic resolutions you obtain **real** native resolutions, say 256x224, 320x240, etc. No stretching.

With super resolutions you are actually stretching on the horizontal axis. Although this is virtually unnoticeable, you are forcing your gpu to upscale (not a big problem anyway). And some might say you can feel some background "shimmering" on horizontal scrollers. _Someting to be verified_

There are some advantages to super resolutions however: better horizontal centering.





# Configuration for the Super Resolution mode #

In vmmaker.ini, disable ListFromXml, and run it.

In mame.ini, set:

resolution 2560x0

cleanstretch 2 (not meant to help with scanlines or anything but to be able to use as few resolutions as possible and still get integer scaling in the vertical axis)

This will work as a wildcard for resolutions that are 2560 pixels wide. So GroovyMAME will select the best height from the ones available to ensure that the vertical scaling will be integer as long as it's possible.

This plus the ResIList.txt below should be enough. Notice that depending on your monitor you may not need all the resolutions I added in ReslList.txt, so create your own that fits your needs, regarding maximum height, frequencies, etc...

For some emulators and Steam,
You may need to add 640x480@60, 800x600@60 and 1024x768@60 to the ResIList.txt (and set a monitor preset in vmmaker.ini which allows it)




# ResIList.txt for the Super Resolution mode #

ResIList.txt

## Desktop ##

> 640 x 480 @ 60.000000 desktop

## Super resolutions ##

2560 x 240 @ 60.000000 super

2560 x 248 @ 60.000000 super

2560 x 256 @ 60.000000 super

2560 x 264 @ 60.000000 super

2560 x 272 @ 60.000000 super

2560 x 280 @ 60.000000 super

2560 x 288 @ 60.000000 super

2560 x 296 @ 60.000000 super

2560 x 304 @ 60.000000 super

2560 x 320 @ 60.000000 super

2560 x 336 @ 60.000000 super

2560 x 344 @ 60.000000 super

2560 x 352 @ 60.000000 super

2560 x 360 @ 60.000000 super

2560 x 368 @ 60.000000 super

2560 x 376 @ 60.000000 super

2560 x 384 @ 60.000000 super

2560 x 392 @ 60.000000 super

2560 x 400 @ 60.000000 super

2560 x 416 @ 60.000000 super

2560 x 432 @ 60.000000 super

2560 x 448 @ 60.000000 super

2560 x 464 @ 60.000000 super

2560 x 480 @ 60.000000 super

2560 x 480 @ 60.000000 super

2560 x 496 @ 60.000000 super

2560 x 496 @ 60.000000 super

2560 x 512 @ 59.000000 super

2560 x 544 @ 55.000000 super

2560 x 560 @ 54.000000 super

2560 x 768 @ 60.000000 super

2560 x 800 @ 60.000000 super






# Super Resolution for 31khz CRT #

Two options (second is best but need 120Hz monitor)

1.- Software scanlines (-cleanstretch 2, -effect scanlines, -monitor arcade\_31 / vesa\_480 / vesa\_600):

2560x480@60 (31 kHz)

2560x512@60 (> 31 kHz)

2560x576@60 (> 31 kHz)

2.- Hardware scanlines (-cleanstretch 2, -black frame insertion, -monitor pc\_31\_120 / pc\_70\_120):

2560x240@120 (31 kHz)

2560x256@120 (> 31 kHz)

2560x288@120 (> 31 kHz)