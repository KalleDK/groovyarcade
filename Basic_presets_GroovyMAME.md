# Basic presets GroovyMAME #

GroovyMAME + video d3d + frame\_delay is as good as using ddraw thanks to the cleanstretch patch (in terms of pixel accuracy, and low input lag), but with much better performance when it comes to scaling. Only possible drawback may be tearing on high resolution modes (this is due to frame\_delay).


---


Automatic syncrefresh/triplebuffer selection:

If you leave both options disabled in mame.ini, groovymame will decide which one to use automatically.

If the target refresh is achieved, groovymame will select -syncrefresh. On the other hand, if we cannot achieve the desired refresh, due to monitor limitations (vertical games above 256 lines, etc), triplebuffer is used instead, so that speed is kept at 100% rennouncing to smooth scrolling.

You can control how off the obtained refresh must be in order to trigger triplebuffering, by means of the new option -sync\_refresh\_tolerance. The default value is 2 Hz.


---


To enable nonage hiscore:
You just need to set it in the mame.ini file to turn off the nagscreen. Like this :

disable\_hiscore\_patch   0

disable\_nagscreen\_patch 0

disable\_loading\_patch   0


---


You can overclock the neo geo games (and all other games) in groovymame if you wish:

Just enable cheats, then in mame config menu, go into slider controls menu -> overclock cpu to eg. 200% (option is only present if cheats are enabled)