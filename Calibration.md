# Settings #

Which resolution to adjust to get our settings: The higher the width, the better the accuracy.

You won't get the same settings for every resolutions, especially if you use very low resolutions as a base.

However you will manage to find if a certain value must be in the range of, say, 5, or 8. Then is a matter of fine tuning.

Notes:

•To use one of the built-in presets, use it by its name in the monitor option of mame.ini, e.g.: monitor generic\_15

•To use a custom preset, use the keyword custom as the monitor name in mame.ini (monitor custom), then fill in the required crt\_range lines

•Then crt\_range lines shown below are the ones used internally by GroovyMAME for each monitor preset. You don't need to declare them explicitely. They're just provided as a starting point to readjust existing presets.

GM overrides your Arcade OSD adjustments.

So, once you center 384 x 240 with Arcade OSD, write down the resulting values in the Horizontal Geometry menu, and use them to build a custom monitor specs line to place in mame.ini

The format of the monitor\_specs lines is this:
monitor\_specs\_0-6  HfreqMin-HfreqMax, VfreqMin,VfreqMax, HFrontPorch, HSyncPulse, HBackPorch, VfrontPorch, VSyncPulse, VBackPorch, HSyncPol, VSyncPol, ActiveLinesLimit, VirtualLinesLimit

So in order to create your custom one, replace the following values with the ones you got from Arcade\_OSD:
monitor\_specs\_0  15625-15800, 49.50-65.00, 2.000, 4.700, 8.000, 0.064, 0.160, 1.056, 0, 0, 200, 448

# Calibration #

A proper calibration is often an iterative process: crt\_range -> pots -> crt\_range -> pots -> ... Good enough

In other words: the default adjustment of the pots is not always the "reference" point, they may be shifted initially.

Besides, you'll get better granularity on the horizontal by using "dotclock\_min 8.0" in mame.ini.


We just set a minimum dotclock to force horizontal resolutions below a certain limit to be doubled (x2). This causes zero degradation to the picture and has the effect to double the accuracy on the calculations regarding horizontal porches, so the result is better horizontal centering (on average).

The issue where the picture gets compressed on the borders is a typical one of CRT monitors. But you should expect it to be symmetrical. If this is not the case, it may have to do with the horizontal linearity adjustment (in case the monitor has one).

You usually test this stuff with a grid pattern. Just shrink the borders to the max, even leaving a bit of overscan to fill the whole phosphor real state, and live with it.