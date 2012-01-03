# Play debian package

These scripts allow you to build a debian packages from the official play distribution.

## Pre-requisite

You need a debian or ubuntu system. On the system, the following packages need to be installed:
* build-essential 
* dh-make
* fakeroot
* curl

## Play version configuration

Building a package is easy. Simply edit the file debian/playversion and indicate the right version number (i.e. 1.2.4). You also need to edit the file debian/control and fill in the right version number for the Standard-Version field.
Once this is done, run the command `dch -i' and input the changes to your package.

## Building the debian package

To build the package simply run `fakeroot dpkg-buildpackage -b` from the project root directory. The scripts will download the right play distribution.

## Switching to a previous play version

If you have multiple play versions installed on your server, you can switch from one version to another using the `update-play-alternatives`. 
There are 2 commands:
* `update-play-alternatives -l` list the different play version
* `update-play-alternatives -s {version}` set the current play version to {version}

## Play id

The debian package set the default play id to *prod*. You can change this value by running `play id`. The value is stored in /etc/play/{version}/id