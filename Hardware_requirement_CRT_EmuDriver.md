# Introduction #

To take full advantage of GroovyMame, you need a specific ATI card compatible with the CRT\_EmuDriver.
Those drivers come with a table of pre-installed video modes that GroovyMame expects to find and use.
After installing, you can use VideoModeMaker to better adjust the mode list to fit your particular monitor type.

# Details #

[link to the last revisions of CRT\_EmuDriver](http://mame.3feetunder.com/windows-ati-crt-emudriver/)

ATI Card needed for CRT\_emudrivers:

- Windows XP : ATI Radeon 7000 to the HD 4xxx

- Windows 7 : ATI HD 4xxx

However, groovymame can also generate custom timings under Windows for virtually any card supported by powerstrip, by making use of its API. Anyway, keep in mind this method is way more limited and unreliable than the standard one.

But GroovyMAME can pass your custom defined modeline to Powerstrip on a per ini base so you could in theory achieve whatever you want provided the card is supported by Powerstrip (sadly not the last one because this software is discontinued) and you have the time and patience.