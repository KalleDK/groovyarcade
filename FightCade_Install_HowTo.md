# Introduction #
FightCade is a new online retro arcade gaming platform to play your favorite arcade games against opponents around the world.

  * It records your game and provides the ability to replay it - http://www.fightcade.com/replay/
  * Records attendance stats - http://www.fightcade.com/stats/
  * Player Profiles - http://www.fightcade.com/id/pof

# Installing FightCade on GroovyArcade #
To install FightCade on GroovyArcade follow the below steps.

Download and extract the FightCade package.

```bash
$ cd /home/arcade/emulators
$ wget http://www.fightcade.com/download/fightcade-linux-v040.tar.gz
```

We will update the Arch Linux package list to ensure we are installing the latest packages.
```bash
$ sudo pacman -Sy```

Extract the package and run the installation script included with FightCade.
```bash
$ tar -zxvf fightcade-linux-v040.tar.gz
$ cd FightCade

$ sudo ./linux-install.sh```

You will be asked to select qt4 backend. Press 1 to select phonon-qt4-gstreamer

```

:: There are 2 providers available for phonon-qt4-backend:
:: Repository extra
1) phonon-qt4-gstreamer  2) phonon-qt4-vlc
```

The installation script included with FightCade v040 doesn't install all the required packages to enable FightCade to run. Execute the command below to install the additional packages.

```bash
 $ sudo pacman -S extra/python2-sip extra/python2-pyqt4 multilib/lib32-mpg123```

We will create a shortcut to launch FightCade from the desktop. Add the below information into a file named FightCade.desktop. You can use a text editor rather than the "cat" command.
```bash

cat > /home/arcade/Desktop/FightCade.desktop
[Desktop Entry]

Version=0.26
Encoding=UTF-8
Name=FightCade
Comment=Online retro arcade gaming platform
Exec=/home/arcade/emulators/FightCade/fightcade
Terminal=false
Type=Application
Icon=/home/arcade/emulators/FightCade/assets/icon-128.png
Categories=Game;ArcadeGame;
StartupNotify=False
GenericName[en_GB]=
```
Press CTRL-D to exit and save your file.

To launch FightCade we will navigate through the GroovyArcade Linux Setup menu and change our FrontEnd to LXDE. This gives us a desktop environment to launch FightCade. If you used the exit to shell option type
```
sudo gasetup``` to return to the GroovyArcade Linux Setup.

In the Groovy Arcade Linux Setup Menu select:
  * 2 Setup (video, audio, network, etc.)
  * 5 Front-End / Window Manager
  * 2 LXDE Desktop
  * Hit enter on OK
  * 5 Return to Main
  * 10 Return to Main
  * 1 Start Front-End / Window Manager

You will now be in a desktop environment and be able to see your FightCade shortcut. Double click on it to launch FightCade.

After creating an account and logging in select "Settings -> Locate Roms Folder"

When you start or watch a game, the Final Burn Alpha emulator will load. Through here you can remap your keys and set your desired screen configuration.

When prompted install the below Wine packages. An internet connection is required.
  * Wine Mono package.
  * Wine Gecko package.

## Advanced Configuration ##
For advanced users, you can edit the configuration file manually. All other uses should use the GUI to configure their options.

```bash
$ vim /home/arcade/emulators/FightCade/config/ggpofba-ng.default.ini```