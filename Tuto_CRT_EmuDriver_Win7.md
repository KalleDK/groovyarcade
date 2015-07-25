# Introduction #

Add your content here.


# Installation notes #

1.- For safety, make sure UAC is enabled until you have everything up and running. This will avoid installation issues.

2.- Run the Setup program on the package with ADMIN RIGHTS enabled.

3.- DO NOT restart the system when W7 prompts you to do so, let the Setup program finish, allow it to set TEST mode on.

4.- CRT Emudriver for W7 doesn't boot in 15 kHz automatically after restart. You need to enable it manually, but this is a little tricky unless you have a multisync monitor. If you have standard arcade monitor, here are the steps you MUST follow:

4.1.- Install the driver using a computer monitor (LCD or CRT 31 kHz capable monitor)

4.2.- Once installed, turn the computer off and plug your arcade monitor.

4.3.- Boot the machine, with the arcade monitor **turn off** (keep it off to avoid bad frequencies in, not needed if you have a jpac)

4.4.- Once you hear W7 sound so you're sure the boot process is ready, unplug the arcade monitor and plug the computer monitor on the same output you were using for the arcade monitor. The purpose of this thing is to avoid W7 reading the LCD's EDID during the boot process.

4.5.- Now you should have a 31 kHz picture on your computer monitor. Go into screen properties, advanced, show all modes. In the list there should be this mode: 640 x 480 @ 30 Hz. 30 Hz stands for interlaced here. That's a 15 kHz mode. Select it and apply. Now your computer monitor should get out of sync.

4.6.- Plug your arcade monitor now. You should get a stable picture.

4.7.- Go **again** into screen properties, advanced, show all modes and re-select 640 x 480 @ 30 Hz and apply. This is required so that the mode "sticks" after the cable swap.

4.8.- Now reboot, and if everything is all right, you should have a stable 15 Khz mode on your monitor since now on each restart.


In case you're going to use VMMaker and ArcadeOSD, make sure to use the ones in the package, and run them with admin rights. Magic resolutions won't work in W7, so make sure to disable it from vmmaker.ini (it's enabled by default) and use Super Resolutions.


# The UAC prompt fix #

With regards to setting admin priviliges for GM in Win7 (needed for the automatic modeline refresh rate adjustment), there is a neat way of having it enabled by default just so that you don't have to manually confirm the UAC prompt everytime you start GM.

By following these two steps it effectively mimics WindowsXP behaviour, i.e. there's no prompt upon starting GM and it can read and write to the registry:

1. Set admin privileges for the GM executable as described in OPTION 5 from this link: http://www.sevenforums.com/tutorials/11841-run-administrator.html. This will prompt you everytime you start GM to confirm that you want to allow admin priviliges for GM (allow reading/writing to registry).

2. This step allows programs (as configured in step 1) to run in administrator mode **without** bringing up the UAC prompt. Note that it will only allow this option to be set for the administrator account/user. The steps to follow are described on the microsoft forum here: http://answers.microsoft.com/en-us/windows/forum/windows_vista-security/uac-and-one-program-used-very-regulary/67bfc4b5-faff-4de4-be48-f395bf1c519d.