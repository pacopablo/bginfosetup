BgInfo Setup
=============

BgInfo_ is an awesome tool.  It will show various system configuraiton
information on the desktop.  This is especiialy useful when using RDP to
access multiple servers remotely.  At a glance, one can know to which system
they are connected.

BgInfo_ is distributed as a zip file containing the application.  This is
great until one wants to customize the configuration and deploy BgInfo_ to
multiple computers.  Running BgInfo_ via `Group Policy`_ is one solution.
Another solution is to create an installation package for BgInfo_.

Not surprisingly, BgInfo_'s license prohibits its re-distribution.  Therefore,
one cannot simply create an installer and present it to the Internet.
However, it is simple enough to download BgInfo_ and create your own installer
for one's own use.

Requirements
------------

Download the following

# BgInfo
# InnoSetup
# ``bginfosetup.iss`` file from this project

Prep
----

The following instructions assume being logged into a Windows 7 or Server 2008
series machine.  InnoSetup_ will work fine on an XP or Server 2003 machine.
The path to the BgInfo_ files will need to be changed to reflect its location
on an XP or 2003 machine.

# Clone the project to ``C:\bginfosetup``

  ::

   git clone git://github.com/pacopablo/bginfosetup C:\bginfosetup

# Install InnoSetup_
# Unzip BgInfo_ to ``%USERPROFILE%\Downloads\BGInfo``

Building the Installer
----------------------

# Double-click on the ``bginfosetup.iss`` file.  This should launch InnoSetup_
# Build the project by pressing ``Ctrl-F9``, the toolbar button, or selecting
  ``Build->Compile`` from the menu.

If no errors are encountered, the setup file, ``bgsetup.exe`` should be
located in ``C:\bgsetupinfo\Output\``



.. _BgInfo: http://technet.microsoft.com/en-us/sysinternals/bb897557N
.. _Group Policy: http://forum.sysinternals.com/topic17828_post89946.html#89946
.. _InnoSetup: http://www.jrsoftware.org/isinfo.php

