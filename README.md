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
See [repo command reference](https://source.android.com/setup/develop/repo) for details


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

As first test it is suggested to build the `core-minimal-image` provided by Poky Yocto 

```
bitbake -k core-image-minimal
```
In case you want to build the `engicam-test-hw` image, in order to use `firmware-imx` you need to accept the *Freescale EULA* at `/sources/meta-freescale/EULA`. Please read it and in case you accept it, write: `ACCEPT_FSL_EULA = "1"` in your `local.conf`.

```
bitbake -k engicam-test-hw
```


## Notes

This is a kit composed by these repositories

* The repo setup (this one) : https://github.com/koansoftware/koan-engicam-mx6-bsp-repo
* The base files : https://github.com/koansoftware/koan-engicam-mx6-base
* The customized meta layer: https://github.com/koansoftware/meta-engicam

## Contributing

Please use GitHub (https://github.com/koansoftware/koan-engicam-mx6-bsp-repo) to submit issues or pull requests, or add to the documentation on the wiki. Contributions are welcome!

------

(C)2020 Copyright - KOAN sas - <https://koansoftware.com>

