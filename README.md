# Koan BSP for Engicam iMX6 - Yocto Project

To get the BSP you need to have `repo` installed and use it as:

## Install the `repo` utility:

```
$: mkdir ~/bin
$: curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
$: chmod a+x ~/bin/repo
```

## Download the BSP source:

```
$: PATH=${PATH}:~/bin
$: mkdir yocto-engicam-mx6-warrior
$: cd yocto-engicam-mx6-warrior
$: repo init -u https://github.com/koansoftware/koan-engicam-mx6-bsp-repo -b warrior
$: repo sync -j8
```

Now you have downloaded the source of all projects

## First time

```
$: MACHINE=microgea DISTRO=poky source ./setup-environment build
```
NOTE: Other times, call `source ./setup-environment build`


After this step, you will be with everything need for build an image.

## Build image

```
bitbake -k core-image-minimal
```

Copyright (C)2020 KOAN - <https://koansoftware.com>
