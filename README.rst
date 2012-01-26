----------------------------------------------
Chantilly Robotics Guillotine Drive Code
----------------------------------------------

This project contains `FIRST Team 612 Chantilly Robotics`_' code for driving
the 2011 robot, Guillotine.

Notes
++++++++++++++++

As last year's code was entirely written in LabVIEW, this code is a rewrite and
a work in progress.  Not all functionality is implemented.  Additionally, many
components of Guillotine are salvaged, so only basic funcitonality is available
unless some of the components are reinstalled.

This code also can provide a base for future code on subsequent robots.  A fork
of this repository can provide a nice foundation for new robot code.

The code may require updates and maintainance as the API and libraries are
changed.  The WPILib version must be compatible with the image version in order
for the kernel to load the user code module.

This code was originally branched off of the 2012 code base and retroactivly
adjusted to work with the 2011 robot.  The commit it is based off of is
2456a3baea47ccf0545896d48892d5b63337b5b8.

Usage
++++++++++++++++

For now, this project assumes that you already have ucpp_ installed and
configured for your system.  The build process is as follows::

  $ ucpp init               #run once
  $ ucpp configure          #run each time the files in the project have changed
  $ make                    #compile and link all code (debug)
  $ make DEBUG_MODE=0       #compile and link all code (release)
  $ make deploy             #deploy code to robot

For more information regarding ucpp, see 'ucpp.rst'.

Configuring
++++++++++++++++

 - Some configuration is required on the cRIO to get everything to work.  First,
   when imaging it is necessary to select the option for WindRiver C++, and please
   enable NetConsole (except for in perhaps release builds).
 - Remember that the cRIO runs an ftp server that allows anonymous ftp access.
 - Second, for NetConsole to work ni-rt.ini needs to have the DNS and default
   gateway set to the router.  The default is 10.6.12.1, and, though this works on
   the field, it will not allow NetConsole to work for debugging.  The subnet mask
   of computer running NetConsole must also be set to 255.0.0.0 (not the more
   intuitive 255.255.255.0).
    - Again, without these changes, the robot will still DRIVE fine.
 - FOR NOW, the robot REQUIRES version 30 of the firmware.  This WILL change come
   build season, though!
 - Be sure to undo any/all changes to ni-rt.ini before going onto the field!!!

License
++++++++++++++++

All code in this project is licensed under the ISC License (see 'LICENSE.rst')
and is Copyright |c| 2012 Chantilly Robotics unless otherwise noted.

Contributors
++++++++++++++++

A full list of contributors is in 'AUTHORS.rst'.

Thanks
++++++++++++++++
Thanks go out to nikitakit and all the other developers of the ucpp_ project.
Thanks to github_ for providing hosting of our code.
And finally, a big thanks to the entire organization of FIRST_.


.. _`FIRST Team 612 Chantilly Robotics`: http://www.chantillyrobotics.org/
.. _ucpp: https://github.com/nikitakit/ucpp
.. _github: https://github.com/
.. _FIRST: http://usfirst.org/
.. |c| unicode:: 0xA9 .. (Copyright (c) Sign)
