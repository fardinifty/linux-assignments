FARDIN HOSSAIN IFTY, amk100839@student.hamk.fi
TASK 6

Part 1: Understanding APT & System Updates. 
* Updating the package list is important because shis command updates the list of available packages from the repositories to ensure that I get the latest versions of packages before installing or upgrading.
* The differece between update and upgrade is "apt update" updates the list of available package versions and "apt upgrade" upgrades installed packages to their latest available versions.
* NO, theres no pending updates.
  
Part 2: Installing & Managing Packages.
* I picked this packagefrom the list- 
gimp/noble-updates 2.10.36-3ubuntu0.24.04.1 amd64
  GNU Image Manipulation Program
* This gimp package depends on these following:  libgimp2.0t64 (>= 2.10.36), libgimp2.0t64 (<= 2.10.36-z), gimp-data (>= 2.10.36), gimp-data (<= 2.10.36-z), graphviz, xdg-utils, libaa1 (>= 1.4p5), libbabl-0.1-0 (>= 1:0.1.78), libbz2-1.0, libc6 (>= 2.38), libcairo2 (>= 1.12.2), libfontconfig1 (>= 2.12.6), libfreetype6 (>= 2.2.1), libgcc-s1 (>= 3.3.1), libgdk-pixbuf-2.0-0 (>= 2.30.8), libgegl-0.4-0t64 (>= 1:0.4.38), libgexiv2-2 (>= 0.10.6), libglib2.0-0t64 (>= 2.79.0), libgs10 (>= 9.10~dfsg), libgtk2.0-0t64 (>= 2.24.10), libgudev-1.0-0 (>= 167), libharfbuzz0b (>= 0.6.0), libheif1 (>= 1.13.0), libjpeg8 (>= 8c), libjson-glib-1.0-0 (>= 1.5.2), libjxl0.7 (>= 0.7.0), liblcms2-2 (>= 2.9), liblzma5 (>= 5.1.1alpha+20120614), libmng2 (>= 2.0.2), libmypaint-1.5-1 (>= 1.5.0), libopenexr-3-1-30 (>= 3.1.5), libopenjp2-7 (>= 2.0.0), libpango-1.0-0 (>= 1.29.4), libpangocairo-1.0-0 (>= 1.29.4), libpangoft2-1.0-0 (>= 1.29.4), libpng16-16t64 (>= 1.6.2), libpoppler-glib8t64 (>= 0.44.0), librsvg2-2 (>= 2.32.0), libstdc++6 (>= 13.1), libtiff6 (>= 4.0.3), libwebp7 (>= 1.3.2), libwebpdemux2 (>= 1.3.2), libwebpmux3 (>= 1.3.2), libwmf-0.2-7 (>= 0.2.12), libwmflite-0.2-7 (>= 0.2.12), libx11-6, libxcursor1 (>> 1.1.2), libxext6, libxfixes3, libxmu6 (>= 2:1.1.3), libxpm4, zlib1g (>= 1:1.1.4)
* yes, the package has been installed successfully. And the version is 2.10.36-3ubuntu0.24.04.1 amd64

Part 4: Managing Repositories & Troubleshooting.
* Yes, the package removed.
* The difference between remove and purge is "remove" uninstalls the package but keeps configuration files and purge removes the package and its configuration files.
* This step is important because it removes orphaned dependencies that are no longer needed.
* It deletes cached package files from /var/cache/apt/archives to free up space.

Part 4: Managing Repositories & Troubleshooting
*This file contains URLs of package repositories.
*The universe repository contains community-maintained open-source software.
*I tried installing non existing packege and i get "E: Unable to locate package fakepackage" this message. To troubleshoot this issue I will Check for typos in the package name, run sudo apt update to refresh package lists, search for the correct package name using apt search.
