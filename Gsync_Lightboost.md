# Technical informations #

Black frame insertion (also called Lightboost) halves the current refresh rate whatever it is. If you force black frame insertion on a fixed 60 Hz display, a 60 Hz game will run at 50% of speed. If you have a 120 Hz capable monitor, you will select this refresh, either in the desktop properties or in GM setup, then apply black frame insertion and everthing should run smoothly at 60 Hz.

Obviously if you’re using a 120Hz LCD, games that didn't run at 60 Hz natively will run at the wrong speed, as with any other LCD, but perfectly smooth. Black frame insertion requires the most strict v-sync so there's no room for triple buffering here.

On the other hand, when using a CRT, groovymame will precalculate the exact double refresh rate beforehand, whenever possible, so when black frame insertion is applied the resulting refresh is equal the native. It is possible to achieve arbitrary refresh rates for LCD monitors too, in combination with Powerstrip, but you need to find a model that's both 120 Hz and variable refresh rate capable, and a video card that's supported by Powerstrip (unlikely combination of things).

For G-sync you need a specific implementation of black frame insertion, one that is based on the CPU clock rather than the GPU clock (GroovyMAME does it). You will need to divide the frame period by 2 just based on the CPU clock, in order to insert the black frame just in time, and this needs to be really accurate, otherwise you'll get a flashy picture like a silent film from the 1920's.

It's still a mistery how to combine G-Sync with Lightboost in a sensible way.

Lightboost for 60 Hz games requires black frame insertion, but...

Black frame insertion requires syncrefresh, but...

G-sync involves disabling syncrefresh


... Black frame insertion might be possible without syncrefresh, just based on the cpu clock, but this would involve some important modifications of MAME throttling routines.

# Setup #

Regarding groovymame & Lightboost, you need to use these settings:

monitor lcd

black\_frame\_insertion 1

syncrefresh 1

... While forcing the desktop resolution to 120 Hz

On the other hand, G-Sync has not been tested yet with groovymame. Regular MAME could be just as good in this situation.

A guessed settings would be:

triplebuffer 0

syncrefresh 0

waitvsync 0

throttle 1