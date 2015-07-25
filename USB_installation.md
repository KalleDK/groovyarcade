

# Installing Groovy Arcade Arch Linux to a USB Flash Drive #

This guide is meant for people not familiar with the Linux operating system. Experienced Linux users will probably prefer to install Groovy Arcade to a fixed hard drive instead of an USB pendrive.

Installing Groovy Arcade to a fixed hard drive is not a much more difficult process, it's just as easy, indeed. However, as a Windows user, I have an already working Windows-based arcade system that required endless hours of tweaking. Although I like testing new stuff, switching my system's hard drive in order to test Groovy Arcade is something I definitely don't want to go through. I would like to preserve my arcade system unmodified whenever possible.

The good news are you can create a fully working Groovy Arcade Linux setup without modifying a single byte in your hard drive. By installing Groovy Arcade to an USB flash drive, you will build a functional arcade system in half an hour, which you can use since then as an alternative to your already working Windows system. Switching to Groovy Arcade and back to Windows is as easy as plugging or unplugging a pendrive before booting. It's better than that: Groovy Arcade in a pendrive is a portable arcade system.

# Requirements #

  * A PC which BIOS can boot from USB.
  * A supported video card (ATI).
  * A NTFS-formatted hard drive with your ROMs already in (i.e. your currently working Windows system).
  * A USB drive of 8 GB or larger.
  * A blank CD (preferably rewritable).
  * A keyboard (preferably PS-2).
  * A standard PC monitor (optional).
  * An hour of your time.

# Getting started #

**Creating the live-cd**

First, we will download the most recent Groovy Arcade CD image. If yours is a 64-bit capable PC, use the 64-bit version for better performance: **GroovyArcade-Arch2013.02.24-x86\_64.iso**. Next, burn this image to a blank CD. I like using rewriteable CDs for these tasks.

**Checking your BIOS settings**

Booting from the CD/DVD drive often requires you to enter the BIOS setup menu and change the boot order (boot device sequence). You can often choose the right device on boot, usually by pressing F11 or F12, which brings the device selection menu. Make sure you know how this works with your particular system before proceeding.

**Keyboard**

Probably more than 90% of Groovy Arcade menus can be navigated by just using the cursors, Enter and Escape keys. Thanks to this, you will be able to perform most of the required operations with the only help of your arcade controls, provided you have those keys mapped to your control panel buttons (you should).

However, for a few operations during installation, you will need to type some keys, so having a keyboard plugged is going to be required.

For older mother boards, it may be necessary to enable 'legacy USB support' to get USB keyboards working before the operating system loads. PS-2 keyboards just work.


**Use your target arcade PC to run for the installation process**

You are probably tempted to use your laptop or desktop PC in order to do the installation before moving the pendrive to your arcade cabinet.

Well, although this is indeed possible and it works, it does require some further teaking to be performed on the target system, and you may encounter additional difficulties. So I strongly recommend against this practice, unless you have some experience on previous installations.

Always make the installation using the target PC where Groovy Arcade is going to run.

**Dealing with the boot frequency issue**

Before we proceed, you need to be aware that the BIOS prompt, as well as the first seconds of the boot process, **will output a 31 kHz signal** to your monitor. Yes, even with Groovy Arcade.

Due to this, if yours is a standard fixed-sync 15 kHz monitor, the first screens during the boot process will be out of sync and partially or totally garbled. But more important, this also means a potential **risk of damage** to your monitor. If you have some experience with PC-to-arcade stuff, this is a well-known issue to you and I'm sure you'll find your way through it.

Anyway, here are some suggestions to deal with this old issue:

  * Use an Ultimarc's ArcadeVGA, which can output 15 kHz during boot.
  * Use an Ultimarc's J-Pac with a normal ATI card, this will filter the 31 kHz signal to create a safe 15 kHz split screen, that is readable to some extent (more or less depending on the card).
  * Have a PC monitor around so you can deal with the boot menu (see picture in next step), and then switch cables back to the arcade monitor right after this (this is a bit tricky, because you should manage to switch to your arcade monitor _right_ after you select the proper boot option, if you leave the PC monitor attached for too long during the boot process, there's a risk that its EDID might mess with our settings).
  * Use a standard PC such as a laptop for the installation process, forgetting my advice in the previous point.
  * Just leave the arcade monitor off and resolve the first menu blindly using the picture below as a reference. Then turn the monitor on.
  * etc...

A few seconds after booting, the system will be outputting a 15 kHz signal already.

Don't panic: once the system is installed, you shouldn't need to access any options during boot time any more, so you will just leave the boot process to complete with your monitor off, and then turn it on once the system is loaded and a safe frequency is being output.




# Booting the live-CD #

It's time to boot Groovy Arcade. Insert the live-CD in the CD drive and start your system. Some spinning noise and we should be here:

![http://aburamushi.net/calamity/img/20130224_224144.jpg](http://aburamushi.net/calamity/img/20130224_224144.jpg)

Now, before you complain, if your picture looks scrambled compared to this, keep in mind I'm using an ArcadeVGA card in this machine, that's how I get perfect 15-kHz pictures on boot. You can use this picture to guide you through the menu on your monitor in case you can't get a clear picture (use up/down cursors, and Enter).

**What video option should we select?**

Most of the time, we will be using either one of the first two options: **[DVI-1 15kHz]** or **[VGA-1 15khz]** options. (Notice this is the case even for PAL/NTSC TV sets. PAL/NTSC specific options should only be used for highly restrictive TV sets).

In order to know which output to use, VGA or DVI, you need to determine which one is the primary output device. For most older ATI cards, the VGA is the primary device, so you will pick [VGA-1 15kHz]. For newer models, such as the HD 4xxx family, the DVI is actually the primary device, so you will need to pick [DVI-1 15kHz] and use a DVI-VGA adapter.

You'll probably be already using the right output if you have a working Windows system. Otherwise you may need to do some testing until you find the right ouput. A typical symptom that you're using the wrong output is getting a blank screen a few seconds after boot.

So mine is an old ArcadeVGA and I'm connecting it through VGA, so I will pick VGA-1. Find your proper output, and after a few seconds we should be here:

![http://aburamushi.net/calamity/img/20130224_224234.jpg](http://aburamushi.net/calamity/img/20130224_224234.jpg)

Notice that, at this point, our pictures should already look the same, so you should have a clear 15 kHz picture ready on your end. You'll see a lot of text messages scrolling on the screen. In case you're not familiar with Linux, this is how the boot process looks like. In less than a minute, we will see this welcome screen:

![http://aburamushi.net/calamity/img/20130224_224259.jpg](http://aburamushi.net/calamity/img/20130224_224259.jpg)

Press Enter, and we're ready to discover the Groovy Arcade live-CD.

# Testing the live-CD #

Groovy Arcade live-CD starts directly into an old-school looking menu system called **gasetup** (G.A. setup). This menu is designed to access most Groovy Arcade configuration features without the need of typing obscure commands which would frighten the average user (you and me). Behind the scenes, there's a fully powered Arch Linux system, that experienced users can tweak to their like. You will quickly get familiar with the gasetup menu once you start navigating it. Here's how the main menu looks like:

![http://aburamushi.net/calamity/img/20130224_224334.jpg](http://aburamushi.net/calamity/img/20130224_224334.jpg)

The first thing we need to do is to tell Groovy Arcade the kind of monitor we're going to use. Groovy Arcade needs two separate video configurations:

  * **Grub's video configuration:** this is the one we just did on boot. These settings are used by the system kernel only. The 15 kHz picture you're seeing in gasetup is the result of these grub video settings.
  * **X Window video configuration:** this is the one we're about to do. All our emulators will run over a X Window System. We need to provide the right video settings that suit our monitor, and these will be used by all our emulators and the desktop applications (LXDE).

So let's enter the Setup menu: option 2, **"Setup (video, audio, network, etc.)"**. This menu is where all the required settings are done:

![http://aburamushi.net/calamity/img/20130224_224356.jpg](http://aburamushi.net/calamity/img/20130224_224356.jpg)

Now, we'll enter the fist submenu: option 1, **"Video Setup":**

![http://aburamushi.net/calamity/img/20130224_224417.jpg](http://aburamushi.net/calamity/img/20130224_224417.jpg)

Ok. Now we'll be shown a long list with many different types of monitors. If you're lucky and your particular monitor is listed, go for it. If this is not the case, don't panic, these are the options to consider first:

  * **Generic 15.7 kHz:** (15.625-15.750 kHz) This is a very conservative setting which should work for all standard fixed-sync 15-kHz arcade monitors and most TVs.
  * **Arcade 15.7 kHz - standard resolution:** (15.625-16.200 kHz) This setting is similar to the previous one but allows for a higher horizontal frequency. This means more lines of resolution provided the monitor supports it. This setting should work for many standard fixed-sync 15 kHz arcade monitors and some TVs.
  * **Arcade 15.7-16.5 kHz - extended resolution:** (15.625-16.500 kHz) Similar to the previous one, but still allows for a slightly higher horizontal frequency. This setting will work on extended resolution fixed-sync arcade monitors and just a few TVs (e.g. Sony).

These three options, are ordered from top to bottom as safer to less safe. If you don't know much about monitors and want to be absolutely safe, choose "Generic 15.7 kHz". On the other hand, if you're sure your monitor can deal with extended resolutions up to 16.5 kHz, pick "Arcade 15.7-16.5 kHz - extended resolution". I believe the one in the middle, "Arcade 15.7 kHz - standard resolution" is a good compromise for most arcade monitors.

Bear in mind that dual-sync 15-25 kHz or even tri-sync 15-25-31 kHz monitors can be safely configured through the "Generic 15.7 kHz" option. You will just miss the higher resolutions/frequencies.

If yours is a dual or tri-sync monitor and you want to benefit from the higher frequencies, but still don't see your monitor listed, you can use one of the generic ready-made presets:

  * Arcade 15.7/25.0 kHz - dual-sync
  * Arcade 15.7/25.0/31.5 kHz - tri-sync

These should be safe enough, just bear in mind some manual adjustments to the monitor's geometry settings on frequency switching will be required, as these settings are not calibrated for your specific monitor.

You also have generic presets for medium and high resolution monitors:

  * Arcade 25.0 kHz - medium resolution
  * Arcade 31.5 kHz - high resolution

Once you've chosen the right option, press OK, you'll be asked for confimation, answer YES:

![http://aburamushi.net/calamity/img/20130224_224436.jpg](http://aburamushi.net/calamity/img/20130224_224436.jpg)

That was all you need to setup by now. Time to test some games. This step is required to check that the system main features are in working order.

We'll exit the setup menu, back to the main menu. Now we will enter option 1: **"Start Front-End / Window Manager"**. Groovy Arcade is pre-configured to launch the **AdvmenuPLUS** front-end by default. Loading this front-end for the first time can be a bit slow, especially when running from a CD, because it needs to read and process a huge XML file. Just a bit of patience and you'll be here:

![http://aburamushi.net/calamity/img/20130224_224514.jpg](http://aburamushi.net/calamity/img/20130224_224514.jpg)

Groovy Arcade CD contains some freely available ROMs. Those are the ones you'll be able to test and play here. They're more than enough to check basic functionality.

My favourite one is the last on the list: **World Rally**, a 1993 cool arcade game by Gaelco, with **Carlos Sainz's** car included:

![http://aburamushi.net/calamity/img/20130224_224622.jpg](http://aburamushi.net/calamity/img/20130224_224622.jpg)

Launch this game and press "F11". This will bring MAME's speed percent text on the right-top corner. Check that this figure stays at "100%". This is a quick check to make sure that the v-sync feature works. A properly working v-sync is the single most important feature an arcade system must have. Things to consider:

  * It doesn't matter if you eventually see the speed drop to 99% provided it quickly returns to 100% and the scroll is smooth.
  * Continuous speed drop-downs mean that your system's CPU is not powerfull enough for modern MAME. Bad luck.
  * On the other hand, a crazy and erratic speed means the video drivers are not providing reliable v-sync information. Too bad.

If you're using the right hardware (i.e. an ATI video card) everything should be fine at this point. Nvidia cards are now supported too but still in experimental state, so we can't promise anything, you're warned.

The **World Rally** game is a good one to test, because it has both scroll and audio. Look carefully at the scroll, judge its smoothness, enjoy. You may have issues however with audio. Sound volume might be too low. Check that at least you have audio, you'll be able to adjust its volume later.

# Installation #

If your test completed succesfully, we're ready to start the installation to the flash drive. Exit **AdvmenuPLUS** by pressing Escape, and you'll be back to the main menu.

Take your USB pendrive and plug it in now.

We're going to enter option 3: **"HD Installation and Partition Tools":**

![http://aburamushi.net/calamity/img/20130224_224707.jpg](http://aburamushi.net/calamity/img/20130224_224707.jpg)

I beg you to pay special attention during the next steps, because they are potentially dangerous. **You can actually erase all your hard drive contents if you pick the wrong option by accident.**

You don't need to be scared, just concentrate on your task a bit harder.

Obviously, **all the contents in your USB pendrive, if any, will be deleted**, so make sure to backup whatever relevant data you may have in it.

We're going to enter option 3: **"Partition Manager (CAUTION!)"** (_sound of violins_)

Now you will be asked **"Do you want to stop Automount?"**. Answer YES. And you'll be shown a screen similar to this:

![http://aburamushi.net/calamity/img/20130224_224741.jpg](http://aburamushi.net/calamity/img/20130224_224741.jpg)

Your actual screen will depend on the drives you have available in your sytem. Anyway, the **very important** thing here is to identify which of these drives represents your pendrive.

Unlike Windows, where drives are named with letters like **A:, C:, D:**, etc., in Linux, drives are reported as **"/dev/sda"**, **"/dev/sdb"**, etc.

In my system, I know that I have a 160-GB hard drive, and the pendrive I'm using has a capacity of 16-GB. So, looking at the reported sizes in the previous screen, it becomes obvious that **in my particular system, /dev/sda is the hard drive, and /dev/sdb is the pendrive.** But please, don't make any assumption based on my system, always double check.

Ok, so because I'm absolutely positive that **/dev/sdb** is my **pendrive**, I will select this drive in order to enter the **partition tool**. This is how it looks like:

![http://aburamushi.net/calamity/img/20130224_224758.jpg](http://aburamushi.net/calamity/img/20130224_224758.jpg)

Notice that your screen will be different to mine. This is due to the fact that I had a previous Groovy Arcade installation already in this pendrive (one of the distributions we've been testing these months).

This screen shows the list of partitions that exist in the drive. In my case, I have **sdb1, sdb2 and sdb3**. These are my old Groovy Arcade partitions (GA creates 3 separate partitions). You will probably have a single **sdb1** partition, which file format is likely to be **fat32**, if you've been using this pendrive previously with Windows.

Anyway, we need to delete all existing partitions in the pendrive. So you will place the cursor on them one by one, and select **[Delete](Delete.md)**. When you're done, select **[Write](Write.md)**, so the updated partition table will be written to disk. At this point, **_all data in the disk will be erased_**. You will be asked for confirmation, and you need to type **y-e-s** here. (This is the step that required a keyboard, remind?)

We'll be ready to go when the list of partitions shown is empty. Select **[Quit](Quit.md)** then. Now you will be asked **"Do you want to start Automount?", and you will answer NO.**

We are now back in the **"HD Installation and Partition Tools":**, let's enter option 2: **"Hard Drive Installation"**

You'll be asked for confirmation again: **"Install to disk?"** Answer YES.

Now you're going to be asked a series of questions:

**"Do you want to setup Networking?"** -> NO

**"Do you want to setup Audio?"** -> NO

**"Do you want to setup System settings?** -> NO

**"Do you want to have a drive of ROMs/Snaps to mount as /home/roms?** -> NO

Dont worry about this by now, you will be able to edit these settings later on the already installed system.

Finally, you'll reach a point where you're asked:

**"Do you want to Auto-partition an empty drive?"** Now you must answer YES.

You'll be shown the drive selection menu again, and as we did before, make sure to pick the pendrive. The installation process will start:

![http://aburamushi.net/calamity/img/20130224_225206.jpg](http://aburamushi.net/calamity/img/20130224_225206.jpg)

This will take a while so go and get a coffee. Three partitions will be created in your pendrive: **GAboot**, **SwapSpace** and **GA**, and they'll be formatted separately. If the process is completed successfully, you will be shown this screen:

![http://aburamushi.net/calamity/img/20130224_231531.jpg](http://aburamushi.net/calamity/img/20130224_231531.jpg)

Now you should have a bootable Groovy Arcade pendrive. You can remove the live-CD on boot (not before). If you've configured your BIOS properly, it will find your bootable pendrive and boot from it.

Fingers crossed. Let's see if our Groovy Arcade pendrive works. Boot time should be much faster now. After a while, the **AdvmenuPLUS** frontend will show.

If you reached this point, **congratulations!**

# Finding your ROMs #

Now you have a fully working arcade system, but unfortunately we just have a few games to play with in it. We need to tell Groovy Arcade where our ROMs live. Fortunately this is a pretty straight-forward process now, and one of the features that makes Groovy Arcade so cool.

In order to find the ROMs we first need to exit **AdvmenuPLUS** by pressing Escape. This will close the front-end and send us back to gasetup, after a few seconds.

At this point you must already be very familiar with gasetup. Enter
**"Setup (video, audio, network, etc.)"**, then **"Add ROM path"**. This will bring a list of systems whose ROMs are to be searched for. We will start by **GroovyMAME**, the default emulator for arcade games. Once selected, you will be shown this menu:

![http://aburamushi.net/calamity/img/20130224_232209.jpg](http://aburamushi.net/calamity/img/20130224_232209.jpg)

This deserves a brief explanation.

Groovy Arcade will search your entire system for potential ROM paths. This includes your local hard drive, where your current NTFS Windows partition is, with all your ROMs, snaps, etc. in it.

Of course, Groovy Arcade needs some criteria in order to filter ROM paths. It is assumed that the word **"roms"** has to be present somewhere within the path name.

The first option will search for paths which name _ends_ with the word "roms": e.g. **"/blablabla/.../roms"**

The second option will search for paths which name _contains_ the word "roms": e.g. **"/blablabla/.../roms/blablabla"**

So say you have the following path structure in your hard drive:

```
C:\Emu\MAME\roms
C:\Emu\Megadrive\roms
C:\Emu\SNES\roms
```

... then you would choose the first option.

On the other hand, if you have the following path structure:

```
C:\roms\MAME
C:\roms\Megadrive
C:\roms\SNES
```

... then you would choose the second option.

You may be wondering why we shouldn't use the second option all the time, which implies the first condition too. Well, the reason is that if you store CHD files in your ROM folder, because of the way these are structured, that would produce an extremely long list of candidate paths.

In my particular setup, I need to use the second search option. You'll need to wait while Groovy Arcade searches your entire system:

![http://aburamushi.net/calamity/img/20130224_232011.jpg](http://aburamushi.net/calamity/img/20130224_232011.jpg)

Eventually, it will show the final list of candidate paths. This is what I get here:

![http://aburamushi.net/calamity/img/20130224_232135.jpg](http://aburamushi.net/calamity/img/20130224_232135.jpg)

Have a look at this picture. If your not familiar with Linux, it may result a bit confusing at first. As we said, in Linux you don't have a DOS-like drive letter structure. So your hard drive paths won't start by "C:\" as you might expect. Instead of that, in Linux, drives are _mounted_ as a directory in a tree that represents the whole system. Groovy Arcade _mounts_ all local drives inside a folder named **"/media"**. So this is the place you need to search when looking for your files.

Inside **"/media"**, you will have a subfolder for each **partition**. As my hard drive contains a single partition, its all contained in a folder, labelled **"/media/sda1-ata-MAXTOR\_STM316021".**

Once you get that, it won't be hard to identify your local ROM paths. I store my current MAME ROMS in "C:\Roms\Mame", so I will select "**"/media/sda1-ata-MAXTOR\_STM316021/Roms/Mame"** from the above list.

And that's all! By doing this, both **AdvmenuPLUS** and **GroovyMAME** will find your local ROMs. You don't need to do any further teaking of config files or anything, this is already done for you by gasetup.

You can exit now, or go on with the configuration of the other systems. Notice that for each console system, you have two options available. For instance, you have both **"Sega Megadrive/Genesis"** and **"UME - Sega Megadrive/Genesis"**. The first one configures the **Mednafen** emulator for Megadrive/Genesis. The second one does the corresponding configuration for **GroovyUME**.

**GroovyUME** is the preferred emulator for console systems in Groovy Arcade. However, it has high CPU requirements, so you'll need a powerful PC to emulate most of the systems.

There's an additional path you need to setup for **GroovyUME** to work, its name is **"UME - BIOS ROMs"** and it is the path where the different system bioses are stored. These are required by **GroovyUME**.

Finally, we will configure the snaps paths, so that **AdvmenuPLUS** can show a nice snapshot for our games. The process is analogue to adding ROM paths, you just need to use the option **"Add Snap path"** and configure each system individually.

There's an alternative method for ROMs/snaps searching that may be faster in some situations. From the main menu, enter the option **"File Manager (MC)"**. This will lauch **Midnight Commander"**, a nice text based disk explorer. Browse your system and enter the folder that contains the ROM/snap files you want to use with a particular emulator. Then press "F2" to show the menu. You will see an option named **"Add ROMs/Snaps path"**. Select this option and a script will be launched so you can choose the emulator you want to setup. Follow the instructions. Just decide which of the two methods you prefer.

Time to launch **AdvmenuPLUS** (remind: **"Start Front-End / Window Manager"** in the main menu) and you're ready to enjoy. Tip: use "5"/"6" or "F5"/"F6" to switch between systems.

Have fun,

The Groovy Arcade Team