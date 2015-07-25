

# Introduction #
GroovyArcade is regarded by enthusiasts as the OS of choice for easily running a wide variety of emulators. It offers support for various frontends and has been tweaked for both CRT and LCD monitors.

This guide is recommended for users who wish to perform a HDD installation of GroovyArcade.

## About GroovyArcade ##
GroovyArcade is a community driven project. It was primarily maintained by Ves.

If you like this project and wish to keep it alive consider contributing or donating to the project.

## Issues ##
Any issues with GroovyArcade are to be posted on
https://code.google.com/p/groovyarcade/issues/list

The WiKi has a guide [here](https://code.google.com/p/groovyarcade/wiki/Reporting_problems) explaining how to post an issue.

## Support ##
Please use the forum at [Build Your Own Arcade Controls (BYOAC)](http://forum.arcadecontrols.com/).

GroovyArcade support questions can be posted in the BYOAC GroovyMAME sub forum. So support posts are easily identifiable please use the following subject lines:
  * GroovyArcade Support - (your heading)
  * GroovyArcade Feature - (your heading)

# Installation #
## Obtaining GroovyArcade ##
[Download The Latest GroovyArcade ISO Here](https://e283dc88d509e5765cdd425ef94c1edb72be4a8f.googledrive.com/host/0B0NB2HYUHHktUFZXTWJfbHpzUlE/)

## Creating a Boot Device ##
### Windows USB ###
  * Insert your USB drive.
  * Download a suitable program to create a USB boot drive. Untested recommendations are:
    * [Yumi](http://www.pendrivelinux.com/yumi-multiboot-usb-creator/)
    * [USBWriter](http://sourceforge.net/projects/usbwriter/)
  * Follow the prompts and complete the installation.
### Linux USB ###
  * Insert your USB drive.
  * Identify your USB device.
```bash

$ dmesg |grep sd```
  * From this output you should be able to identify you USB drive device. Use DD to copy the files to your USB drive.
```bash

$ dd if=GroovyArcade-ArchYYYY.MM.DD-x86_64.iso of=/dev/sdb```
### Windows - Burn CD ###
  * Open Windows Explorer and browse to the directory containing the GroovyArcade ISO.
  * Right mouse click on the ISO file and select "Burn Disk Image"

## Installing GroovyArcade ##
  * Insert your GroovyArcade boot media into your PC. You may need to use an option key to bring up your boot menu.
  * **NOTE**: When using a 15 kHz CRT monitor with a video card that does not support a 15 kHz signal, ensure your CRT monitor is turned off until GroovyArcade has booted. If you don't you may damage your monitor. If you are unsure, turn your monitor off. Your alternatives are to use a Utlimarc [J-Pac](http://www.ultimarc.com/jpac.html), [Ultimarc ArcadeVGA](http://www.ultimarc.com/avgainf.html) or patch your ATI video card using [ATOM-15 ](http://geedorah.com/eiusdemmodi/forum/viewtopic.php?id=64)
  * Select your video card
> <img src='http://i.imgur.com/Wzp7Yj0.png' width='450'>
</li></ul><ul><li>Hit Enter on the below screen<br>
</li></ul><blockquote><img src='http://i.imgur.com/2seS1CG.png' width='450'>
</blockquote>  * Enter 2 setup
> <img src='http://i.imgur.com/drZVUZZ.png' width='450'>
</li></ul><ul><li>Enter 1 Video Setup<br>
</li></ul><blockquote><img src='http://i.imgur.com/o8FL2ad.png' width='450'>
</blockquote>  * Enter 1 Monitor Type
> <img src='http://i.imgur.com/metWb7A.png' width='450'>
</li></ul><ul><li>Select your monitor.<br>
<ul><li><b>NOTE</b>: Some users have recommended trying the generic/Arcade monitor types to see if the visuals improve.<br>
</li></ul></li></ul><blockquote><img src='http://i.imgur.com/DBru8o5.png' width='450'>
</blockquote>  * Select Yes
> <img src='http://i.imgur.com/41o93yE.png' width='450'>
</li></ul><ul><li>Select 2 Monitor Orientation and make your selection<br>
</li></ul><blockquote><img src='http://i.imgur.com/6hpCZfW.png' width='450'>
</blockquote>  * Select 3 Monitor aspect
> <img src='http://i.imgur.com/3lONjDs.png' width='450'>
</li></ul><ul><li>Leave all the other options and select 8 Return to Main<br>
</li></ul><blockquote><img src=' http://i.imgur.com/UjvC0Sl.png' width='450'>
</blockquote>  * Select 10 Return to Main
> <img src='http://i.imgur.com/fWLwDn1.png' width='450'>
</li></ul><ul><li>Select 3 HD Installation and Partition Tools<br>
</li></ul><blockquote><img src='http://i.imgur.com/hDUOlBf.png' width='450'>
<ul><li><b>NOTE</b>: I found that if you select option 2 Hard Drive Installation without an empty drive I would receive an error.<br>
</li></ul><blockquote><img src='http://i.imgur.com/z90xUtG.png' width='450'>
</blockquote>Ensure you have a empty drive or just boot into GroovyArcade, use the partition manager to delete all existing partitions. Reboot and load GroovyArcade again and follow these instructions. This guide will configure the Networking, Audio and some of the System Settings after installation.<br>
<ul><li>Do you want to setup Networking: No<br>
</li><li>Do you want to setup Audio: No<br>
</li><li>Do you want to setup System Settings: Yes<br>
</li></ul><blockquote><img src='http://i.imgur.com/A5k0ckQ.png' width='450'>
<ul><li>Select 1 Password<br>
</li></ul><blockquote><img src='http://i.imgur.com/7d4bUJU.png' width='450'>
</blockquote><ul><li>Enter in the password and select "Set root and arcade users password to arcade?" Yup. arcade was my chosen password in this demo.<br>
</li></ul><blockquote><img src='http://i.imgur.com/hifOjuq.png' width='450'>
</blockquote><ul><li>Select option 2 Language/Keyboard. This is to set your keyboard layout. I'm using a US keyboard layout. We will configure this option through the CLI.<br>
</li></ul><blockquote><img src='http://i.imgur.com/Ncl1YhX.png' width='450'>
<img src='http://i.imgur.com/uTnkrgZ.png' width='450'>
<img src='http://i.imgur.com/iKWbIDl.png' width='450'>
</blockquote><ul><li>If your keyboard layout did not change, configure it manually in post.<br>
</li></ul></blockquote><ul><li>Select Return to Main Menu twice.<br>
</li></ul></blockquote><ul><li>Select if you would like to mount a roms drive.<br>
</li></ul><blockquote><img src='http://i.imgur.com/L5iY4Ld.png' width='450'>
</blockquote><ul><li>Select Yes to Auto Partition an empty drive.<br>
</li></ul><blockquote><img src='http://i.imgur.com/D7NHazr.png' width='450'>
</blockquote><ul><li>Select your drive drive. The most basic explanation is that SD is a drive/block device that isn't IDE. The A means the first B second etc. So I have /dev/sda being the first hard drive.<br>
</li></ul><blockquote><img src='http://i.imgur.com/pyGzKyX.png' width='450'>
</blockquote><ul><li>Click yes to erase all the partition. GroovyArcade will now start installing.<br>
</li></ul><blockquote><img src='http://i.imgur.com/We5dUn0.png' width='450'>
</blockquote><ul><li>Once the installation is finished select Yes and remove your media. And select Yes to Really Reboot System?</li></ul>

By default it will launch into AdvanceMamePlus unless you selected a different fronted.<br>
<br>
<h1>Post Installation</h1>

<h2>Changing the Keyboard Map</h2>
To configure your keyboard map Exit to shell from the CLI and type the below commands:<br>
<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ sudo localectl set-keymap us<br>
[arcade@GroovyArcade ~]$ localectl status</code></pre>
<img src='http://i.imgur.com/GnLZ0Ii.png' width='450'>

<h2>Configuring a Static IP Address</h2>
If you have any issues assigning a static IP through gasetup execute these commands through the CLI.<br>
<br>
Source: <a href='https://wiki.archlinux.org/index.php/Netctl'>https://wiki.archlinux.org/index.php/Netctl</a>

<pre><code><br>
[arcade@GroovyArcade ~]$ sudo netctl disable wired<br>
[arcade@GroovyArcade ~]$ sudo systemctl disable netclt@wired<br>
[arcade@GroovyArcade ~]$ sudo netctl stop wired</code></pre>
Now edit your static IP in the wired profile<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ sudo vi /etc/netctl/wired<br>
[arcade@GroovyArcade ~]$ sudo netctl reenable wired &amp;&amp; netctl restart wired</code></pre>

<img src='http://i.imgur.com/uswh5k8.png' width='450'>

<h2>Locating Files</h2>
Next I will install mlocate. This tool index's the files on your HDD so you can easily search for them.<br>
<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ sudo pacman -S mlocate<br>
[arcade@GroovyArcade ~]$ sudo updatedb</code></pre>

<h2>Configuring ume.ini</h2>
GroovyArcade uses GroovyUME.<br>
<br>
GroovyUME is a combination of GroovyMAME and MESS.<br>
<br>
By applying the GroovyMAME patch to the UME target, Calamity has developed a universal emulator that can benefit from the arcade modeline stuff for console systems too, which includes the improved sync options GroovyMAME implements as standard. In plain English for those of us who have had a few too many beers, it means that when you load any console up through GroovyUME it will automatically use the SwitchRes program to match the resolution and frequency rate of that console game, similar to how most of you have MAME set up looking arcade perfect, you can now do the same for older console systems listed above.<br>
<br>
Source: <a href='http://www.hyperspin-fe.com/forum/showthread.php?24809-One-Emulator-to-Rule-Them-All-GroovyUME-by-Calamity-DrMaxwell-s-AHK-Script'>DrMaxWell</a>

First lets remove nag screens, skip game info, and enable cheats. Ensure ume.ini has the below options set.<br>
<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ vi /home/arcade/ume.ini<br>
<br>
skip_gameinfo 1<br>
<br>
disable_hiscore_patch     0<br>
disable_nagscreen_patch   0<br>
disable_loading_patch     0<br>
<br>
cheat                     1</code></pre>

<h2>Cheats</h2>
Download the latest cheats file from <a href='http://cheat.retrogames.com/'>http://cheat.retrogames.com/</a>
<pre><code><br>
[arcade@GroovyArcade ~]$ cd /home/roms/MAME<br>
[arcade@GroovyArcade ~]$ wget http://cheat.retrogames.com/download/cheat0156.zip<br>
<br>
[arcade@GroovyArcade ~]$ 7z e cheat0156.zip<br>
<br>
[arcade@GroovyArcade ~]$ rm cheat0156.zip</code></pre>

Make sure you followed the steps in Configuring ume.ini and enabled cheats.<br>
<br>
<h2>Managing GroovyArcade</h2>
GroovyArcade has SSH enabled. You can use a tool like <a href='http://www.chiark.greenend.org.uk/~sgtatham/putty/'>putty</a> to logon and configure your system over a network.<br>
<br>
SMB has been enabled so you can access the two main directories of GroovyArcade over a network.<br>
<br>
Just type in<br>
\\yourip e.g \\192.168.1.11<br>
<br>
<img src='http://i.imgur.com/K6c14YQ.png' width='450'>

<ul><li>You can password protect the shares if you desire.<br>
</li><li>You can edit files like ume.ini and copy your roms files over a network by browsing to the correct directory.</li></ul>

<h2>Updating GroovyArcade</h2>
To Be Completed<br>
<br>
<ul><li>Updating GroovyMAME/ GroovyUME</li></ul>

<h2>Updating the Operating System</h2>
Before upgrading you should choose a <a href='https://wiki.archlinux.org/index.php/mirrors'>local mirror</a>.<br>
<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ sudo vi /etc/pacman.conf<br>
<br>
[core]<br>
Server = ftp://ftp.hosteurope.de/mirror/ftp.archlinux.org/core/os/$arch<br>
<br>
Include = /etc/pacman.d/mirrorlist</code></pre>

The operating system can be updated through the CLI using the below command:<br>
<pre><code><br>
[arcade@GroovyArcade ~]$ sudo pacman -Syu </code></pre>