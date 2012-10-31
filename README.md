# Play debian package

These scripts allow you to build a debian packages from the official play distribution.

## Download the latest debian package

If you don't want to build the package yourself, you can download the latest [play 1.2.4 debian package](https://github.com/downloads/lunatech-labs/play-debian-package/play_1.2.4-1_all.deb). 
You can also [browse from previous versions](https://github.com/lunatech-labs/play-debian-package/downloads).

## Pre-requisite

You need a debian or ubuntu system. On the system, the following packages need to be installed:

 * build-essential 
 * dh-make
 * devscripts
 * fakeroot
 * curl

## Play version configuration

Building a package is easy. Simply:

1. edit the file debian/playversion and indicate the right version number (i.e. 1.2.4). 
1. edit the file debian/control and fill in the right version number for the Standard-Version field.
1. run the command `dch -i' and log the changes to your package.

## Building the debian package

To build the package simply, `fakeroot dpkg-buildpackage -b` from this project root directory. The scripts will download the correct play distribution.

## Switching to a previous play version

If you have multiple play versions installed on your server, you can switch from one version to another using the `update-play-alternatives`. 

There are 2 commands:

 * `update-play-alternatives -l` list the different play version
 * `update-play-alternatives -s {version}` set the current play version to {version}

## Play id

> The debian package set the default play id to *prod*. 

You can change this value by running `play id`. The value is stored in /etc/play/{version}/id

## Licence

This software is licensed under the Apache 2 license, quoted below.

Copyright 2011 Lunatech Labs (http://www.lunatech-labs.com).

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this project except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.