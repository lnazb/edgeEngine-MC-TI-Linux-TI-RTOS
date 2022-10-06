# edgeEngine-ti-linux
edgeEngine for TI Linux Platform

# Installation Guide
1. Download latest release [HERE](https://github.com/edgeEngine/edgeEngine-MC-TI-Linux-TI-RTOS/releases)
2. Create new directory
3. Move package to newly created directory 
4. Open terminal and navigate to the newly created directory that now has the downloaded .tar file
5. *Untar package (ex:)
```
tar xvf edgeEngine-ti-linux-v3.0.0.tar
```
6. Run start script to start edgeEngine
```
./start.sh
```
7. Please visit https://developer.mimik.com and create your account and get more information

## NOTE:
* A directory may be made after untaring. Navigate into that directory to find `start.sh` script 
- Do not close terminal window where edgeEngine is running. Closing this window will terminate edgeEngine process
- To stop edgeEngine simply close or use keyboard shortcut CTRL + C in terminal window where edgeEngine is running


# edgeChild-ti-rtos
edgeChild for TI RTOS Platform

Currently it is based on vision_apps. Prepare environment, compile and running it, please read the Ti [document](https://software-dl.ti.com/jacinto7/esd/processor-sdk-rtos-jacinto7/latest/exports/docs/vision_apps/docs/user_guide/BUILD_AND_RUN.html). 

## Building instructions
edgeChild-ti-rtos is provided as a static library.  It should be linked into the TDA4VM mcu2_0 RTOS build, and call the mimik_main() C function to start the edgeChild.

1. Download latest release [HERE](https://github.com/edgeEngine/edgeEngine-MC-TI-Linux-TI-RTOS/releases)
2. *Untar package (ex:)
```
$ tar xvf edgeChild-ti-rtos-v1.0.0.tar
```
3. replace the folder vision_apps/platform/j721e/rtos/mcu2_0 with mcu2_0 in this repository. 
set up environment variables for Ti psdk rtos path and psdk linux path as the following.
```shell
$ export PSDKR_PATH=/home/user1/jacinto/ti-processor-sdk-rtos-j721e-evm-08_02_00_05
$ export PSDKL_PATH=/home/user1/jacinto/ti-processor-sdk-linux-j7-evm-08_02_00_03
```
4. at vision_apps directory, build vision_apps including the edge runtime for rtos mcu2_0 as the following.
```shell
$ make vision_apps -j3
```

## Install the vision_apps with the edge runtime for rtos

Insert the prepared vision_apps sdcard on the Linux machine, at vision_apps directory, install the vision_apps with the edge runtime for rtos as the following
```shell
$ make linux_fs_install_sd
```

## Run the vision_apps with the edge runtime for rtos

plugin the sdcard to the Ti Jacinto 7 j721e board, and power up the board, the bootloader will load the mcu image and run it, the edge runtime is also running.
to see the running log, login the the j721e linux as the following
```shell
$ ssh root@10.0.0.96
```
e.g the j721e ip is 10.0.0.96. to see the all the logs as the following.
```shell
$ cd /opt/vision_apps
$ ../vision_apps_init.sh
```

It shows all the cpu, mcu, and dsp processors running logs
