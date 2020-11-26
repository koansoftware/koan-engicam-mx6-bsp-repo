![koansoftware.com](https://www.koansoftware.com/wp-content/uploads/2019/06/logo_head_3-300x138.jpg)

# Koan BSP for Engicam iMX6 - Yocto Project

This is the unofficial Yocto Project setup system for Engicam iMX6 boards family.

![engicam.com](https://www.engicam.com/grafiche/personalizzate/engicam2/style/images/logo.png)


## Install the `repo` utility

To get the BSP you need to have `repo` installed and use it as:

```
$: mkdir ~/bin
$: curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
$: chmod a+x ~/bin/repo
```

## Download the BSP source

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

Contributing
-------
Please use GitHub (https://github.com/koansoftware/koan-engicam-mx6-bsp-repo) to submit issues or pull requests, or add to the documentation on the wiki. Contributions are welcome!

------

(C)2020 Copyright - KOAN sas - <https://koansoftware.com>

