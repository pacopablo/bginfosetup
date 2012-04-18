BgInfo Setup
=============

BgInfo_ is an awesome tool.  It will show various system configuraiton
information on the desktop.  This is especiialy useful when using RDP to
access multiple servers remotely.  At a glance, one can know to which system
they are connected.

BgInfo is distributed as a zip file containing the application.  This is
great until one wants to customize the configuration and deploy BgInfo to
multiple computers.  Running BgInfo via `Group Policy`_ is one solution.
Another solution is to create an installation package for BgInfo.

Not surprisingly, BgInfo's license prohibits its re-distribution.  Therefore,
one cannot simply create an installer and present it to the Internet.
However, it is simple enough to download BgInfo and create your own installer
for one's own use.

Requirements
------------

Download the following:

#. BgInfo_
#. InnoSetup_
#. This project (pacopablo-bginfosetup-4.16.1beta.zip_)

Prep
----

#. Unzip ``pacopablo-bginfosetup-4.16.1.zip`` to ``C:\bginfosetup``

   |unzip_project|

#. Unhelpfully, GiHub_ has packged the files into a directory labeled
   ``pacopablo-bginfosetup-4.16.1-XXXX.zip``, where ``XXXX`` is some part of a
   hash. Move ``bginfosetup.iss`` and ``logon.bgi`` from the unzipped
   directory to ``C:\bginfosetup``

#. Install InnoSetup_
#. Unzip BgInfo_ to ``C:\bginfosetup\``

Building the Installer
----------------------

#. Double-click on the ``bginfosetup.iss`` file.  This should launch InnoSetup_
#. Build the project by pressing ``Ctrl-F9``, the toolbar button
   or selecting ``Build->Compile`` from the menu.

If no errors are encountered, the setup file, ``bginfosetup.exe`` should be
located in ``C:\bgsetupinfo\Output\``

Running the installer
---------------------

Double-clicking on the installer will run one through a pretty standard
windows installer prompting for various pieces of information.  The installer
will allow one to select the destination directory along with the Start Menu
location.  By default, the installer puts the files into ``C:\Program
Files\BGInfo``, or ``C:\Program Files (x86)\BGinfo`` if on a 64bit Windows
installation.  The default Start Menu location is ``Accessories\BGInfo``.
Additionally, one can choose to run BgInfo after install.

The installer also sets BgInfo to launch on login so one can always enjoy
BgInfo goodness.


Customize BgInfo
----------------

Once installed, if one wants to change the information displayed by BgInfo,
run ``BGInfo Change Config`` found under ``Start->Accessories->BGInfo``.  This
will start BgInfo in edit mode with a timeout of 10 seconds [#f1]_.  Click on
the ``Timeout`` button to stop the timer.  One can modify the template and
then save it to ``C:\Program Files\BGInfo\logon.bgi`` [#f2]_ and the changes will be
preserved for the next logon.  Additionally, one can run ``BGInfo`` found
under ``Start->Accessories->BGInfo`` to apply the changes immediately.


.. rubric:: Footnoes

.. [#f1] Using a timeout other than ``/timer:0`` caused BgInfo to crash under
         Windows Server 2008 R2 SP1.

.. [#f2] Adjust path to reflect the location used during install.


.. links

.. _BgInfo: http://technet.microsoft.com/en-us/sysinternals/bb897557N
.. _Group Policy: http://forum.sysinternals.com/topic17828_post89946.html#89946
.. _InnoSetup: http://www.jrsoftware.org/isinfo.php
.. _pacopablo-bginfosetup-4.16.1.zip: https://github.com/pacopablo/bginfosetup/zipball/4.16.1

.. images

.. |unzip_project| image:: http://github.com/pacopablo/bginfosetup/raw/master/imgs/unzip_project.png
