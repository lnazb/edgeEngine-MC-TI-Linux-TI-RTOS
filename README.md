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

# Usage Guide
edgeChild-ti-rtos is provided as a static library.  It should be linked into the TDA4VM mcu2_0 RTOS build, and call the mimik_main() C function to start the edgeChild.

1. Download latest release [HERE](https://github.com/edgeEngine/edgeEngine-MC-TI-Linux-TI-RTOS/releases)
2. *Untar package (ex:)
```
tar xvf edgeChild-ti-rtos-v1.0.0.tar
```
